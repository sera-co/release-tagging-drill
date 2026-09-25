\# Versioning Convention



\## 1. Semantic Versioning



This repository follows Semantic Versioning using the format:



`MAJOR.MINOR.PATCH`



\### MAJOR



A MAJOR version is increased when a change is breaking or incompatible with the previous release.



Example:



`v1.4.2 -> v2.0.0`



\### MINOR



A MINOR version is increased when a new backward-compatible feature is added.



Example:



`v1.4.2 -> v1.5.0`



\### PATCH



A PATCH version is increased when a backward-compatible bug fix is released.



Example:



`v1.4.2 -> v1.4.3`



When MAJOR or MINOR is increased, the lower version components are reset as required. For example, `v1.4.2 -> v1.5.0` for a MINOR release.



\## 2. Tag Naming Format



All production releases use the exact format:



`vMAJOR.MINOR.PATCH`



Example:



`v1.5.0`



The `v` prefix is mandatory. Release names such as `release\_2`, `latest-good`, `stable-build`, and `v2-final-FINAL` will not be used.



\## 3. Annotated Tags



Production releases use annotated Git tags.



Annotated tags are used because they store release metadata such as the tagger, date, and annotation message, making releases easier to audit and identify.



The command used to create a release tag is:



```bash

git tag -a v1.5.0 -m "Release 1.5.0: add checkout improvements"

```



The tag is then pushed to the remote repository with:



```bash

git push origin v1.5.0

```



Lightweight tags are not used for production releases.



\## 4. Pre-release Rule



Release candidates and beta versions use a pre-release suffix.



Examples:



`v1.5.0-beta.1`



`v1.5.0-rc.1`



`v1.5.0-rc.2`



Pre-release versions come before the corresponding final release:



`v1.5.0-rc.1 < v1.5.0-rc.2 < v1.5.0`



The final release is represented by the normal semantic version:



`v1.5.0`



\## Release Requirements



Every production release must:



1\. Follow Semantic Versioning.

2\. Use the `vMAJOR.MINOR.PATCH` format.

3\. Be created as an annotated Git tag.

4\. Point to the exact release commit.

5\. Have a meaningful annotation message.

6\. Be included in the release map.

7\. Have corresponding release notes.

8\. Be traceable to a deployment record.



