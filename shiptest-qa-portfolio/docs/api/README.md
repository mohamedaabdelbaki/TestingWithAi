# ShipTest Backend and API Knowledge Base

This reference describes the routes and database schema in [ship-app at commit 447c72c](https://github.com/mohamedaabdelbaki/ship-app/tree/447c72c4b4eca87f1b4906052eecb4fdd8bd6373). It covers all **19 API paths and 22 method/path combinations**. Examples use synthetic data. Responses are derived from the repository and have not been captured from a running deployment.

| Document | Use it to find |
| --- | --- |
| 01-authentication-api.md | Registration, login, logout, profile and session behavior |
| 02-shipments-api.md | Request formats, shipment responses, listing, draft editing, finalization and deletion |
| 03-rules-and-rates-api.md | Form rules, service eligibility and quote contracts |
| 04-assistant-api.md | Chat, documentation answers, search and health |
| 05-database-reference.md | Tables, fields, defaults, relationships and request-to-database changes |

## Use in Postman

1. Set `baseUrl` to your ShipTest environment, such as `http://localhost:3000`.
2. Register a test account or log in. Keep cookies enabled for the same host so Postman reuses `auth_session`.
3. Use `Content-Type: application/json` for JSON bodies and `Accept: application/json` for JSON responses. Leave the body empty for GET requests and when the reference says no body.
4. Use IDs returned by your own environment. A shipment’s numeric `id` and its `trackingNumber` serve different purposes.

Explicit errors generally have an `error` string. Shipment operations may add `validationErrors`, `message` or `details`. The shared sign-in guard raises a framework 401, so its JSON body may use `message` instead. Assert the status first.

## Keeping this reference current

When a route changes, update its method, inputs, response and errors in the matching document. When a write changes, update the database change matrix as well. Record the reviewed commit and label any examples verified against a running environment.
