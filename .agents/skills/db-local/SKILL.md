---
name: db-local
description: Answer questions about actual ShipTest data in the local SQLite dev.db using read-only SQL. Use for /db-local requests, checking shipment or user IDs, tracking numbers, saved prices, and comparing API responses with database records.
---

# Query the local ShipTest database

Accept a plain-language question or a read-only SQL query. Examples: `/db-local does shipment 7 exist?` and `/db-local compare shipment 7 with this API response`. Accept an optional database attachment or path.

1. Resolve the database in this order: an explicit path or attachment, the current ShipTest checkout's `prisma/dev.db` (including a reachable `~/Downloads/ship-app/prisma/dev.db` on Windows), then the uploaded `dev.db` in the active workspace. If no local copy is available in ChatGPT, look for the exact filename in the project's Library and materialize the matching SQLite file. Ask for a path or upload if the file is missing or multiple candidates are ambiguous. Never use an unrelated database. Say whether the result is from the local file or an uploaded snapshot.
2. Inspect the actual schema before assuming table or column names. Prefer Python's standard `sqlite3` module. Open the resolved path with `sqlite3.connect(Path(path).resolve().as_uri() + '?mode=ro', uri=True)` and set `PRAGMA query_only = ON`. If Python is unavailable, use an installed SQLite client in read-only mode. Run SELECT queries and schema inspection only. Parameterize values in generated queries. Never execute write statements or load extensions.
3. Select only relevant columns and bound lists unless the user asks for all matches. Omit password hashes and session secrets. When an ID is ambiguous, check relevant tables and label the matches. For API comparisons, distinguish stored values from calculated response fields and explain missing columns without inferring a stored value.
4. Answer in plain language with a short Markdown table when showing several fields or records. State the table queried, report when a match is absent, and identify the file used. Avoid implying that a snapshot reflects later local changes.
