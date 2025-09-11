# Jekyll Reports Portal

A Jekyll-based site that automatically lists and displays HTML reports with a sortable Bootstrap table interface.

## Features

- **Automatic Report Discovery**: Automatically scans and lists all HTML files in the `reports/` folder
- **Sortable Table**: Interactive table with sorting capabilities for Title, Date, and File Size
- **Bootstrap Design**: Clean, minimal design using Bootstrap 5
- **Search Functionality**: Built-in search to filter reports
- **Responsive Layout**: Mobile-friendly design

## Structure

```
jekyll-site/
├── _config.yml          # Jekyll configuration
├── _layouts/            # Layout templates
│   └── default.html     # Main layout with Bootstrap
├── reports/             # Place your HTML reports here
│   ├── marketing_report.html
│   └── sales_dashboard.html
├── index.html           # Auto-listing homepage
├── Gemfile             # Ruby dependencies
└── README.md           # This file
```

## Local Development

1. Install Jekyll and dependencies:
```bash
bundle install
```

2. Run the development server:
```bash
bundle exec jekyll serve
```

3. Open browser to: http://localhost:4000

## GitHub Pages Deployment

1. Push this repository to GitHub
2. Go to Settings → Pages
3. Select source: "Deploy from a branch"
4. Choose branch: main (or master)
5. Select folder: / (root)
6. Save and wait for deployment

Your site will be available at: `https://[username].github.io/[repository-name]/`

## Adding New Reports

Simply add HTML files to the `reports/` folder. They will automatically appear in the index table with:
- Title (derived from filename)
- Last modified date
- File size

## Customization

- Edit `_config.yml` to change site title and description
- Modify `index.html` to customize the table layout
- Update `_layouts/default.html` to change the overall design
- Add more HTML reports to the `reports/` folder

## Requirements

- Jekyll 4.3+
- Ruby 2.7+
- Bundler
