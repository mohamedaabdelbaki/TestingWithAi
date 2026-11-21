# Accounts and access

**Scope** · Registration, sign-in, sign-out and shipment ownership.

| Rule | Expected behavior |
| --- | --- |
| ACC-01 | Registration requires a valid, unique email, a password of at least six characters, full name, phone, country, city, street and postal code. Email uniqueness is case-insensitive. |
| ACC-02 | Successful registration signs the customer in. Returning customers can sign in with their email and password, and sign out when finished. Sessions are configured for 30 days. |
| ACC-03 | Shipment booking, history and personal assistant lookups require a signed-in account. Each customer can access and manage only their own shipment records. |
| ACC-04 | The signed-in account supplies sender details for new bookings. The customer sees their name and email while signed in. |

**Acceptance examples** · Registering the same email with different capitalization is rejected. A signed-out customer is directed to sign in when opening My Shipments. Another customer’s shipment reference reveals no shipment details.

**Open scope** · Profile editing, account administration and password recovery have no defined workflow in this review.

## Sources

Repository review at commit `447c72c`. Acceptance examples describe expected behavior from the review.

- [Story group 01](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/01-authentication-stories.md)
- [Story group 10](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/stories/10-security-stories.md)
