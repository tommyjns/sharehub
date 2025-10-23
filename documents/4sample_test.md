---
layout: universal
---
# Sample Test Document

This is a sample markdown file created **without front matter** to test the auto-frontmatter GitHub Actions workflow.

## Features to Test

- Automatic detection of missing front matter
- Auto-addition of minimal front matter (`---` on two lines)
- Auto-commit by GitHub Actions bot

## Instructions

1. Commit this file to the repository
2. Push to GitHub (main branch)
3. Watch the GitHub Actions workflow run
4. Check this file again - it should have front matter added automatically

## Expected Result

After the workflow runs, this file should start with:
```
---
---
```

And then this content will follow.

## Why This Matters

Jekyll/GitHub Pages requires front matter to process markdown files. Without it, the file is served as plain text instead of being rendered as HTML.
