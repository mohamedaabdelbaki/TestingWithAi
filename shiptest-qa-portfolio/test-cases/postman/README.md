# ShipTest Postman API tests

1. Start ShipTest locally using the app repository's setup instructions.
2. Import the [collection](ship-app.postman_collection.json) and [environment](shiptest-local.postman_environment.json) into the Postman desktop app.
3. Select **ShipTest Local** and confirm that `baseUrl` matches the local server.
4. Run the full collection in order with the cookie jar enabled.

The 57 requests cover authentication, shipment rules, pricing, shipment lifecycle, and the assistant. Postman carries the `auth_session` JWT in its cookie jar. The collection passes the quote, draft ID, and tracking number between requests and checks that logout ends the session.

Use a disposable local database. The run creates a QA account that remains in the database and attempts to clean up the shipments it creates. Assistant requests check availability using the health endpoint and may use the configured provider.

The revised collection has been checked for script syntax and request order. Full live execution is pending.
