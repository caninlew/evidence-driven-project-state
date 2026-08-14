# Public release gate

Use this gate before making the repository public or creating a DOI-bearing release. It is intentionally separate from the engineering checklist: passing CI does not prove that authorship, rights, and research timing are cleared.

## P0 — release blockers

- [ ] Confirm the publishing individual's stable public name.
- [ ] Add an ORCID if available and verify that it belongs to the contributor.
- [ ] Confirm the final GitHub owner and repository URL.
- [ ] Obtain and retain the necessary written internal IP / affiliation clearance.
- [ ] Confirm that the contributor has the right to license every tracked file.
- [ ] Complete the third-party material review in [THIRD_PARTY_NOTICES.md](../THIRD_PARTY_NOTICES.md).
- [ ] Confirm that no client, participant, confidential, copyrighted-source, held-out, project-specific proper name, or otherwise identifiable case material is present in the files or Git history.
- [ ] Copy `CITATION.cff.template` to `CITATION.cff`, replace every placeholder, and validate the file.
- [ ] Confirm that `AUTHORS.md`, the citation metadata, GitHub profile, and release metadata use the same public identity.
- [ ] Run secret scanning and the repository health workflow with no failures.

## P1 — version and preservation

- [ ] Review the repository in a private GitHub repository first.
- [ ] Freeze a release commit and record its SHA.
- [ ] Confirm README rendering, links, issue templates, and Actions.
- [ ] Connect the intended public repository to Zenodo before the first DOI-bearing GitHub release.
- [ ] Create a versioned GitHub release; confirm the Zenodo archive and DOI.
- [ ] Add the DOI to the next citation-metadata release if it was not known at the first release.
- [ ] Request or verify a Software Heritage archive and record the SWHID when available.

## P2 — academic boundary

- [ ] Keep the manuscript, full protocol, held-out cases, and unreported results outside this repository.
- [ ] Time-stamp the research protocol separately, using an embargo if the study plan should not yet be public.
- [ ] Verify the target venue's current preprint, anonymization, data, copyright, and generative-AI policies before submission.
- [ ] Cite the exact software release used in the study.
- [ ] State development, tuning, validation, and held-out roles for every case set.

## Do not release yet if

Any P0 item is incomplete, the repository contains an active citation file with placeholder data, or the rights boundary depends only on an assumption. A Git tag alone is not the final preservation record; use a public release plus an archival identifier.
