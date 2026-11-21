# Pricing and quotes

**Total in USD** = service starting price + (weight × per-kg rate) + origin pickup or drop-off fee + applicable option charges. The base line combines the service and pickup charges. Display totals to two decimal places.

| Service | Starting price | Per kg |
| --- | ---: | ---: |
| Domestic Standard | $15.00 | $0.50 |
| Domestic Express | $30.00 | $1.00 |
| Gulf Standard | $25.00 | $1.50 |
| Gulf Express | $45.00 | $2.50 |
| International Economy | $35.00 | $2.00 |
| International Standard | $50.00 | $3.00 |

| Origin | Home pickup | Postal-office drop-off |
| --- | ---: | ---: |
| Saudi Arabia | $8.00 | $3.00 |
| United Arab Emirates | $10.00 | $3.00 |
| Kuwait | $7.00 | $2.50 |
| Bahrain | $6.00 | $2.00 |
| Qatar | $8.00 | $3.00 |
| Oman | $7.00 | $2.50 |
| Egypt | $15.00 | $5.00 |
| Jordan | $12.00 | $4.00 |
| Lebanon | $12.00 | $4.00 |
| Iraq | $18.00 | $6.00 |

| Option | Charge |
| --- | ---: |
| Signature | $5.00 |
| Liquid handling | $10.00 |
| Insurance | $15.00 |
| Professional packaging | $8.00 |

The preview updates with service, weight, pickup and options. Finalization recalculates the total using current rates. A fallback of $20 home pickup or $8 drop-off exists in pricing and does not extend the supported-country list.

**Acceptance example** · Saudi Arabia → Egypt, 12 kg, International Economy, home pickup and insurance costs **$87.00**. That is $35 + $24 weight charge + $8 pickup + $15 insurance + $5 mandatory signature.

**Open decisions** · A documented assistant example quotes $82 because it omits mandatory signature. The saved price includes liquid handling, but the separate fee in history is reported as zero. A training banner advertises 20% off express shipping and the rate rules apply no discount. Confirm the expected quote, saved breakdown and promotion policy.

## Sources

Repository review at commit `447c72c`. Acceptance examples describe expected behavior from the review.

- [Story group 07](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/07-pricing-and-rates-stories.md)
- [Story group 12](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/12-ai-assistant-stories.md)
