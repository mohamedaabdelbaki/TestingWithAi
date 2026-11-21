# Shipping assistants

| Rule | Expected behavior |
| --- | --- |
| AST-01 | The optional Shipping Assistant is available when creating, editing or repeating a booking. It can look up the signed-in customer’s own shipments and explain when there are no results. |
| AST-02 | It can check route and package eligibility, quote prices using the app’s pricing rules, and explain policy with cited documentation. Quotes should match booking rules and mandatory charges. |
| AST-03 | The assistant can read current form values and point out missing details or errors. It can propose changes to receiver, package, pickup and options. The customer reviews the proposal and explicitly applies it. Sender details stay protected. |
| AST-04 | The dedicated documentation assistant offers sample questions and source-based answers. Assistants acknowledge missing information and avoid inventing prices, tracking references or policy. The core booking journey remains available if assistant features are unavailable. |

**Acceptance examples** · A request about another account’s shipment reveals no details. A proposed receiver stays out of the form until the customer applies it. An undocumented refund question is reported as undocumented.

**Open decision** · Confirm that an assistant quote described as exact applies mandatory signature, pickup restrictions and route eligibility consistently with finalization.

## Sources

Repository review at commit `447c72c`. Acceptance examples describe expected behavior from the review.

- [Story group 12](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/12-ai-assistant-stories.md)
