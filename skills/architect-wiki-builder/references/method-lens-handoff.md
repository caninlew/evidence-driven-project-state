# Handoff to Architect Method Lens

Export one bounded evidence bundle per architect and research question.

## Required files

```text
exports/method-lens/
├─ profile-manifest.md
├─ source-register.md
├─ evidence-register.md
├─ project-register.md
├─ contradiction-register.md
└─ open-questions.md
```

## Profile manifest

Record:

- target architect and verified public role;
- research question and time boundary;
- source counts by P1/P2/S1/S2/U;
- public versus authorized-internal scope;
- project coverage;
- unresolved authorship and copyright restrictions;
- explicit statement that no method conclusion is exported.

## Evidence register

Use one row per evidence item:

| Evidence ID | Evidence class | Claim type | Source ID | Raw locator | Project | Short paraphrase | Supports | Weakens | Team attribution | Confidence | Restrictions |
|---|---|---|---|---|---|---|---|---|---|---|---|

`Claim type` must be one of:

- `AUTHOR_STATEMENT`
- `OFFICIAL_PROJECT_STATEMENT`
- `PROJECT_OBSERVATION`
- `INDEPENDENT_INTERPRETATION`
- `AGENT_INFERENCE`

Do not use Wiki prose as the terminal citation. Retain the Raw locator.

## Project register

Include project identity, dates, status, authorship/team, source coverage, tested hypothesis IDs, possible counterexample role, and known gaps.

## Contradictions and gaps

Export disagreements without resolving them. Include title/role drift, date conflicts, duplicate publication, project authorship ambiguity, built-versus-competition differences, and missing counterexamples.

## Acceptance gate

The handoff is ready only when:

- direct statements can be traced to P1;
- project claims can be traced to P2 or clearly labeled observation;
- independent interpretations remain separate;
- team authorship is visible;
- weakening evidence and gaps are included;
- no line claims to reproduce the architect's persona or likely decision.

Otherwise mark the export `PARTIAL` and list repair tasks.

