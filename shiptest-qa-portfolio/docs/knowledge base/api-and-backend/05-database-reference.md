# Database reference and update behavior

ShipTest uses a SQLite database with a Prisma schema and a configured `DATABASE_URL`. This describes the repository’s schema and write paths. It contains no live database records. Types below are Prisma field types.

## User

| Fields | Type and constraints |
| --- | --- |
| id | Int primary key, auto-increment |
| email | String, unique and indexed, stored lowercase by registration |
| password | String, bcrypt hash, omitted from public user objects |
| fullName, phone, country, city, street, postalCode | Required String fields used to prefill sender data |
| createdAt, updatedAt | DateTime. `createdAt` defaults to now, `updatedAt` is managed on writes |
| shipments | One-to-many relation to Shipment |

## Shipment

| Fields | Type and constraints |
| --- | --- |
| id | Int primary key, auto-increment |
| trackingNumber | String, unique and indexed. Generated as TR + nine digits when the record is created |
| userId, user | Required Int foreign key and relation to User. Indexed. Deleting a User cascades to their shipments |
| senderName, senderStreet, senderCity, senderPostalCode, senderCountry, senderPhone | Required String fields. Stored sender snapshot |
| receiverName, receiverStreet, receiverCity, receiverPostalCode, receiverCountry, receiverPhone | Required String fields. Stored receiver snapshot |
| weight, length, width, height | Float. Weight in kg, dimensions in cm |
| contentDescription | String, defaults to empty |
| shipmentType | String, defaults to Domestic |
| pickupMethod | String, defaults to home |
| serviceType | Required String. Stores the selected service ID |
| signatureRequired, containsLiquid, insurance, packaging | Boolean, each defaults to false |
| price | Required Float. Write paths set it to the same value as totalCost |
| baseCost, insuranceCost, signatureCost, packagingCost, totalCost | Float, each defaults to zero. Base cost includes pickup. No separate liquid-cost column |
| isDraft, status | Boolean defaults to false and String defaults to Pending at schema level. API writes explicitly use `true/draft` and `false/finalized`. Status is indexed |
| createdAt, updatedAt | DateTime. Creation defaults to now and is indexed. Updated timestamp is managed on writes |
| estimatedDelivery, actualDelivery | Nullable DateTime. The reviewed shipment API does not populate these fields |

## DocChunk

| Fields | Type and constraints |
| --- | --- |
| id | Int primary key, auto-increment |
| source | Indexed String for the source document path |
| heading, content | String for the nearest heading and the passage |
| embedding | String containing a JSON array of floats |
| createdAt | DateTime, defaults to now |

DocChunk has no relationship to User or Shipment. The documentation ingestion command rebuilds the dataset by deleting previous chunks and inserting the new set. A running server caches retrieved chunks, so restart it or reset its retrieval cache after rebuilding.

## Which requests update data

| Operation | Write behavior | Check afterward |
| --- | --- | --- |
| Register | Inserts User with normalized email, password hash and contact data | User exists and no password is returned |
| Login, logout, me | Session cookie changes on login/logout. No user row updates | Account data and timestamps are unchanged |
| Create draft through either POST route | Inserts a Shipment under the signed-in user with a new reference, draft flags, supplied values and optional prices | Detail returns the new ID, reference and draft status |
| Update draft with PUT | Replaces shipment contacts, parcel, service, flags and costs. Keeps owner, ID, reference and createdAt. Updates updatedAt | Compare before and after for the same ID. Omitted fields can reset |
| Finalize new booking | Calculates costs, inserts draft row and then marks it finalized | New ID and reference, finalized status, authoritative costs |
| Finalize existing draft | Validates stored values, recalculates costs and then sets finalized status and clears isDraft | Same ID and reference, refreshed costs, advanced updatedAt |
| Delete or cancel shipment | Deletes the existing row | Subsequent detail returns 404 and list excludes it |
| Quote and rules | No database writes | Request produces a quote or rule metadata only |
| Assistant requests | Read documentation chunks or owned shipments as required. No booking or index write | Shipment data stays unchanged pending explicit user action |
| Rebuild documentation index | Replaces DocChunk rows outside the HTTP API | Health and search report the rebuilt index after cache refresh |

The finalization operations perform separate writes for saving values and changing status. If a later write fails, inspect the shipment’s persisted state before retrying. The reviewed API does not expose user update/delete, delivery-event updates, or documentation ingestion as HTTP endpoints.

## Sources

- [prisma/schema.prisma](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/prisma/schema.prisma)
- [scripts/ingest.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/scripts/ingest.ts)
- [src/lib/server/ai/retriever.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/server/ai/retriever.ts)
- [src/lib/server/repositories/shipment.repository.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/server/repositories/shipment.repository.ts)
- [src/lib/server/repositories/user.repository.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/server/repositories/user.repository.ts)
