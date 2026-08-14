# Changelog

All notable changes to this documentation-and-skill repository are recorded here.

## [Unreleased]

### Added

- research status, provenance, reproducibility, data-availability, rights, and academic-release boundaries;
- a non-active citation template and a hard public-release checklist;
- repository checks for citation placeholders, local absolute paths, private research filenames, and conflicting Zenodo metadata.
- Zenodo DOI metadata and a repository citation badge.

### Changed

- archival attribution now requires a stable individual public identity rather than optional anonymous release wording;
- public fixtures are explicitly classified as development regressions rather than a held-out benchmark.

## [0.1.0-alpha.1] - 2026-08-14

### Changed

- synchronized the public author identity, ORCID, and release metadata;
- issued an archival patch release after enabling the repository in Zenodo;
- made no changes to Skill methods, schemas, or evaluation cases.
## [0.1.0-alpha] - 2026-08-14

### Added

- architecture-first public-alpha framing;
- English and Chinese READMEs;
- MIT license, contribution, conduct, security, issue, and pull-request scaffolding;
- installation guidance for Hermes Agent, OpenClaw, and generic Agent Skills hosts;
- architecture domain pack:
  - `architect-project-state`;
  - `architect-method-lens`;
  - `design-test-framework-rounds`;
  - `architect-wiki-builder`;
- machine-readable smoke cases and repository health checks.

### Changed

- source governance now uses authority domain, source status, and attribution instead of a single global source rank;
- Skill frontmatter is restricted to portable `name` and `description` fields;
- named-person, named-practice, and project-specific regression examples were removed from public Skills;
- design-test rules are conditional rather than inheriting one competition's idealized operations assumption;
- release language now distinguishes tested environment, compatibility target, and unverified host;
- contributor affiliation is explicitly biographical and not institutional endorsement.

### Notes

This release packages methods learned through real task iterations, but it does not claim universal host or cross-domain equivalence. Evaluation definitions are included; published run results should identify host, model, Skill commit, date, inputs, and reviewer.
