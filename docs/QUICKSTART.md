# Quickstart

## 5-minute path

### 1. Install for your host

Follow [Installation](INSTALLATION.md). Hermes Agent is the primary tested environment; OpenClaw is the primary compatibility target. Other hosts require their own smoke validation.

### 2. Prepare one project root

Keep one project's sources inside an explicit root. Start with copies or non-confidential fixtures.

```text
project-root/
├─ brief.md
├─ meeting-notes.md
├─ consultant-feedback.md
└─ drawing-notes.md
```

### 3. Establish project state

```text
Use architect-project-state. Treat this folder as the only allowed project root. Register sources, separate current facts, stakeholder statements, derivations, conflicts, and open questions. Do not generate a design proposal. Write a new state version and change log, then re-read them.
```

Expected: traceable source register, domain-aware authority/status, compatible metric definitions, open questions, and bounded tasks.

### 4. Add a method lens only after state is stable

```text
Use architect-method-lens in Apply mode. Start from the verified project state. Produce up to three method cards with evidence, counterexamples, failure conditions, and project-specific questions. Do not imitate recognizable form or personality.
```

### 5. Turn eligible methods into tests

```text
Use design-test-framework-rounds. Turn the eligible method cards into two materially different, falsifiable frameworks. Show assumptions, blockers, stopping conditions, and the next human decision. Recommend the test order, not the final scheme.
```

## The two loops

```text
Project loop: sources -> state -> bounded work -> output -> human decision
Learning loop: failure -> correction -> Skill change -> fixed-input regression -> release
```

A successful file write or an `available` status proves installation only. It does not prove method quality.

## When to stop

Pause for human confirmation when source authority materially changes the conclusion, metric definitions are incompatible, sources conflict without an authorized decision, the workflow reaches professional sign-off, or the output starts turning a hypothesis into an attributed method.