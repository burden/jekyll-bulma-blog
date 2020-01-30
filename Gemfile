source "https://rubygems.org"
ruby RUBY_VERSION
gem "jekyll", "~> 3.8.6"
gem "rake"
gem "html-proofer"
gem "rack", ">= 2.0.8"

group :jekyll_plugins do
  gem "jekyll-assets"
  gem "kramdown"
  gem "uglifier", "~> 3.2"
  gem "jekyll-archives"
  gem "jekyll-compose"
  gem "jekyll-feed"
  gem "jekyll-paginate"
  gem "jekyll-redirect-from"
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem "tzinfo-data", platforms: [:mingw, :mswin, :x64_mingw, :jruby]

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1.0" if Gem.win_platform?
