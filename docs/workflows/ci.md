# Continuous Integration Workflow

Our CI workflow automates building and testing of your code.

## Usage

Reference the shared CI workflow in your repository:

```yaml
name: Continuous Integration

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    uses: your-org/.github/.github/workflows/ci.yml@main
    with:
      node-version: '16'
