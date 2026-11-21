# Rules and rates API

These six POST routes accept JSON, require no session in their handlers, and do not write database rows. Rule responses use `cardName`, `title` and `enabled`. Fields and services described below are properties of the returned JSON.

| Method and path | Example body | 200 response and assertions | Handler errors |
| --- | --- | --- | --- |
| POST /api/rules/sender | `{"from":{"country":"Saudi Arabia"}}` | `fields` includes sender name, phone, country, city, street and postal code. Country options are `{value,label}`. Gulf origin sets street and its validation to required. | 500 rule loading failure |
| POST /api/rules/receiver | `{"from":{"country":"Saudi Arabia"},"to":{"country":"Iraq"}}` | Receiver fields, `context:{senderCountry,receiverCountry}` and `validationErrors`. This example has a route error at `validationErrors.receiverCountry` despite HTTP 200. Gulf destinations require street. | 500 rule loading failure |
| POST /api/rules/package | `{"from":{"country":"Egypt"},"to":{"country":"Saudi Arabia"}}` | `fields` for weight, length, width, height and item description, plus `shipmentType,maxWeight,maxDimension,context`. Example is International, 25 kg, 200 cm, and description visible and required. | 400 missing countries or invalid type, 500 rule loading failure |
| POST /api/rules/service | `{"shipmentType":"IntraGulf","package":{"weight":21}}` | `shipmentType,services,context:{weight}`. Example returns Gulf Standard only. Missing or unparseable weight returns all services for a valid type and null context weight. Overweight can give an empty array with 200. | 400 missing or invalid type, 404 no catalog for type, 500 rule loading failure |
| POST /api/rules/additional-options | `{"from":{"country":"Saudi Arabia"},"to":{"country":"Egypt"},"package":{"weight":18}}` | `fields` for signature, liquid, insurance, packaging and pickup, plus `context:{senderCountry,receiverCountry,weight}`. Example forces signature and disables home pickup. | 500 rule loading failure |
| POST /api/rates | See sample below | `totalPrice,breakdown,context` | 400 missing required values or over service weight, 404 unknown service, 500 calculation failure |

Field descriptors may include `type,label,required,placeholder,visible,validation,options`, depending on the field. Option descriptors can include `checked,disabled,defaultValue,allowedValues,disabledValues`. Validation metadata can include `required,minLength,maxLength,min,max,errorMessage`. Each catalog service has `id,name,description,maxWeight,basePrice,pricePerKg,deliveryDays`.

| Shipment type | Service IDs |
| --- | --- |
| Domestic | `domestic_standard`, `domestic_express` |
| IntraGulf | `gulf_standard`, `gulf_express` |
| International | `international_economy`, `international_standard` |

## Rate request and response

Required fields are `serviceId`, numeric `weight`, `senderCountry`, `receiverCountry` and `pickupMethod` (`home` or `postal_office`). Optional booleans are `signatureRequired`, `containsLiquid`, `insurance` and `packaging`. Send actual JSON booleans.

```json
{"serviceId":"international_economy","weight":12,"senderCountry":"Saudi Arabia","receiverCountry":"Egypt","pickupMethod":"home","signatureRequired":true,"insurance":true}
```

```json
{"totalPrice":87,"breakdown":{"baseCost":67,"signatureCost":5,"insuranceCost":15,"packagingCost":0,"liquidCost":0},"context":{"serviceName":"International Economy","shipmentType":"International","weight":12,"senderCountry":"Saudi Arabia","receiverCountry":"Egypt","pickupMethod":"home"}}
```

Amounts are numeric USD. The base cost includes pickup. A quote applies the flags supplied in the rate request. It does not apply the full booking checks, so use the rules endpoints for available options and the shipment finalization response to verify the authoritative stored total.

## Sources

- [src/routes/api/rates/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/rates/%2Bserver.ts)
- [src/routes/api/rules/additional-options/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/rules/additional-options/%2Bserver.ts)
- [src/routes/api/rules/package/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/rules/package/%2Bserver.ts)
- [src/routes/api/rules/receiver/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/rules/receiver/%2Bserver.ts)
- [src/routes/api/rules/sender/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/rules/sender/%2Bserver.ts)
- [src/routes/api/rules/service/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/rules/service/%2Bserver.ts)
