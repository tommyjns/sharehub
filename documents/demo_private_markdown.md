---
---
# Demo Document Without Front Matter

This is a test document created without front matter to verify the auto-frontmatter workflow.

## Purpose

This file should trigger the GitHub Actions workflow which will automatically add the minimal front matter (`---` on two lines) to the top of this file.

## Expected Behavior

1. File is pushed to GitHub without front matter
2. Workflow detects it's missing front matter
3. Workflow adds `---\n---\n` to the beginning
4. Workflow commits the change automatically
5. Jekyll can now process this file correctly
