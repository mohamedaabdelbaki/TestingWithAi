# Route and parcel eligibility

The Gulf group comprises Saudi Arabia, United Arab Emirates, Kuwait, Bahrain, Qatar and Oman. The other supported countries are Egypt, Jordan, Lebanon and Iraq.

| Rule | Condition | Outcome |
| --- | --- | --- |
| RTE-01 | Origin and destination are the same country | Domestic, maximum 50 kg |
| RTE-02 | Two different Gulf countries | IntraGulf, maximum 30 kg |
| RTE-03 | Any other country pair | International, maximum 25 kg, subject to route restrictions |
| RTE-04 | Origin is in the Gulf and destination is Iraq | Booking is blocked |
| RTE-05 | Origin is outside the Gulf and destination is in the Gulf | Item description appears and is required, with a form range of 5–200 characters |
| RTE-06 | Any eligible shipment | Enter weight of at least 0.1 kg and length, width and height of 1–200 cm each. Maxima are inclusive. Service-specific caps can be lower. |

**Acceptance examples** · Qatar → Qatar is Domestic. Saudi Arabia → Iraq is blocked at every weight. Iraq → Saudi Arabia is International and requires a description. An International parcel at exactly 25 kg meets the route weight cap. A 200 cm dimension meets the form limit.

**Open decision** · Finalization accepts positive weights below 0.1 kg and dimensions below 1 cm, and omits the description maximum. Confirm one set of parcel limits for all booking paths.

## Sources

Repository review at commit `447c72c`. Acceptance examples describe expected behavior from the review.

- [Story group 03](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/03-receiver-information-stories.md)
- [Story group 04](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/04-package-information-stories.md)
- [Story group 09](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/09-business-rules-stories.md)
