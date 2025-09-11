source "https://rubygems.org"

# Jekyll for static site generation (without github-pages gem for now)
gem "jekyll", "~> 4.3.2"

# Jekyll plugins
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-seo-tag", "~> 2.8"
end

# Windows and JRuby compatibility
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance booster for watching directories on Windows
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock http_parser.rb gem to v0.6.x for JRuby builds
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]

# Add webrick for Ruby 3.0+ compatibility
gem "webrick", "~> 1.8"
