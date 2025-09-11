# Jekyll Commands for Local Development

## Build and Serve Commands

### To build the site:
```bash
bundle exec jekyll build
```

### To run the site locally (development server):
```bash
bundle exec jekyll serve
```
This will run the site at: http://127.0.0.1:4000/

### To run with live reload (auto-rebuild on file changes):
```bash
bundle exec jekyll serve --livereload
```

### To run on a different port:
```bash
bundle exec jekyll serve --port 3000
```

## Configuration Notes

- For **local development**: The `baseurl` in `_config.yml` is set to `""` (empty), so the site runs at http://127.0.0.1:4000/
- For **GitHub Pages**: Change `baseurl` back to `"/jekyll-site"` before pushing to GitHub

## Ruby/Gem Architecture Fix (if needed in future)

If you encounter architecture issues with gems on M4 Mac, use:
```bash
# Uninstall problematic x86_64 gems
sudo gem uninstall [gem-name] -a -x --force

# Reinstall with ARM64 architecture
sudo arch -arm64 gem install [gem-name]
```

## Dependencies
- Ruby 2.6.10 (system Ruby on macOS)
- Jekyll 4.2.2 (compatible with Ruby 2.6)
- Bundler 2.4.22 (compatible with Ruby 2.6)
