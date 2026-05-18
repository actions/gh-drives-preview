# GitHub Drives (Private Preview)

Persistent storage for GitHub Actions workflows.

> ⚠️ **Private preview.** Access is gated. Contact the drives team to enroll your repository.

## Usage

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      id-token: write
    steps:
      - name: Checkout Drive
        uses: actions/gh-drives-preview/checkout@main
        with:
          drive-name: default

      # ... your work ...

      - name: Commit Drive
        uses: actions/gh-drives-preview/commit@main
        with:
          drive-name: default
```

- **`checkout`** — creates or loads a persistent drive into your workspace.
- **`commit`** — saves changes back to storage. Omit to use read-only.

## Requirements

- `ubuntu-latest` runner (Linux only during preview)
- Repository enrolled in the private preview