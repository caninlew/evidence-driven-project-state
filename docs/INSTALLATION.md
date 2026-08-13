# Installation

## Compatibility profile

The skills use the open Agent Skills layout: one folder per skill, a `SKILL.md` file with `name` and `description` frontmatter, plus optional `references/` files.

Current priority environments:

| Host | Status | Notes |
|---|---|---|
| Hermes Agent | Primary tested environment | The original workflow and repeated forward tests were run here |
| OpenClaw | Primary compatibility target | The layout follows its Agent Skills-compatible loader; runtime parity remains an ongoing validation item |
| Other Agent Skills hosts | Format target, not yet certified | Tool names, security boundaries, refresh behavior, and reference loading may differ |

Do not describe format compatibility as full runtime equivalence.

## Install on Hermes Agent

Copy each complete skill directory into the skills root used by your Hermes installation, preserving names and `references/`. Official Hermes documentation uses `$HERMES_HOME/skills/` (normally `~/.hermes/skills/`); desktop distributions may expose a platform-specific managed directory.

Example layout:

```text
$HERMES_HOME/skills/
├─ architect-project-state/
├─ architect-method-lens/
├─ design-test-framework-rounds/
└─ architect-wiki-builder/
```

Start a fresh session or refresh the skill registry, then confirm the skills are discoverable. If the repository is published, Hermes also supports installing a Skill from a direct `SKILL.md` URL; use the host's current command help rather than assuming a stale command syntax.

## Install on OpenClaw

Copy each complete skill directory into one of OpenClaw's supported locations:

- workspace skills: `<workspace>/skills/`;
- managed user skills: `~/.openclaw/skills/`;
- shared personal skills: `~/.agents/skills/`.

Preserve each folder name so it matches frontmatter `name`. Refresh the session and inspect the host's skill list. OpenClaw compatibility is a current target; run the smoke cases before relying on behavioral parity.

## Generic Agent Skills hosts

Where supported, place a skill directory under the host's project or personal skills root, commonly `.agents/skills/<skill-name>/` or `~/.agents/skills/<skill-name>/`. Verify all of the following:

1. the host discovers `SKILL.md`;
2. it loads linked files under `references/`;
3. the frontmatter parser accepts the description;
4. file and network permissions match the task boundary;
5. a fixed smoke case produces the required evidence discipline.

## Optional LLM Wiki adapter

`architect-wiki-builder` can use a local LLM Wiki API at `http://127.0.0.1:19828`. Keep it local, do not publish tokens, and treat generated pages as retrieval candidates. If unavailable, the Skill must degrade to Raw-only evidence audit instead of rebuilding a second Wiki.

## Verification checklist

After installation:

1. all four skills appear in the host's skill registry;
2. `architect-project-state` refuses to promote an unconfirmed note into project fact;
3. incompatible metric definitions remain incomparable;
4. `architect-method-lens` produces evidence-backed method hypotheses rather than biography or style imitation;
5. `design-test-framework-rounds` produces falsifiable frameworks, not a final design;
6. `architect-wiki-builder` reaches the local API or reports Raw-only degradation;
7. the host does not access files outside the permitted project root.

See [Quickstart](QUICKSTART.md) and the smoke cases under `evals/`.