# Shipment contacts

**Scope** · Sender and receiver details used on a booking.

| Rule | Expected behavior |
| --- | --- |
| CON-01 | A new shipment prefills the sender’s name, phone, country, city, street and postal code from the account. The sender summary is read-only. Editing or repeating a shipment loads the sender details carried by that record. |
| CON-02 | Customers enter the receiver’s name, phone, country, city and postal code. A street address is required when either contact’s own country is in the Gulf group. Street is optional for a non-Gulf shipment address. Registration separately requires a street. |
| CON-03 | Form rules specify at least two characters for name and city, 10–15 phone digits, 3–10 postal-code characters and at least five characters for a required Gulf street. The stories describe letters, spaces, hyphens and apostrophes for names. |

**Acceptance examples** · An Egyptian receiver may leave street blank. A Saudi receiver must provide it. Switching the receiver country from Egypt to Saudi Arabia makes street required.

**Open decision** · Align validation across registration, editing and finalization. Registration measures phone length in characters. The shipment form counts digits. Finalization checks the 10-digit minimum but omits the upper limit and some street, name and postal-code checks. Confirm which phone separators and name characters are allowed.

## Sources

Repository review at commit `447c72c`. Acceptance examples describe expected behavior from the review.

- [Story group 02](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/02-sender-information-stories.md)
- [Story group 03](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/03-receiver-information-stories.md)
- [Story group 09](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/09-business-rules-stories.md)
