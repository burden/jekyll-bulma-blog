# jekyll-bulma-blog

> A fully-featured blog boilerplate for Jekyll made extraordinary with the help of Bulma.

**[Demo](https://jekyll-bulma-blog.burden.cc/)**

### Blog Features

- Smart navigation knows which page is active
- Contact form: Formspree (redirects back to your "thank you" page)
- Categories can have captions
  - The `categories` frontmatter behaves as a slug
- Categories and tags can have descriptions, shown on archive pages
- Featured blog post
  - note: first post is used if nothing is specified
  - SEO tags
  - Sitemap
- Archive pages for categories, tags, and year.

## Boilerplate Features

- [Bulma 0.7.4](https://github.com/jgthms/bulma/tree/0.7.4)
- Dependency management: [yarn](https://yarnpkg.com)
- Asset pipeline: [jekyll-assets](https://rubygems.org/gems/jekyll-assets)
  - [JS uglifier](https://rubygems.org/gems/uglifier/versions/3.2.0)
- HTML compression: [compress.html](http://jch.penibelst.de/)
- Testing: [html-proofer](https://github.com/gjtorikian/html-proofer)
- Analytics: [Google Analytics](https://www.google.com/analytics/)

## Dependencies
Your development environment should have ruby and the gem package manager setup already.

1. Install bundler `gem install bundler`
2. Install [yarn](https://yarnpkg.com/en/docs/install)

## Getting Started

```6235d7e5f0f3a49f9b3530b4781ac879a8ba2386
$ bundle install
$ yarn install
$ bundle exec jekyll serve
```

## Usage

### Add obfuscated email address
```sh
$ bundle exec rake email
Please type in an email address then press ENTER/RETURN
contact@example.com

Installation:
Update src/_config.yml with the following pairs.

email-key: d05fIsWcv61GbThaN3FkOuL9mHXVnYgBQJUR8r2S7DizwKexqtAZMCP4Eoplyj
email-encoded: XhxWUXW@fIUzaNf.Xhz
```

### New post
```
$ bundle exec jekyll post "Hello beautiful world"
```

## Deploy to Github Pages from Travis
1. Point Travis to repository
2. Configure Travis
3. Generate a [Personal Access Token](https://github.com/settings/tokens) from Github
  - The only scope needed is repo:public_repo
4. Set `GITHUB_API=<token>` on Travis
  - Make sure `Display value in build log` toggle is set to `Off`!
