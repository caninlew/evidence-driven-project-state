# Reproducibility

## Purpose

The repository makes workflow instructions inspectable, but reproducibility requires more than publishing prompts. A reported run should preserve enough environment, input, output, and review information for another team to understand what was tested and what remains host-dependent.

## Minimum run manifest

Record the following for every published evaluation:

| Field | Requirement |
|---|---|
| run ID and timestamp | stable identifier and timezone |
| repository version | release tag and commit SHA |
| Skill identity | Skill name and file hash |
| Agent environment | host, host version, model, and model setting |
| tools and permissions | available tools, allowed root, network state, and approval mode |
| input identity | redistributable file or hash plus authority status |
| procedure | prompt, mode, iteration limit, and any human intervention |
| output identity | artifact paths or hashes and completion state |
| evaluation | assertions, rubric, reviewer process, and disagreements |
| deviations | retries, failures, exclusions, and protocol changes |

## Development versus evaluation

- `evals/` contains public development regression cases.
- A case seen while writing or correcting a Skill is not held out.
- Held-out cases must be separated before evaluation and must not be exposed through prompts, fixtures, logs, or repository history.
- Report unsuccessful and partial runs, not only successful demonstrations.
- Do not compare hosts unless inputs, permissions, tools, stopping rules, and review criteria are equivalent or the differences are explicitly analyzed.

## Recommended artifact bundle

For a publishable study, archive a public-safe bundle containing the run manifest, versioned Skills, evaluation rubric, allowed inputs or hashes, generated outputs that may be shared, scored result table, adjudication notes, and a machine-readable checksum list. Restricted source material should remain in a separately controlled location described by [DATA_AVAILABILITY.md](DATA_AVAILABILITY.md).
