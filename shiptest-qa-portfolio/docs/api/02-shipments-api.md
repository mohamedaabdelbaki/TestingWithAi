# Shipments API

All routes in this document require the session cookie. Shipment list and ID operations use the signed-in user’s ownership. Use the numeric ID as the path parameter. A missing or other-account shipment returns 404 on ID-based operations.

| Method and path | Request | Success | Handler errors | Database effect |
| --- | --- | --- | --- | --- |
| GET /api/shipments | Query parameters below, no body | 200 list envelope below | 500 listing failure | Read rows and filtered count |
| POST /api/shipments | Flat shipment body below | 201 shipment object | 400 creation failure, may include details | Insert draft |
| POST /api/shipments/draft | Nested body with optional rates | 201 `{success:true,message:"Draft saved successfully",shipment}` | 400 invalid draft measurements with field errors, 500 save failure | Insert draft |
| POST /api/shipments/finalize | Complete nested body, incoming rates ignored | 201 finalization envelope below | 400 validation, pricing, or finalization failure | Insert shipment and mark finalized |
| GET /api/shipments/{id} | No body | 200 `{shipment}` | 400 invalid ID, 404 missing, 500 read failure | Read shipment |
| PUT /api/shipments/{id} | Nested body with optional rates | 200 shipment object | 400 invalid ID, non-draft or update failure, 404 missing | Replace editable draft values and costs |
| POST /api/shipments/{id}/finalize | No body, uses stored draft | 200 finalization envelope below | 400 invalid ID, already finalized, invalid draft or pricing failure, 404 missing, 500 finalization failure | Update costs and status on existing row |
| DELETE /api/shipments/{id} | No body | 200 `{success:true,message}` | 400 invalid ID, 404 missing, 500 deletion failure | Delete row |

The delete success message is `Shipment deleted successfully` for drafts or `Shipment cancelled successfully` for finalized records. Guarded requests can also return 401.

## List query and response

| Parameter | Supported values | Default |
| --- | --- | --- |
| status | draft, finalized, all | all |
| shipmentType | Domestic, IntraGulf, International, all | all |
| sortBy | createdAt, totalCost, status | createdAt |
| sortOrder | asc, desc | desc |
| page | Page number, starts at 1 | 1 |
| limit | Rows per page | 10 |

Example `GET /api/shipments?status=draft&shipmentType=Domestic&page=1&limit=10`. Success contains `{shipments: Shipment[], total: number, page: number, limit: number, totalPages: number}`. The count is scoped to the filters and account. A valid empty result is `{"shipments":[],"total":0,"page":1,"limit":10,"totalPages":0}`. The handler does not consistently validate query parameters before applying them.

## Nested request example

```json
{
  "from":{"name":"Sample Tester","phone":"0501234567","country":"Saudi Arabia","city":"Riyadh","street":"Example Street","postalCode":"12345"},
  "to":{"name":"Sample Receiver","phone":"01012345678","country":"Egypt","city":"Cairo","street":"","postalCode":"11511"},
  "package":{"weight":12,"length":20,"width":15,"height":10,"description":""},
  "service":{"type":"international_economy","shipmentType":"International","pickupMethod":"home"},
  "additional":{"signature":true,"liquid":false,"insurance":true,"packaging":false},
  "rates":{"base":67,"signature":5,"insurance":15,"packaging":0,"total":87}
}
```

Contacts and service fields are strings, parcel measurements and costs are numbers, and option flags are booleans. Weight is in kg and dimensions are in cm. `shipmentType` is derived from the countries if omitted. `pickupMethod` defaults to `home`. Missing text usually becomes an empty string, missing or nonnumeric measurements become zero, and omitted option flags default to false. Negative parcel values are rejected by the draft check. PUT is a replacement-style update, so send the complete draft to preserve existing data. Full booking checks apply on finalization. Errors from those checks use `{"error":"Validation failed","validationErrors":{"signatureRequired":"Signature is required when shipping to Egypt"}}` as an example. Existing-draft finalization also adds a message on validation failure. Pricing errors may include `details`.

## Flat request for POST /api/shipments

```json
{
  "senderName":"Sample Tester","senderPhone":"0501234567","senderCountry":"Saudi Arabia","senderCity":"Riyadh","senderStreet":"Example Street","senderPostalCode":"12345",
  "receiverName":"Sample Receiver","receiverPhone":"01012345678","receiverCountry":"Egypt","receiverCity":"Cairo","receiverStreet":"","receiverPostalCode":"11511",
  "weight":12,"length":20,"width":15,"height":10,"itemDescription":"",
  "serviceType":"international_economy","shipmentType":"International","pickupMethod":"home",
  "signatureRequired":true,"containsLiquid":false,"insurance":true,"packaging":false,
  "baseCost":67,"signatureCost":5,"insuranceCost":15,"packagingCost":0,"totalCost":87
}
```

This handler creates a draft and passes flat fields directly to persistence. It defaults omitted price components to zero. Use the complete flat body when exercising this route. It has no full booking validation step.

## Shipment and finalization responses

A shipment object contains the fields below. List items, ID detail, writes and finalization all use this object, sometimes within an envelope.

```json
{
  "id":42,"trackingNumber":"TR123456789","status":"finalized",
  "from":{"name":"Sample Tester","phone":"0501234567","country":"Saudi Arabia","city":"Riyadh","street":"Example Street","postalCode":"12345"},
  "to":{"name":"Sample Receiver","phone":"01012345678","country":"Egypt","city":"Cairo","street":"","postalCode":"11511"},
  "package":{"weight":12,"length":20,"width":15,"height":10,"description":""},
  "service":{"type":"international_economy","shipmentType":"International","pickupMethod":"home"},
  "options":{"signature":true,"liquid":false,"insurance":true,"packaging":false},
  "rate":{"base":67,"total":87,"signature":5,"insurance":15,"packaging":0,"liquid":0},
  "createdAt":"2026-11-18T12:00:00.000Z","updatedAt":"2026-11-18T12:01:00.000Z"
}
```

Finalization wraps the object in `{success:true,message:"Shipment finalized successfully",shipment,rateBreakdown}`. For the sample, `rateBreakdown` is `{"baseCost":67,"signatureCost":5,"insuranceCost":15,"packagingCost":0,"liquidCost":0}`. With liquid enabled, the finalization breakdown can show a $10 liquid charge while `shipment.rate.liquid` is still zero. The saved total includes the charge.

QA flow. Save a draft → read it → update it → finalize it → read it again. Verify the same ID and tracking number, current price, and final status. A second attempt to finalize the same record returns 400.

## Sources

- [src/routes/api/shipments/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/shipments/%2Bserver.ts)
- [src/routes/api/shipments/[id]/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/shipments/%5Bid%5D/%2Bserver.ts)
- [src/routes/api/shipments/[id]/finalize/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/shipments/%5Bid%5D/finalize/%2Bserver.ts)
- [src/routes/api/shipments/draft/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/shipments/draft/%2Bserver.ts)
- [src/routes/api/shipments/finalize/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/shipments/finalize/%2Bserver.ts)
