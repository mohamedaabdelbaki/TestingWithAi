# Rule-driven form fields

Use stable IDs for fields rendered by DynamicCard. Rules APIs can override defaults for route, country, weight and service. See [booking behavior](frontend-map.md).

## Sender Information

[Rule source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/rules/sender-card.json)

| Field key | Label or options | Render type | Default validation or state |
| --- | --- | --- | --- |
| `senderName` | Full Name | text | {"required": true, "validation": {"required": true, "minLength": 2, "errorMessage": "Name must be at least 2 characters"}} |
| `senderPhone` | Phone Number | text | {"required": true, "validation": {"required": true, "minLength": 10, "maxLength": 15, "errorMessage": "Phone number must be between 10-15 digits"}} |
| `senderCountry` | Country | select | {"required": true, "validation": {"required": true, "errorMessage": "Please select a country"}} |
| `senderCity` | City | text | {"required": true, "validation": {"required": true, "minLength": 2, "errorMessage": "City is required"}} |
| `senderStreet` | Street Address | text | {"required": false, "validation": {"required": false, "minLength": 5, "errorMessage": "Street address is required"}} |
| `senderPostalCode` | Postal Code | text | {"required": true, "validation": {"required": true, "minLength": 3, "maxLength": 10, "errorMessage": "Postal code must be between 3-10 characters"}} |

## Receiver Information

[Rule source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/rules/receiver-card.json)

| Field key | Label or options | Render type | Default validation or state |
| --- | --- | --- | --- |
| `receiverName` | Full Name | text | {"required": true, "validation": {"required": true, "minLength": 2, "errorMessage": "Name must be at least 2 characters"}} |
| `receiverPhone` | Phone Number | text | {"required": true, "validation": {"required": true, "minLength": 10, "maxLength": 15, "errorMessage": "Phone number must be between 10-15 digits"}} |
| `receiverCountry` | Country | select | {"required": true, "validation": {"required": true, "errorMessage": "Please select a country"}} |
| `receiverCity` | City | text | {"required": true, "validation": {"required": true, "minLength": 2, "errorMessage": "City is required"}} |
| `receiverStreet` | Street Address | text | {"required": false, "validation": {"required": false, "minLength": 5, "errorMessage": "Street address is required"}} |
| `receiverPostalCode` | Postal Code | text | {"required": true, "validation": {"required": true, "minLength": 3, "maxLength": 10, "errorMessage": "Postal code must be between 3-10 characters"}} |

## Package Information

[Rule source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/rules/package-card.json)

| Field key | Label or options | Render type | Default validation or state |
| --- | --- | --- | --- |
| `weight` | Weight (kg) | number | {"required": true, "validation": {"required": true, "min": 0.1, "errorMessage": "Weight must be greater than 0"}} |
| `length` | Length (cm) | number | {"required": true, "validation": {"required": true, "min": 1, "max": 200, "errorMessage": "Length must be between 1-200 cm"}} |
| `width` | Width (cm) | number | {"required": true, "validation": {"required": true, "min": 1, "max": 200, "errorMessage": "Width must be between 1-200 cm"}} |
| `height` | Height (cm) | number | {"required": true, "validation": {"required": true, "min": 1, "max": 200, "errorMessage": "Height must be between 1-200 cm"}} |
| `itemDescription` | Item Description | text | {"required": false, "visible": false, "validation": {"required": false, "minLength": 5, "maxLength": 200, "errorMessage": "Item description is required when shipping from outside the Gulf into a Gulf country"}} |

## Additional Options

[Rule source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/rules/additional-options.json)

| Field key | Label or options | Render type | Default validation or state |
| --- | --- | --- | --- |
| `signatureRequired` | Signature Required | checkbox | {"checked": false, "disabled": false} |
| `containsLiquid` | Contains Liquid | checkbox | {"checked": false, "disabled": false} |
| `insurance` | Insurance ($15.00) | checkbox | {"checked": false, "disabled": false} |
| `packaging` | Professional Packaging ($8.00) | checkbox | {"checked": false, "disabled": false} |
| `pickupMethod` | Pickup Method · Home Pickup (home), Drop Off at Postal Office (postal_office) | radio | {"defaultValue": "home"} |

## Service Information

[Rule source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/rules/service-card.json)

| Field key | Label or options | Render type | Default validation or state |
| --- | --- | --- | --- |
| Service options | Radio cards from the service catalog by route and weight | radio | See the linked JSON and service rules endpoint |

## Control lookup

- Receiver and package fields use the field key as the DOM ID. Sender fields are read-only display values. Additional Options labels and pickup choices come from the rule response. Service radios are rendered per service. See the component inventory for input attributes.
