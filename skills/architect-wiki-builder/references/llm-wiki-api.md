# LLM Wiki Local API Reference (V0.2)

Default endpoint: `http://127.0.0.1:19828` — local only. No LAN, no auth changes, no tokens in any output.

## Endpoints

| Endpoint | Method | Purpose | Notes |
|---|---|---|---|
| `/api/v1/health` | GET | status check | `ok:true` + version |
| `/api/v1/projects` | GET | project list | record current project id/name/path |
| `/api/v1/projects/current/files?root=all&recursive=true&maxFiles=10000` | GET | file tree | returns directory tree with `children`; walk recursively; note `truncated` |
| `/api/v1/projects/current/sources/rescan` | POST | safe rescan | `changedTasks=[]` ⇒ no new tasks this run, not "no data" |
| `/api/v1/projects/current/search` | POST | semantic search | body: `{"query": "...", "topK": 10, "includeContent": true}` |
| `/api/v1/projects/current/graph?q=...&limit=100` | GET | entity graph | navigation only; no method conclusions |
| `/api/v1/projects/current/files/content?path=...` | GET | read one page | path is URL-encoded; verify path exists |

Never call `/chat`.

## Search status semantics

- `STRONG_MATCH` — direct on-topic hits
- `WEAK_MATCH` — tangential or low-score hits
- `PROCESSING_OR_NOT_INDEXED` — zero results or no dedicated page; queued or not yet indexed, not a failure
- `API_ERROR` — endpoint failed

`RETRIEVED` alone does not establish evidence.

## Source scope semantics

- LLM Wiki `raw/sources/...` copies are **indexing artifacts**, not canonical Raw.
- Register `SOURCE_DRIFT` when path, SHA-256, or version differs from canonical Raw.
- If agent-generated wiki paths appear in LLM Wiki sources fields → register `DUPLICATE_SEMANTIC_INPUT_CANDIDATE` (Raw → Agent Wiki → LLM Wiki chain); do not delete anything; propose alias/freeze actions only.

## Degradation

API unreachable → Raw-only evidence audit against canonical Raw and existing registers. Never rebuild a second wiki as fallback.
