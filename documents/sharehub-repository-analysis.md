---
layout: universal
---
# ShareHub Repository Analysis

**Repository**: https://github.com/tommyjns/sharehub
**Analyzed**: 2025-10-31
**Focus**: All files

## Overview

ShareHub is a Jekyll-based document sharing portal with tag-based access control. Documents can be public or private based on tags in their front matter, not their folder location.

## Key Features

### Tag-Based Protection System
- **Public files**: No `access` tag needed (default)
- **Private files**: Add `access: private` in front matter
- **Password**: "maco" for all private documents

### Repository Structure
```
sharehub/
├── documents/          # All documents (both public and private)
│   ├── *.md           # Markdown files
│   ├── *.html         # HTML files
│   └── [subfolders]/  # Optional organization by topic
├── _layouts/          # Jekyll layouts (DO NOT MODIFY)
│   └── universal.html # Universal layout with protection logic
└── index.html         # Main listing page
```

## Technology Stack

- **Framework**: Jekyll 4.3.2
- **Deployment**: GitHub Pages
- **Authentication**: Session-based password protection
- **Frontend**: Bootstrap, DataTables, jQuery
- **Version Control**: Git/GitHub

## File Organization

### Documents Directory
All documents stored in `/documents/` folder with optional subfolders for organization:
- `/documents/reports/`
- `/documents/presentations/`
- `/documents/Archive/`
- `/documents/Report/`

### Access Control
Access is controlled via YAML front matter tags, not folder structure:

**Public Document (default):**
```yaml
---
title: "Document Title"
---
```

**Private Document:**
```yaml
---
title: "Document Title"
access: private
---
```

## Key Configuration Files

### `_config.yml`
- **Title**: Share Hub
- **Base URL**: /sharehub
- **Markdown**: Kramdown
- **Plugins**: jekyll-feed, jekyll-seo-tag
- **Default Layout**: universal

### `Gemfile`
- Jekyll 4.3.2
- Jekyll plugins (feed, SEO)
- WebRick for Ruby 3.0+ compatibility

## Index Page Features

- **Before login**: Shows only public documents
- **After login**: Shows all documents (public + private)
- **Visual indicators**:
  - 🔒 Lock icon for private files
  - Folder badges for files in subfolders
- **Default view**: HTML/MD files only (checkbox to show all types)
- **Sorting**: Alphabetical by title/folder name
- **Search**: DataTables integration for filtering
- **Mobile responsive**: Adaptive layout for different screen sizes

## Automated Workflows

### GitHub Actions

#### 1. Jekyll Build & Deploy (`jekyll.yml`)
- Triggered on push to main
- Builds Jekyll site
- Deploys to GitHub Pages
- Permissions: contents (read), pages (write), id-token (write)

#### 2. Add Frontmatter (`add-frontmatter.yml`)
- Triggers on push (documents folder changes)
- Adds YAML frontmatter to files missing it
- Ensures all documents have proper metadata

## Document Management

### Adding Documents

**Public Document:**
```yaml
---
---
Content here...
```

**Private Document:**
```yaml
---
access: private
---
Private content...
```

### Git Workflow
```bash
git pull origin main
git add documents/[filename]
git commit -m "Add [type]: [description]"
git push origin main
```

### URL Structure
- **GitHub Pages**: `https://[username].github.io/sharehub/documents/[filename]`
- **Relative**: `/documents/[filename]`

## Security Features

- Password protection for private documents
- Session-based authentication
- Client-side password checking
- SHA256 password hashing support (future)

## AI Assistant Integration

The repository includes comprehensive AI assistant prompts (`AI_ASSISTANT_PROMPT.md`) for:
- Document upload automation
- MCP Git server integration
- Access control management
- Repository maintenance

### MCP Connection Assumptions
- **Repository**: sharehub (default)
- **Authentication**: Automatic via MCP
- **Documents Path**: `/documents/` folder

## Example Documents

### Current Documents
- `demo_private_markdown.md` - Private demo
- `demo_webpage.html` - Public demo
- `testmd.md` - Test markdown
- Various reports in `/documents/Report/`
- Archived documents in `/documents/Archive/`

## Mobile Responsiveness

- Adaptive header layout
- Hidden date column on small screens
- Responsive table controls
- Touch-friendly password input
- Optimized search interface

## Best Practices

1. **Always** upload documents to `/documents/` folder
2. **Never** modify files in `_layouts/` directory
3. **Always** include minimal front matter (`---\n---`)
4. **Remember** files are public by default
5. **Use** descriptive commit messages
6. **Ask** user if document should be private
7. **Password** is always "maco"
8. **Title** is optional - filename used as fallback

## Migration from Folder-Based System

For existing files in `public/` and `private/` folders:
1. Move all files to `documents/` folder
2. Add `access: private` to previously private files
3. Remove old folder structure
4. Commit and push changes

## Troubleshooting

### Document Not Appearing
- Verify YAML front matter syntax
- Check file is in `documents/` folder
- Wait 5 minutes for GitHub Pages rebuild
- Clear browser cache

### Access Issues
- Private files need `access: private` tag
- Password is case-sensitive: "maco"
- Session storage keeps login until browser closes

## Important Notes

1. **Default Access**: Public unless tagged private
2. **Build Time**: 1-5 minutes after push
3. **File Size**: Keep under 100MB
4. **Front Matter**: Required for all .md and .html files
5. **Jekyll Processing**: Auto-converts .md to HTML

## Resources

- **Repository**: https://github.com/tommyjns/sharehub
- **GitHub Pages**: https://tommyjns.github.io/sharehub
- **Jekyll Docs**: Included in `JEKYLL_COMMANDS.md`
- **AI Prompts**: `AI_ASSISTANT_PROMPT.md`

## Tags

#repository #jekyll #github-pages #documentation #static-site #access-control
