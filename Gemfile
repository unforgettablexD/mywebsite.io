source "https://rubygems.org"

# gem 'jekyll', '~> 4.3.4'
# GitHub Pages gem (includes Jekyll and other plugins)
gem "github-pages", group: :jekyll_plugins
gem 'bundler'
gem 'faraday-retry'
gem 'backports'
gem 'kramdown'
gem 'puma'
gem 'csv'
gem 'base64'


# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
# gem "github-pages", group: :jekyll_plugins
# you can read more about it here 
# https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll
# https://pages.github.com/versions/

# Plugins
group :jekyll_plugins do
    # gem 'devlopr'
    gem 'jgd'
    gem 'jekyll-feed'
    gem 'jekyll-paginate'
    gem 'jekyll-gist'
    gem 'jekyll-seo-tag'
    gem 'jekyll-sitemap'

    # gem 'jekyll-admin',
end


# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
  gem "tzinfo"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.2.0", install_if: -> { Gem.win_platform? }
gem "webrick"
gem "ffi"
