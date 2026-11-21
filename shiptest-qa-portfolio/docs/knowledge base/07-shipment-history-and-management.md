# Shipment history and management

| Rule | Expected behavior |
| --- | --- |
| HIS-01 | My Shipments shows owned records with reference, origin and destination, weight, status, price and actions. Current ordering is newest first. Customers can filter by status and shipment type. |
| HIS-02 | Shipment details show contacts, parcel, service, options and rate. Drafts can be resumed or finalized. |
| HIS-03 | Repeat opens a new booking prefilled from a finalized shipment. Saving the new booking creates a separate record and reference. |
| HIS-04 | Ask for confirmation before removal. Draft removal is presented as deletion. Finalized shipment removal is presented as cancellation. Both remove the record. |

**Acceptance examples** · Filtering to Draft shows only draft rows in the customer’s account. Cancelling the confirmation leaves the record available. Repeating a finalized shipment and saving a new draft keeps both records.

**Open decisions** · The stories describe adjustable sorting and pagination. The current page loads up to 100 matching records and computes displayed counts from that set. Confirm pagination, sorting and whether summary counts cover the whole account. Confirm cancellation eligibility, history retention and refund policy. The reviewed workflow ends at booking finalization and defines no carrier handoff, live delivery tracking, payment or returns.

## Sources

Repository review at commit `447c72c`. Acceptance examples describe expected behavior from the review.

- [Story group 08](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/08-shipment-management-stories.md)
