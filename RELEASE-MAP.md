\# Release Map



This document maps each release version to the exact Git commit and describes what was present at that release point.



| Version | Commit    | Date       | What Shipped                                                                     |

| ------- | --------- | ---------- | -------------------------------------------------------------------------------- |

| v1.0.0  | `4febcc6` | 2026-06-06 | Initial repository baseline                                                      |

| v1.1.0  | `ff1fb9a` | 2026-06-06 | Assignment repository scaffold and project structure                             |

| v1.2.0  | `82535d9` | 2026-06-06 | Checkout service placeholder implementation with service name and version output |



\## Release Identification



List releases in descending semantic-version order:



```bash

git tag --sort=-v:refname

```



Inspect the commit associated with a release:



```bash

git show v1.2.0

```



Find the previous release:



```bash

git tag --sort=-v:refname

```



The next version below the current release can be used as the previous known-good release.



\## Rollback



To roll back to a specific known release:



```bash

git checkout v1.1.0

```



A release tag points to an exact commit, so the same tag can be used to reproduce the same code state.



For example:



```bash

git checkout v1.2.0

```



restores the repository to the exact commit associated with `v1.2.0`.



\## Traceability



The release chain is:



`Version -> Git Tag -> Commit -> Code State`



This provides precise traceability because each release identifier points to a specific immutable Git commit.



Without versioned tags, operators would need to manually identify a commit from an inconsistent history or deployment document. That increases the chance of selecting the wrong code during rollback.



With annotated SemVer tags, the release and its exact commit can be identified and reproduced consistently.



