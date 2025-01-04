# GitHub Action

## Swift Doc Deployment

### Deploys the Swift documentation to GitHub pages.

#### Usage

```yml
name: "Swift Doc Deployment"

on: [push]

jobs:
  build:
    runs-on: macos-latest

    steps:
      - uses: actions/checkout@main
      - uses: g1j0shi/swift-doc-deployment@main
```

#### Input

```yml
      ...
      - uses: g1j0shi/swift-doc-deployment@main
        with:
          target: "SwiftPackage" # The Swift package target to generate documentation for.
          branch: "gh-pages" # The branch where the documentation will be deployed.
```
