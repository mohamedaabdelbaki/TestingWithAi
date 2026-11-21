# Assistant API

Chat, ask and search require the session cookie and return 503 if assistant configuration is unavailable. Health is public. None of these endpoints creates a shipment, writes the form, or persists conversation history.

| Method and path | Request | 200 response | Other responses |
| --- | --- | --- | --- |
| POST /api/agent/chat | Required `message` string, nonblank and max 4000 characters. Optional `history` and `formContext`. | `{reply,toolCalls,proposal,model,latencyMs}` | 400 invalid message, 401 unauthenticated, 503 missing configuration, 500 failure |
| POST /api/assistant/ask | Required nonblank `question`, optional integer `k` | `{answer,sources,model,latencyMs}` | 400 invalid question, 401 unauthenticated, 503 missing configuration, 500 failure |
| POST /api/assistant/search | Required nonblank `query`, optional integer `k`, optional numeric `minScore` | `{query,k,minScore,indexedChunks,results}` | 400 invalid query, 401 unauthenticated, 503 missing configuration, 500 failure |
| GET /api/agent/health | No body | `{ok,apiKeyConfigured,model,embeddingModel,indexedChunks,hints}` | A missing key or empty index is reported in a 200 body with `ok:false` |

## Chat

```json
{"message":"What is missing from my shipment form?","history":[{"role":"user","content":"I am preparing a new shipment."}],"formContext":null}
```

History entries use `role` (`user` or `assistant`) and string `content`. The handler keeps the most recent ten valid entries. Optional form context is current client display data. Reply and model are strings. Latency is milliseconds. Each tool entry has `name,args` and optional string `result`. A proposal is null or `{values,violations}`. The user applies proposed values in the form separately.

## Documentation and health

- Ask example `{"question":"When is signature required?","k":4}`. Each source is `{n,source,heading,score}`. With no retrieved passages the response has an explanatory answer, empty sources and an empty model string.
- Search example `{"query":"home pickup weight","k":4,"minScore":0}`. Each result is `{id,source,heading,content,score}`. Search retrieves passages without generating a chat answer. Empty results are valid.
- Both documentation routes default `k` to 4 and clamp integer values to 1–10. Search defaults `minScore` to 0.
- Health reports configured model names and a documentation chunk count. It makes no external model call. `hints` is an array of messages, and `ok` requires both a configured key and a nonempty index.

For QA, check the stable response fields, status, citations and account scope. Exact generated wording can vary.

## Sources

- [src/routes/api/agent/chat/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/agent/chat/%2Bserver.ts)
- [src/routes/api/agent/health/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/agent/health/%2Bserver.ts)
- [src/routes/api/assistant/ask/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/assistant/ask/%2Bserver.ts)
- [src/routes/api/assistant/search/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/assistant/search/%2Bserver.ts)
