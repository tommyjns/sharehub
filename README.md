# Share Hub - Secure Document Sharing Portal

A Jekyll-based document sharing portal with password protection, designed for GitHub Pages deployment.

## Features

- 📁 **Dual-folder structure**: Public and Private document sections
- 🔒 **Password Protection**: Secure access to confidential documents
- 📊 **Smart Tables**: Sortable, searchable document listings with DataTables
- 📱 **Responsive Design**: Works on desktop and mobile devices
- 🚀 **GitHub Pages Ready**: Deploy directly to GitHub Pages

## Quick Start

### 1. Setup

1. Fork or clone this repository
2. Enable GitHub Pages in your repository settings
3. Set the source to deploy from the main branch

### 2. Adding Documents

#### Public Documents (Open Access)
Place documents in the `public/` folder:

```markdown
---
layout: default
title: Your Document Title
date: 2024-10-15
---

Your content here...
```

#### Private Documents (Password Protected)
Place documents in the `private/` folder:

```markdown
---
layout: private_protected
title: Confidential Document
date: 2024-10-15
---

Your confidential content...
```

### 3. Password Protection

- **Default Password**: `dev123123`
- **Protection Levels**:
  - Level 1: Password required to view private document list
  - Level 2: Password required for each private document access
- **Sharing with Password**: Add `?key=dev123123` to the URL

#### Changing the Password

To change the password, update it in two files:

1. **index.html** (line ~189):
```javascript
if (password === 'dev123123') {
```

2. **_layouts/private_protected.html** (line ~108):
```javascript
if (password === 'dev123123') {
```

> ⚠️ **Security Note**: This uses client-side protection suitable for casual privacy. For sensitive data, use server-side authentication.

## File Structure

```
share-hub/
├── _layouts/
│   ├── default.html          # Standard layout for public documents
│   └── private_protected.html # Password-protected layout
├── public/                    # Public documents (open access)
│   └── *.md / *.html
├── private/                   # Private documents (password required)
│   └── *.md / *.html
├── _config.yml               # Jekyll configuration
├── index.html                # Main portal page
└── README.md                 # This file
```

## Document Format

### Markdown Files (.md)

```markdown
---
layout: default  # or private_protected for private docs
title: Document Title
date: 2024-10-15
---

# Your Content

Write your content in Markdown format...
```

### HTML Files (.html)

```html
---
layout: default  # or private_protected for private docs
title: Document Title
date: 2024-10-15
---

<h1>Your Content</h1>
<p>Write your content in HTML format...</p>
```

## Customization

### Site Title and Description

Edit `_config.yml`:

```yaml
title: Share Hub
description: Secure Document Sharing Portal
```

### Styling

The site uses Bootstrap 5. To customize:
- Modify styles in `_layouts/default.html`
- Add custom CSS in the `<style>` sections

### Table Features

DataTables is configured with:
- Search functionality
- Sorting by columns
- Pagination (10 items per page)
- Responsive design

## Deployment

### GitHub Pages

1. Push your changes to GitHub
2. Go to Settings → Pages
3. Select source: Deploy from branch (main)
4. Your site will be available at: `https://[username].github.io/[repository-name]/`

### Local Development

```bash
# Install Jekyll
gem install bundler jekyll

# Install dependencies
bundle install

# Run locally
bundle exec jekyll serve

# Visit http://localhost:4000
```

## URL Parameters

- `?key=[password]` - Unlock private section with password
- `?unlock=[password]` - Alternative parameter for unlocking

Example: `https://yourdomain.com/share-hub/?key=dev123123`

## Browser Compatibility

- Chrome (recommended)
- Firefox
- Safari
- Edge
- Mobile browsers

## Session Persistence

- Password authentication is stored in browser session
- Remains active until browser tab is closed
- Each new tab requires re-authentication

## Troubleshooting

### Documents not appearing in list
- Ensure proper front matter with `title` and `date` fields
- Check file is in correct folder (public/ or private/)

### Password not working
- Clear browser cache and session storage
- Ensure password matches in both index.html and private_protected.html

### Date not displaying
- Add `date: YYYY-MM-DD` to document front matter

## Security Considerations

This portal uses client-side password protection, which:
- ✅ Prevents casual access to private documents
- ✅ Works with static hosting (GitHub Pages)
- ❌ Should NOT be used for highly sensitive data
- ❌ Can be bypassed by technical users

For production use with sensitive data, consider:
- Server-side authentication
- Encrypted storage
- Professional security audit

## License

MIT License - See LICENSE file for details

## Support

For issues or questions:
1. Check this README
2. Review existing GitHub Issues
3. Create a new Issue with details

---

Built with Jekyll, Bootstrap 5, and DataTables
