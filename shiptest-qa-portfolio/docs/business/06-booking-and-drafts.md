# Booking and drafts

**Customer journey** · Review sender → enter receiver → enter parcel → choose service and options → review quote → save draft or finalize.

| Rule | Expected behavior |
| --- | --- |
| BKG-01 | Complete valid receiver details before proceeding to parcel entry. Complete the parcel before choosing a service. A quote requires a service selection. |
| BKG-02 | Save Draft allows an incomplete booking. The draft can be reopened and edited. |
| BKG-03 | Finalization requires valid contacts, an eligible route and parcel, a service, a pickup method and mandatory options. Recalculate pricing. If checks fail, show the issues and keep an existing record as a draft. |
| BKG-04 | A customer can finalize a new booking directly or finalize an existing draft from its list or detail actions. Finalized records are read-only. |
| BKG-05 | Initial record creation assigns a unique tracking reference in the format TR plus nine digits. An existing draft keeps that reference when finalized. |

**Acceptance examples** · An incomplete draft can be saved. Attempting to finalize it prompts the customer to correct missing or invalid data. A valid draft finalized from its details changes status and retains its reference.

**Open decisions** · The edit form’s Finalize Shipment control currently saves the draft. Confirm the intended outcome for that control. The stories place options after service selection, while the current form enables options after package completion.

## Sources

Repository review at commit `447c72c`. Acceptance examples describe expected behavior from the review.

- [Story group 08](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/08-shipment-management-stories.md)
- [Story group 11](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/11-progressive-form-stories.md)
