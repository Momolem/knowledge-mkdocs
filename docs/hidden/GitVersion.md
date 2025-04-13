---
share: true
tags:
  - git
  - ci
  - versioning
---
> [!info] Official Website
> https://gitversion.net/
## Setup
Install gitversion (from https://gitversion.net/docs/usage/cli/installation)
```shell
dotnet tool install --global GitVersion.Tool --version 5.*
```

Initialize via wizard:
```shell
dotnet-gitversion init
```

Configure branch specific information using template from https://gitversion.net/docs/reference/configuration#:~:text=a%20build%20server.-,Branch%20configuration,-Then%20we%20have

### Example Setup
```yml
mode: ContinuousDelivery  
ignore:  
  sha: []  
merge-message-formats: {}  
branches:  
  main:  
    regex: ^master$|^main$  
    mode: ContinuousDelivery  
    tag: ''  
    increment: Patch  
    prevent-increment-of-merged-branch-version: true  
    track-merge-target: false  
    source-branches: [ 'develop', 'release' ]  
    tracks-release-branches: false  
    is-release-branch: false  
    is-mainline: true  
    pre-release-weight: 55000  
  develop:  
    regex: ^dev(elop)?(ment)?$  
    mode: ContinuousDeployment  
    tag: dev  
    increment: Minor  
    prevent-increment-of-merged-branch-version: false  
    track-merge-target: true  
    source-branches: []  
    tracks-release-branches: true  
    is-release-branch: false  
    is-mainline: false  
    pre-release-weight: 0  
  release:  
    regex: ^releases?[/-]  
    mode: ContinuousDelivery  
    tag: beta  
    increment: None  
    prevent-increment-of-merged-branch-version: true  
    track-merge-target: false  
    source-branches: [ 'develop', 'main', 'support', 'release' ]  
    tracks-release-branches: false  
    is-release-branch: true  
    is-mainline: false  
    pre-release-weight: 30000  
  feature:  
    regex: ^features?[/-]  
    mode: ContinuousDelivery  
    tag: useBranchName  
    increment: Inherit  
    prevent-increment-of-merged-branch-version: false  
    track-merge-target: false  
    source-branches: [ 'develop', 'main', 'release', 'feature', 'support', 'hotfix' ]  
    tracks-release-branches: false  
    is-release-branch: false  
    is-mainline: false  
    pre-release-weight: 30000  
  pull-request:  
    regex: ^(pull|pull\-requests|pr)[/-]  
    mode: ContinuousDelivery  
    tag: PullRequest  
    increment: Inherit  
    prevent-increment-of-merged-branch-version: false  
    tag-number-pattern: '[/-](?<number>\d+)[-/]'  
    track-merge-target: false  
    source-branches: [ 'develop', 'main', 'release', 'feature', 'support', 'hotfix' ]  
    tracks-release-branches: false  
    is-release-branch: false  
    is-mainline: false  
    pre-release-weight: 30000  
  hotfix:  
    regex: ^hotfix(es)?[/-]  
    mode: ContinuousDelivery  
    tag: beta  
    increment: Patch  
    prevent-increment-of-merged-branch-version: false  
    track-merge-target: false  
    source-branches: [ 'develop', 'main', 'support' ]  
    tracks-release-branches: false  
    is-release-branch: false  
    is-mainline: false  
    pre-release-weight: 30000  
  support:  
    regex: ^support[/-]  
    mode: ContinuousDelivery  
    tag: ''  
    increment: Patch  
    prevent-increment-of-merged-branch-version: true  
    track-merge-target: false  
    source-branches: [ 'main' ]  
    tracks-release-branches: false  
    is-release-branch: false  
    is-mainline: true  
    pre-release-weight: 55000
```

## Usage
### Show all possible Variables
```sh
dotnet-gitversion
```
Example output:
```json
{
  "Major": 0,
  "Minor": 8,
  "Patch": 0,
  "PreReleaseTag": "",
  "PreReleaseTagWithDash": "",
  "PreReleaseLabel": "",
  "PreReleaseLabelWithDash": "",
  "PreReleaseNumber": null,
  "WeightedPreReleaseNumber": 60000,
  "BuildMetaData": null,
  "BuildMetaDataPadded": "",
  "FullBuildMetaData": "Branch.develop.Sha.a5cf5c881143995e3549a786eb89ab388a1f0fab",
  "MajorMinorPatch": "0.8.0",
  "SemVer": "0.8.0",
  "LegacySemVer": "0.8.0",
  "LegacySemVerPadded": "0.8.0",
  "AssemblySemVer": "0.8.0.0",
  "AssemblySemFileVer": "0.8.0.0",
  "FullSemVer": "0.8.0",
  "InformationalVersion": "0.8.0+Branch.develop.Sha.a5cf5c881143995e3549a786eb89ab388a1f0fab",
  "BranchName": "develop",
  "EscapedBranchName": "develop",
  "Sha": "a5cf5c881143995e3549a786eb89ab388a1f0fab",
  "ShortSha": "a5cf5c8",
  "NuGetVersionV2": "0.8.0",
  "NuGetVersion": "0.8.0",
  "NuGetPreReleaseTagV2": "",
  "NuGetPreReleaseTag": "",
  "VersionSourceSha": "a5cf5c881143995e3549a786eb89ab388a1f0fab",
  "CommitsSinceVersionSource": 0,
  "CommitsSinceVersionSourcePadded": "0000",
  "UncommittedChanges": 1,
  "CommitDate": "2024-05-21"
}
```

### Show single variable
```sh
dotnet-gitversion /showvariable FullSemVer
```

Example output
```
0.9.0-zweitesFeature.1+0
```