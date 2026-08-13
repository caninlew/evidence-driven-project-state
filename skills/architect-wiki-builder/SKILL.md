---
name: architect-wiki-builder
description: Integrate a local LLM Wiki via its API as a retrieval-candidate layer, verify every claim against canonical Raw, and hand off verified evidence to architect-method-lens. Use when retrieving architect evidence, auditing LLM Wiki sources, running an evidence audit, or preparing a method-lens handoff. V0.2 no longer generates a second semantic wiki or knowledge graph, never uses /chat, and never imitates the architect.
---

# Architect Wiki Builder (V0.2)

## Role

Connect three layers and keep them strictly separated:

1. **canonical Raw** — the only authority layer. Read-only; files are never rewritten, renamed, moved, or deleted. Content hashes (SHA-256) and captured time are recorded.
2. **LLM Wiki** (local API, default `http://127.0.0.1:19828`) — machine-generated navigation, full-text search, and graph layer. Its pages are **RETRIEVAL CANDIDATES, never final evidence**.
3. **Agent workflow** — audits, retrieves via API, verifies against canonical Raw, registers evidence, judges hypotheses, and hands off to architect-method-lens.

Workflow: canonical Raw → LLM Wiki scans and generates navigation → API/MCP search candidates → agent verifies against canonical Raw → evidence registration → hypothesis judgement → architect-method-lens handoff.

## Boundary

- Do not generate a second set of people/projects/concepts wiki pages. Do not maintain a second knowledge graph.
- Do not feed agent-generated wiki pages into the LLM Wiki (creates a Raw → Agent Wiki → LLM Wiki duplicate semantic chain).
- Do not treat search hit counts as evidence counts. A retrieved page is a candidate, not proof.
- Do not call the LLM Wiki `/chat` endpoint.
- Do not simulate the architect's persona or answer in first person.
- Default API endpoint is `http://127.0.0.1:19828` only. Never open LAN access, never read, display, write, or log tokens.

## Evidence classes (keep)

- P1 architect's signed statement / direct interview answer
- P2 official project material from architect/studio/institution
- S1 independent scholarly or technical analysis
- S2 edited professional reporting or criticism
- U unresolved

Claim types stay separated: AUTHOR_STATEMENT / OFFICIAL_PROJECT_STATEMENT / PROJECT_OBSERVATION / EDITORIAL_CONTEXT / INTERVIEWER_CONTEXT / PROJECT_FACT (verified by independent material) / AGENT_INFERENCE. Interviewer questions are INTERVIEWER_CONTEXT and are never attributed to the architect. A project recalled or explained by the architect is AUTHOR_STATEMENT_ABOUT_PROJECT, not PROJECT_FACT.

Also keep: alias and duplicate audit (same-source duplicates are aliased, never counted twice), attribution split between individual / research studio / design institute / project team, canonical Raw traceability, hypothesis lifecycle (candidate → supported → contested → rejected), recurring-method upgrade gate, contradiction and open-question registers, and the architect-method-lens handoff contract in `references/method-lens-handoff.md`.

## API & security rules

- Only connect to `http://127.0.0.1:19828`.
- No LAN exposure, no auth changes, no tokens in any report, file, or log.
- If the API is unreachable: **degrade to Raw-only evidence audit** (canonical Raw + existing registers). Never rebuild a second wiki as a fallback.

## Operations

### llm-wiki-rescan

Call `POST /api/v1/projects/current/sources/rescan`. `changedTasks=[]` only means no new tasks were created this run — never interpret it as "no data" or "scan failed"; material may already be queued or registered. Record the response verbatim in the log.

### llm-wiki-search

Call `POST /api/v1/projects/current/search` with `topK` (10 default) and `includeContent: true`. Separate endpoint success from semantic hit quality:

- `STRONG_MATCH` — direct, on-topic hits with relevant content
- `WEAK_MATCH` — hits exist but are tangential or low score
- `PROCESSING_OR_NOT_INDEXED` — zero results or missing dedicated page; not a failure
- `API_ERROR` — endpoint failed

`RETRIEVED` alone never establishes evidence.

### llm-wiki-graph

Call `GET /api/v1/projects/current/graph?q=...&limit=...`. Use only for navigation and to raise verification questions. Never derive method conclusions from the graph.

### llm-wiki-source-audit

For each key claim, return to canonical Raw and register:

- LLM Wiki page path
- retrieval statement
- canonical Raw path
- Raw locator (line or section)
- canonical file SHA-256
- captured time
- claim type
- authority
- attribution
- VERIFIED / CONFLICT / UNVERIFIED
- whether it may enter method research

The LLM Wiki's `raw/sources` copies are indexing artifacts, not canonical Raw. Register `SOURCE_DRIFT` whenever path, SHA, or version differs between the copy and canonical Raw.

### llm-wiki-method-handoff

Only these entries may be handed to architect-method-lens:

- verified against canonical Raw
- status VERIFIED
- authority explicit
- attribution explicit
- no unresolved key conflict

A single P1 statement may at most form a hypothesis; it can never become a recurring method from one interview alone (see `references/method-lens-handoff.md`).

## Quality gates (all must pass before any handoff)

1. Interviewer examples were not mis-attributed to the architect.
2. Project-page "we" voice was not mistaken for the architect's personal words.
3. Authority is present on every registered claim.
4. LLM Wiki summaries were not passed off as Raw.
5. Weak matches were not written as hits.
6. Index copies were not treated as canonical.
7. No Raw → Agent Wiki → LLM Wiki duplicate semantic input.
8. Full project team attribution is retained.
9. No persona simulation.
10. No recurring method upgrade without cross-project verification.

Any failure returns `PARTIAL` with the exact repair task.

## Anonymous regression case: attribution drift

A generated concept page once converted a project example raised in an interview question into an example supposedly supplied by the interviewee. The canonical transcript showed that the interviewee answered only at the building-type level. Treat this as a regression case: interviewer examples remain `INTERVIEWER_CONTEXT`; verify speaker, wording, and locator against Raw before registering any attributed claim.

## Degradation

API down → Raw-only evidence audit. Missing/queued content → PROCESSING_OR_NOT_INDEXED, never "lost". No new research is started through the API without user instruction.

## References

- `references/vault-schema.md` — documents the frozen experimental-vault schema (historical baseline)
- `references/method-lens-handoff.md` — handoff contract (unchanged)
- `references/llm-wiki-api.md` — local LLM Wiki API endpoints and status semantics
