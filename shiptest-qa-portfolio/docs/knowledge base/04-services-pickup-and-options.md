# Services, pickup and options

Offer only services for the detected shipment type and eligible weight. Show availability, estimated delivery and price information. Clear a selection that becomes unavailable after a route or weight change. If no service is offered, tell the customer.

| Shipment type | Service | Max kg | Estimated business days |
| --- | --- | ---: | --- |
| Domestic | Domestic Standard | 50 | 2–3 |
| Domestic | Domestic Express | 30 | 1 |
| IntraGulf | Gulf Standard | 30 | 4–5 |
| IntraGulf | Gulf Express | 20 | 2 |
| International | International Economy | 25 | 8–10 |
| International | International Standard | 25 | 5–7 |

| Rule | Expected behavior |
| --- | --- |
| SVC-01 | Home pickup is the default. Postal-office drop-off is also available. |
| SVC-02 | Above 17 kg, require postal-office drop-off unless the origin is Iraq. At exactly 17 kg, home pickup remains available. |
| SVC-03 | All shipments to Egypt or Jordan require signature, including domestic bookings. Signature is selected and locked. It is optional for other destinations. |
| SVC-04 | Liquid handling, insurance and professional packaging are optional and incur fixed fees when selected. |

**Acceptance examples** · At 20 kg both Gulf services qualify. Above 20 kg, Gulf Express drops out. At 18 kg, an Iraqi origin can use home pickup and an Egyptian origin must use drop-off.

**Open decision** · Final pricing checks the selected service’s weight cap. Confirm that every finalization and quote must also verify that the service belongs to the route.

## Sources

Repository review at commit `447c72c`. Acceptance examples describe expected behavior from the review.

- [Story group 05](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/05-service-selection-stories.md)
- [Story group 06](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/06-additional-options-stories.md)
- [Story group 09](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/09-business-rules-stories.md)
