# Publish Steps

## Goal

This document covers the final manual steps to publish the repository.

At this point, the repository contents are already prepared.  
What remains is the actual GitHub-side publication flow.

## 1. Create the repository

Recommended repository name:

`evidence-driven-project-state`

Recommended visibility for the first pass:

- private first, if you want one last visual check
- public directly, if you are ready to release

## 2. Fill the GitHub About section

Use the values in:

- [GITHUB_ABOUT_AND_TOPICS.md](GITHUB_ABOUT_AND_TOPICS.md)

Recommended About:

`Evidence-driven, state-based project organization for complex multi-source workflows. Architecture-first domain pack included.`

## 3. Add repository topics

Use the suggested topics from:

- [GITHUB_ABOUT_AND_TOPICS.md](GITHUB_ABOUT_AND_TOPICS.md)

## 4. Push the repository

Standard sequence:

```bash
git init
git add .
git commit -m "chore: prepare public v0.1.0-alpha release"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```

## 5. Check GitHub rendering

After push, verify:

1. `README.md` renders correctly
2. Mermaid in `docs/ARCHITECTURE_FLOW.md` displays correctly
3. links between docs work on GitHub
4. issue templates are visible when opening a new issue
5. GitHub Actions shows the `Repo Health` workflow

## 6. Create the first release

Suggested tag:

`v0.1.0-alpha`

Suggested title:

`v0.1.0-alpha - Architecture-first public alpha`

Suggested body:

Use or adapt:

- [RELEASE_NOTES_v0.md](../RELEASE_NOTES_v0.md)

## 7. Optional first-day polish

If you want the repository to look more mature on day one, also do:

1. pin the repository if it matters to your profile
2. add a social preview image later
3. enable Discussions only if you want open-ended community input
4. keep Issues enabled for structured feedback

## 8. Final publish gate

You are ready to publish if:

- README is acceptable as the first impression
- repository name and About text are final
- no private material, named research subjects, client details, local paths, or credentials remain
- the affiliation disclaimer is visible and the named individual or handle is set if desired
- the Hermes smoke cases pass and any OpenClaw result is reported accurately

If all five are true, the repository is ready for GitHub publication.
