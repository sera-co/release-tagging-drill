\# Release Notes



\## v1.2.0 — 2026-06-06



\### Added



\* Added the checkout service placeholder implementation.

\* Added explicit service name and service version output.



\### Changed



\* Updated the application entry point from the placeholder `runCheckout()` function to `run()`.



\### Fixed



\* Improved the application startup output so the service name and version are clearly identified.



\### Rollback



Previous known-good release: `v1.1.0`



Rollback command:



```bash

git checkout v1.1.0

```



\---



\## v1.1.0 — 2026-06-06



\### Added



\* Established the repository assignment scaffold and project structure.



\### Rollback



Previous known-good release: `v1.0.0`



Rollback command:



```bash

git checkout v1.0.0

```



\---



\## v1.0.0 — 2026-06-06



\### Added



\* Established the initial repository baseline.



\### Rollback



This is the initial release baseline.



\## Release Note Policy



Every release should document:



\* Version and date

\* Added changes

\* Changed behavior

\* Fixed issues

\* Previous known-good rollback target



Release notes complement Git tags by explaining what changed while the tag identifies the exact code state.



