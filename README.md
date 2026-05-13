# @actalog/node-ci

[![CI](https://github.com/actalog/node-ci/actions/workflows/ci.yml/badge.svg)](https://github.com/actalog/node-ci/actions/workflows/ci.yml)
[![CD](https://github.com/actalog/node-ci/actions/workflows/cd.yml/badge.svg)](https://github.com/actalog/node-ci/actions/workflows/cd.yml)

Continuous Integration for Node.js projects

## Getting started

```yml
name: CI

on:
  - pull_request
  - push

permissions:
  pull-requests: write

jobs:
  node-ci:
    name: Node CI
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actalog/node-ci@v3
        with:
          package-manager: pnpm # optional, default is npm
```

## Inputs

| Name              | Description                                        | Default |
| ----------------- | -------------------------------------------------- | ------- |
| `node-version`    | Node.js version                                    | `24`    |
| `package-manager` | Package manager to use (`npm`, `yarn`, or `pnpm`)   | `npm`   |
| `except`          | Scripts to skip (comma-separated: `build`, `lint`) | ``      |
| `github-token`    | GitHub Token (for SonarCloud and PR comments)      | ``      |
| `sonar-token`     | SonarCloud Token                                   | ``      |
