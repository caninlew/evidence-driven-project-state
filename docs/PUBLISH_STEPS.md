# Publish Steps

## Goal

Create a citable public software release without publishing the manuscript, held-out evaluation set, confidential evidence, or unresolved authorship and rights claims.

## 1. Complete the hard gate first

Before initializing or pushing the repository, complete every P0 item in [PUBLIC_RELEASE_GATE.md](PUBLIC_RELEASE_GATE.md). In particular, confirm:

- the publishing individual's stable public name;
- ORCID if it will be used;
- the final GitHub owner and repository URL;
- written IP and affiliation clearance;
- rights to license every tracked file.

Do not activate `CITATION.cff` with placeholder or assumed values.

## 2. Create an active citation file

Copy `CITATION.cff.template` to `CITATION.cff`, replace every placeholder, and validate it. Keep only `CITATION.cff` unless Zenodo-specific metadata is genuinely required: when both `.zenodo.json` and `CITATION.cff` exist, Zenodo gives `.zenodo.json` precedence.

The DOI may be omitted from the first citation file because it does not exist until the archive is created. Add it in a later metadata release.

## 3. Create a private GitHub repository first

Recommended repository name:

`evidence-driven-project-state`

Initialize and push only after the hard gate is complete:

```bash
git init
git add .
git commit -m "chore: prepare public v0.1.0-alpha release"
git branch -M main
git remote add origin <confirmed-repository-url>
git push -u origin main
```

Keep the repository private for the first remote review. Confirm README rendering, links, issue templates, Actions, contributor metadata, and Git history.

## 4. Configure the public repository

Use [GITHUB_ABOUT_AND_TOPICS.md](GITHUB_ABOUT_AND_TOPICS.md) for the About text and topics. Keep Issues enabled for reproducible bug reports. Enable Discussions only if the maintainer can moderate open-ended requests.

Before the DOI-bearing release:

1. make the reviewed repository public;
2. connect the repository in the [Zenodo GitHub integration](https://help.zenodo.org/docs/github/);
3. confirm that the intended repository is enabled in Zenodo.

## 5. Create the first archival release

Suggested tag and title:

- `v0.1.0-alpha`
- `v0.1.0-alpha - Architecture-first public alpha`

Use [RELEASE_NOTES_v0.md](../RELEASE_NOTES_v0.md) as the release body. Create a GitHub Release, not only a tag. Confirm the archived files, creator metadata, license, version DOI, and concept DOI in Zenodo.

If the first DOI was unknown when `CITATION.cff` was committed, add the DOI and issue a small metadata release. Keep citation metadata consistent across GitHub, Zenodo, README, AUTHORS, and ORCID.

## 6. Preserve an additional public record

Request or verify [Software Heritage](https://archive.softwareheritage.org/) archival after the public release. Record the SWHID in a later release or provenance update when available.

## 7. Keep the paper boundary separate

The GitHub release establishes a public software version; it does not publish the paper's full novelty package. Keep the manuscript, complete protocol, held-out cases, and unreported results outside this repository. If a time-stamped study plan is needed without immediate disclosure, use a separately controlled or embargoed research registration.

Before journal submission, re-check the venue's current policies for preprints, anonymization, data availability, copyrighted material, and substantive generative-AI use.

## 8. Final decision

Publish only when both of these are true:

- the repository health workflow passes;
- every P0 item in [PUBLIC_RELEASE_GATE.md](PUBLIC_RELEASE_GATE.md) is complete.

If either condition fails, keep the GitHub repository private and do not create a DOI-bearing release.