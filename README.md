# Share Hub - MCP Server Upload Guide

## Overview
This guide provides instructions for uploading documents to the Share Hub using an MCP server with Git capabilities. The Share Hub is a Jekyll-based document sharing portal with public and private sections.

## Repository Structure
```
sharehub/
├── public/          # Public documents (no password required)
│   ├── *.md        # Markdown files (auto-converted to HTML by Jekyll)
│   └── *.html      # Direct HTML files
├── private/         # Private documents (password protected - default: "maco")
│   ├── *.md        # Markdown files (auto-converted to HTML by Jekyll)
│   └── *.html      # Direct HTML files
└── _layouts/        # Jekyll layouts (DO NOT MODIFY)
```

## File Upload Guidelines

### 1. Public Documents
Upload files to the `public/` directory for documents that should be accessible without authentication.

**For Markdown files (.md):**
```
Location: public/[filename].md
```
- Must include YAML front matter at the top:
```yaml
---
title: "Document Title"
date: 2025-01-09
---
```

**For HTML files (.html):**
```
Location: public/[filename].html
```
- Can be standalone HTML or use Jekyll templating
- If using Jekyll templating, include front matter:
```yaml
---
title: "Document Title"
layout: default
---
```

### 2. Private Documents
Upload files to the `private/` directory for password-protected documents.

**For Markdown files (.md):**
```
Location: private/[filename].md
```
- Must include YAML front matter:
```yaml
---
title: "Confidential Document Title"
date: 2025-01-09
---
```

**For HTML files (.html):**
```
Location: private/[filename].html
```
- Include front matter for Jekyll processing:
```yaml
---
title: "Confidential Document Title"
layout: private_protected
---
```

### 3. Organizing Documents in Subfolders
You can create subfolders within `public/` or `private/` for better organization:
```
public/
├── reports/
│   ├── quarterly_report.md
│   └── annual_summary.html
├── presentations/
│   └── product_launch.md
```

## File Naming Conventions
- Use lowercase letters
- Replace spaces with underscores or hyphens
- Avoid special characters except `-` and `_`
- Examples: `marketing_report.md`, `q1-sales-data.html`

## Git Workflow for MCP Server

### Step 1: Clone or Pull Latest Changes
```bash
git pull origin main
```

### Step 2: Add Your Document
Place your file in the appropriate directory:
- `public/` for public access
- `private/` for password-protected access

### Step 3: Commit Changes
```bash
git add [filepath]
git commit -m "Add [document type]: [brief description]"
```

Example commit messages:
- "Add public report: Q1 2025 marketing analysis"
- "Add private document: Confidential financial data"
- "Update public/sales_dashboard.html with latest figures"

### Step 4: Push to Repository
```bash
git push origin main
```

## Document Templates

### Markdown Template (public/example.md)
```markdown
---
title: "Document Title Here"
date: 2025-01-09
author: "Author Name"
---

# Main Heading

## Introduction
Your content here...

## Section 1
More content...

## Conclusion
Final thoughts...
```

### HTML Template (public/example.html)
```html
---
title: "Document Title Here"
layout: default
---

<h1>Main Heading</h1>

<section>
    <h2>Introduction</h2>
    <p>Your content here...</p>
</section>

<section>
    <h2>Main Content</h2>
    <p>More content...</p>
</section>
```

## URL Structure After Upload
Once uploaded and pushed, documents will be accessible at:

**Public documents:**
- `https://tommyjns.github.io/sharehub/public/[filename]`
- Example: `https://tommyjns.github.io/sharehub/public/marketing_report`

**Private documents:**
- `https://tommyjns.github.io/sharehub/private/[filename]`
- Example: `https://tommyjns.github.io/sharehub/private/confidential_data`
- Password required: "maco"

## Important Notes
1. **Jekyll Processing**: GitHub Pages automatically processes .md files to HTML
2. **Index Page**: The main page at https://tommyjns.github.io/sharehub/ automatically lists all uploaded documents
3. **Password Protection**: All files in `private/` are automatically password-protected
4. **Build Time**: After pushing, GitHub Pages may take 1-5 minutes to build and deploy changes
5. **File Size**: Keep individual files under 100MB for optimal performance

## Troubleshooting

### Document Not Appearing
- Ensure proper YAML front matter is included
- Check file is in correct directory (public/ or private/)
- Wait 5 minutes for GitHub Pages to rebuild
- Verify git push was successful

### Formatting Issues
- Validate YAML front matter syntax
- Check markdown syntax is correct
- Ensure HTML files are well-formed

### Access Issues
- Private documents require password: "maco"
- Clear browser cache if having issues
- Check URL is correct including the /sharehub/ base path

## Support
For issues or questions about the Share Hub structure, refer to the main README.md file or contact the repository administrator.
