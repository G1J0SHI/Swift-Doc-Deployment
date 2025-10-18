# GitHub Action

## Swift Doc Deployment

### Deploys the Swift documentation to GitHub pages.

#### Usage

```yml
name: "Swift Doc Deployment"

on: [push]

jobs:
  deploy:
    runs-on: macos-latest
    permissions:
      pages: write
      id-token: write
    environment:
      name: github-pages
      url: ${{ steps.cicd.outputs.page-url }}
    steps:
      - uses: g1j0shi/swift-doc-deployment@main
        id: cicd
```

#### Input

| Name   | Description                                         | Required | Default |
| ------ | --------------------------------------------------- | -------- | ------- |
| target | The Swift package target to generate documentation. | true     | -       |

#### Output

| Name     | Description                           |
| -------- | ------------------------------------- |
| page-url | URL of the deployed GitHub Pages site |

#### Example

```yml
      ...
      - uses: g1j0shi/swift-doc-deployment@main
        id: cicd
        with:
          target: "SwiftPackage"
```
