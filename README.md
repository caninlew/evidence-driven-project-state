# Evidence-Driven Project State

An evidence-driven, state-based framework for turning complex, multi-source work into traceable project state, bounded action, and reviewable handoffs.

It is architecture-first today. The governance method is designed to generalize to consulting, product, research, and other knowledge-intensive work, but cross-domain parity still needs published evaluation.

Chinese version: [README.zh-CN.md](README.zh-CN.md)

> Independent open-source work by an individual affiliated with TJAD AI专班 / 量子城市专班. The affiliation is biographical only; this is not an official TJAD or working-group publication or endorsement. See [AUTHORS.md](AUTHORS.md).

## Why this exists

Most project systems track tasks but lose the evidence behind them. This repository adds a controlled state layer between raw material and execution:

- where each consequential claim came from;
- which authority domain it belongs to;
- whether it is issued, confirmed, provisional, contested, or Agent-generated;
- which metric definitions are compatible;
- which conflicts and questions remain open;
- which recommendations were never approved;
- what bounded work may safely proceed next.

## Core thesis

The hard part of ambiguous project work is often context governance, not content generation. Separate source observations, current facts, stakeholder statements, decisions, derivations, assumptions, proposals, open questions, and tasks before asking an Agent to advance the work.

## What is included

The architecture domain pack currently contains:

- `architect-project-state` — evidence, authority, metrics, change, and bounded tasks;
- `architect-method-lens` — evidence-backed method hypotheses and counterexamples, without persona or style imitation;
- `design-test-framework-rounds` — comparable, falsifiable design tests rather than premature schemes;
- `architect-wiki-builder` — optional LLM Wiki retrieval adapter with canonical-Raw verification.

```text
raw sources
  -> controlled project state
  -> evidence-backed method lens
  -> falsifiable test frameworks
  -> human decision

failure
  -> human correction
  -> Skill revision
  -> fixed-input regression
  -> next release
```

The second loop is what turns a one-off conversation into reusable, reviewable experience.

## Compatibility

These Skills follow the open Agent Skills folder pattern and use portable `name` + `description` frontmatter.

| Host | Current position |
|---|---|
| Hermes Agent | Primary tested environment for the originating workflow |
| OpenClaw | Primary compatibility target; runtime parity validation is ongoing |
| Other Agent Skills hosts | Format target only until host-specific smoke tests pass |

See [Installation](docs/INSTALLATION.md). Compatibility does not imply identical tools, permissions, refresh behavior, or outputs.

## Who it is for

Best fit: architecture and urban design teams, evidence-heavy consulting, ambiguous product discovery, research programs, and multi-stakeholder projects with frequent revisions.

Not a fit: trivial tasks, teams needing only a Kanban board, or workflows that expect an Agent to decide unresolved authority conflicts autonomously.

## Evidence discipline

1. Register before interpreting.
2. Judge authority by domain, source status, and attribution—not filename or a single global rank.
3. Keep incompatible metric definitions separate.
4. Preserve conflict instead of flattening it.
5. Do not inherit Agent proposals as project facts.
6. Keep named-person methods evidence-backed and never simulate a personality.
7. Preserve failed baselines and test Skill changes against fixed cases.
8. Keep professional judgment, statutory conclusions, client commitments, and authorship with identified humans.

## Start here

- [Installation](docs/INSTALLATION.md)
- [Quickstart](docs/QUICKSTART.md)
- [Architecture flow](docs/ARCHITECTURE_FLOW.md)
- [Adoption model](docs/ADOPTION_MODEL.md)
- [Contributing](CONTRIBUTING.md)
- [Authors and affiliation](AUTHORS.md)
- [Security](SECURITY.md)
- [Evaluation cases](evals/README.md)
- [Research status](RESEARCH_STATUS.md)
- [Reproducibility](REPRODUCIBILITY.md)
- [Data availability](DATA_AVAILABILITY.md)
- [Provenance](PROVENANCE.md)
- [Academic release policy](ACADEMIC_RELEASE_POLICY.md)
- [Public release gate](docs/PUBLIC_RELEASE_GATE.md)

## Repository structure

```text
.
├─ docs/
├─ evals/
├─ examples/
└─ skills/
   ├─ architect-project-state/
   ├─ architect-method-lens/
   ├─ design-test-framework-rounds/
   └─ architect-wiki-builder/
```

Directory names inside a user's project are recommendations, not protocol requirements. The real boundary is: one explicit project root, task-relevant sources, traceable state, and clear write authority.

## Status

**Public alpha / architecture-first.** The workflow grew through repeated real-task corrections and forward tests in Hermes Agent. The repository now includes de-identified Skills, installation guidance, CI checks, and machine-readable smoke cases. It does not yet claim broad host certification or equivalent performance outside architecture.

This is a research software artifact, not a peer-reviewed result or preprint. The included cases are development regressions, not a held-out benchmark. See [RESEARCH_STATUS.md](RESEARCH_STATUS.md).

## Citation

Use the exact versioned release in research or derivative work. A `CITATION.cff.template` is provided, but the active `CITATION.cff` must not be created until the publishing individual's identity, ORCID if used, and final repository URL are confirmed. See the [public release gate](docs/PUBLIC_RELEASE_GATE.md).

## License

MIT. See [LICENSE](LICENSE).
