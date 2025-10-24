# Setup Openlane Action

⚠️ **EXPERIMENTAL** - This action is experimental and subject to breaking changes. Use at your own risk.

A GitHub Action to set up the Openlane client in your workflow to sync changes such as internal policies stored as markdown

## Usage

```yaml
steps:
    - uses: theopenlane/setup-openlane@v1
        with:
            version: 'latest'  # Optional: specify Openlane version
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `version` | Version of Openlane client to install | No | `latest` |


## Example Workflow

```yaml
name: CI
on: [push, pull_request]

jobs:
    test:
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@v4
            - uses: theopenlane/setup-openlane@v1
                with:
                    version: 'v0.38.0'
            - run: openlane --version
```
