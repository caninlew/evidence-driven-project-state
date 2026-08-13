# Architect Research Vault Schema

Use this schema for `init` and schema audits. Keep the Vault local unless the user authorizes synchronization.

## Directory structure

```text
architect-vault/
├─ AGENTS.md
├─ index.md
├─ log.md
├─ raw/
│  ├─ public/
│  │  ├─ articles/
│  │  ├─ interviews/
│  │  ├─ project-pages/
│  │  ├─ books/
│  │  └─ media-notes/
│  └─ authorized-internal/
├─ wiki/
│  ├─ sources/
│  ├─ people/
│  ├─ studios/
│  ├─ projects/
│  ├─ concepts/
│  ├─ hypotheses/
│  ├─ contradictions/
│  └─ open-questions/
└─ exports/
   └─ method-lens/
```

`raw/` is immutable evidence. `wiki/` is Agent-maintained interpretation. `AGENTS.md` and templates are the Schema layer. `exports/` contains bounded handoffs, not new facts.

## Required source-page fields

```yaml
---
title: ""
type: source
source_id: ""
authority: P1 | P2 | S1 | S2 | U
source_kind: article | interview | lecture | book | official-project | critique | internal
authors: []
architect_attribution: direct | studio | team | third-party | unresolved
published: ""
captured: ""
url: ""
raw_path: ""
content_hash: ""
language: ""
access: public | authorized-internal | restricted
status: active | duplicate-alias | superseded | unresolved
aliases: []
tags: []
---
```

Include: concise summary, evidence excerpts as short paraphrases, direct-statement locator, related projects/concepts, contradictions, copyright/use note, and open questions.

## Required project-page fields

```yaml
---
title: ""
type: project
project_id: ""
architects: []
studio: ""
team: []
client: ""
location: ""
design_date: ""
completion_date: ""
status: proposed | competition | built | altered | unknown
sources: []
updated: ""
---
```

Separate official statements, observable project facts, independent interpretations, Agent observations, and authorship uncertainties.

## Required hypothesis-page fields

```yaml
---
title: ""
type: hypothesis
hypothesis_id: ""
status: candidate | supported | contested | rejected
supporting_sources: []
weakening_sources: []
projects_covered: []
updated: ""
---
```

A Wiki hypothesis is only a research lead. It is not a recurring method until validated by `architect-method-lens`.

## AGENTS.md minimum rules

1. Search existing Wiki pages before creating new ones.
2. Never modify or delete Raw evidence.
3. Require source references for factual claims.
4. Preserve conflicts, dates, and applicable scope.
5. Distinguish individual, studio, institution, and project-team authorship.
6. Mark Agent inference and hypothesis explicitly.
7. Update only affected pages, backlinks, index, and append-only log.
8. Stop for unclear authorization or disclosure status.
9. Do not imitate a living architect or speak in first person.
10. Export evidence rather than personality prompts.

## Naming

- Raw files: preserve Web Clipper filenames unless collisions occur.
- Source pages: `SRC-###_short-title.md`.
- Projects: `PRJ-###_project-name.md`.
- Hypotheses: `HYP-###_verb-led-claim.md`.
- Contradictions: `CON-###_topic.md`.
- Open questions: `OQ-###_question.md`.

