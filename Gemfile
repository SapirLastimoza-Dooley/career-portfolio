source "https://rubygems.org"

gem "jekyll", "~> 3.8"
gem "duktape"

# Fixes `jekyll serve` in ruby 3
gem "webrick"

group :jekyll_plugins do
  gem "github-pages"
  gem "jekyll-include-cache"
  gem "jekyll-compose"
end

gem 'wdm' if Gem.win_platform?
gem "tzinfo-data" if Gem.win_platform?

gem 'jekyll-theme-hydejack', '~> 9.1', '>= 9.1.6'