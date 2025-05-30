# Checking Broken links in markdown

---
The idea is like a app inside the project.

To add a new action inside a project:

Create a directory if worflow:
```bash
mkdir -p .github/workflows
```

Create the workflow file:
```yaml
name: Check Markdown Links

on:
  push:
    paths:
      - '**/*.md'
  pull_request:
    paths:
      - '**/*.md'
  workflow_dispatch:

jobs:
  linkChecker:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Lychee Broken Link Checker
        uses: lycheeverse/lychee-action@v2.4.1
        with:
          args: >-
            --verbose
            --exclude-mail
            --no-progress
            './**/*.md'

```
## 📚References & Resources
