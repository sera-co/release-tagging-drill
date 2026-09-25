\# Tag Audit



\## Overview



The repository's release history is inconsistent and does not provide a reliable, sortable, or traceable release history. The existing release documentation uses multiple naming conventions, while `git tag` currently returns no actual Git tags.



\## Identified Tagging Problems



\### 1. `latest-good` is an ambiguous release name



\*\*Evidence:\*\* `docs/release-notes-old.md` lists `latest-good`, and `docs/deployment-history.md` records a production deployment from `latest-good` on 2026-05-04.



\*\*Problem:\*\* The name describes a temporary status rather than a specific version number. A future release could also become the "latest good" release, making the name difficult to interpret historically.



\*\*Risk:\*\* During a rollback, the team cannot determine from the name alone which release `latest-good` represents or how it relates chronologically to other releases. This makes rollback and auditing unreliable.



\### 2. `release\_2` does not follow semantic versioning



\*\*Evidence:\*\* `docs/release-notes-old.md` contains `release\_2`, and `docs/deployment-history.md` records an emergency rollback to `release\_2` on 2026-04-22.



\*\*Problem:\*\* The name does not communicate whether this was a major release, minor release, or patch release.



\*\*Risk:\*\* Operators cannot reliably determine where `release\_2` belongs in release history or compare it with other releases. This makes selecting the correct rollback target more difficult.



\### 3. `1.5.0` is missing the required `v` prefix



\*\*Evidence:\*\* `docs/release-notes-old.md` contains a release named `1.5.0`.



\*\*Problem:\*\* The repository uses other forms such as `v1.4.2`, while this release omits the `v` prefix. Mixing `1.5.0` with `v1.4.2` creates an inconsistent naming convention.



\*\*Risk:\*\* Inconsistent naming makes automated sorting, release discovery, and operational documentation harder to interpret. A team member may also mistake differently formatted names for different release conventions.



\### 4. `v2-final-FINAL` is ambiguous



\*\*Evidence:\*\* `docs/release-notes-old.md` contains `v2-final-FINAL`.



\*\*Problem:\*\* The name uses repeated "final" wording instead of a semantic version such as `v2.0.0`. It does not communicate the exact release sequence or what changed.



\*\*Risk:\*\* If another release is created after `v2-final-FINAL`, it is unclear how it should be named or ordered. During an incident, the team cannot use the name to determine its precise position in release history.



\### 5. `stable-build` is not a versioned release identifier



\*\*Evidence:\*\* `docs/release-notes-old.md` contains `stable-build`, while `docs/deployment-history.md` records a missing deployment record for the release tagged `stable-build` on 2026-03-15.



\*\*Problem:\*\* The name describes a state rather than a unique release version.



\*\*Risk:\*\* "Stable" can apply to multiple releases over time. Without a semantic version, the team cannot reliably identify the exact release represented by the name, making deployment auditing and rollback less precise.



\### 6. `patch-new` does not identify a specific patch version



\*\*Evidence:\*\* `docs/release-notes-old.md` contains `patch-new`.



\*\*Problem:\*\* The name suggests a patch release but does not specify which patch number it represents.



\*\*Risk:\*\* The team cannot determine its chronological position or distinguish it from another patch release. This makes it difficult to identify the exact code that should be deployed or restored.



\### 7. No actual Git release tags exist



\*\*Evidence:\*\* Running `git tag` produces no output, and `git tag --sort=-v:refname` also produces no output.



\*\*Problem:\*\* The repository has release names in documentation, but those names are not currently represented as Git tags pointing to specific commits.



\*\*Risk:\*\* There is no permanent Git reference connecting a release name to an exact commit. A rollback therefore requires manually identifying a commit instead of checking out a known release tag, increasing the chance of selecting the wrong code.



\## Conclusion



The repository needs one consistent release convention using semantic versions in the `vMAJOR.MINOR.PATCH` format. Release versions should be created as annotated Git tags and mapped to their commits and deployment records so that releases can be audited and rolled back precisely.



