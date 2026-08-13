# Contributing

Thanks for your interest in improving this project.

## Contribution Principles

This repository is intentionally opinionated. Contributions should strengthen:

- evidence traceability
- state separation
- conflict visibility
- bounded task discipline
- human approval boundaries

Please avoid contributions that turn the project into:

- a generic todo list
- a black-box automation layer
- a domain-specific style generator

## Good Contribution Types

- improve core schemas
- improve examples
- add domain-neutral documentation
- add carefully scoped domain packs
- clarify adoption boundaries
- improve release hygiene

## Skill contract

Every new or materially changed Skill must answer six questions:

- **WHEN** — what user intent or project condition triggers it?
- **IN** — what inputs, authority, and boundaries are required?
- **DO** — what ordered actions does it perform?
- **STOP** — when must it refuse, pause, or remain provisional?
- **OUT** — what durable work products does it create?
- **QA** — how can a reviewer verify that it did not overreach?

A successful installation is not method validation. Add or update a fixed-input regression case under `evals/` whenever a failure changes a rule. Preserve the failed behavior as an anonymous case, record the expected assertions, and do not publish confidential source material.
## Before Opening a PR

Please make sure:

1. the change has a clear problem statement
2. the change preserves source-versus-fact discipline
3. the change does not silently broaden the repository scope
4. any new domain pack includes examples and explicit boundaries
5. named people, practices, clients, and private project residue have been removed or explicitly authorized
6. Skill frontmatter uses only portable `name` and `description` fields
7. a changed behavioral rule has a corresponding regression case

## PR Expectations

In your pull request, include:

- what problem this change solves
- what files are affected
- whether the change is core or domain-specific
- what assumptions remain unresolved

## Scope Guidance

When in doubt:

- keep core rules general
- keep domain rules explicit
- keep examples concrete
- keep claims modest and verifiable
