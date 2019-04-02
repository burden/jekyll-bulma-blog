# jekyll-bulma-blog

> A full-featured blog boilerplate for Jekyll made extraordinary with the help of Bulma.

**[View Demo](https://jekyll-bulma-blog.burden.cc/)**

![jekyll-bulma-blog](https://raw.githubusercontent.com/burden/jekyll-bulma-blog/master/screenshot.png)

### Blog Features

- Categories can have captions
- Smart navigation knows which page is active
- Archive pages for categories, tags, and year.
  - Categories and tags pages can have descriptions
- Atom feed
- Featured blog post
  - note: first post is used if nothing is specified.
- Basic SEO
  - schema.org (Website)
  - open graph
  - sitemap.xml
- Contact page
  - Honeypot and reCAPTCHA implemented to thwart spam-bots
- Display your email address
  - Your email is protected from spam-bots by using obfuscation
- Create and edit blog posts with [Prose CMS](https://prose.io)
    
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

```
$ bundle install
$ yarn install
$ bundle exec jekyll serve
```

## Usage

### Add your email address

```sh
$ bundle exec rake email
Please type in an email address then press ENTER/RETURN
contact@example.com

Installation:
Update src/_config.yml with the following pairs.

email-key: d05fIsWcv61GbThaN3FkOuL9mHXVnYgBQJUR8r2S7DizwKexqtAZMCP4Eoplyj
email-encoded: XhxWUXW@fIUzaNf.Xhz
```

### Contact Page

The contact page uses Formspree.io by default, unless deploying to Netlify.

Some things to consider
- 100 free submissions per month
- Upon submission, it will Redirects you to thank you page (see thanks.html)
- No registration required

When deploying to Netlify, the blog will automatically integrate with Netlify Forms. If you still prefer to use Formspree.io, simply change the `site.contact.page.service` block to `formspree`

If you don't have access to `rake` or you don't care to obfuscate your email address, you can choose to display your email in plaintext by inputing your address in the `site.contact.email-plain` block. 


### Content Management

#### Command Line

```
draft      # Creates a new draft post with the given NAME
post       # Creates a new post with the given NAME
publish    # Moves a draft into the _posts directory and sets the date
unpublish  # Moves a post back into the _drafts directory
page       # Creates a new page with the given NAME
```

**Create a post**
```
$ bundle exec jekyll post "Hello beautiful world"
```
For more examples and configuration options be sure to check out the `jekyll-compose` [repo](https://github.com/jekyll/jekyll-compose) 

#### Prose
Prose is an open source web-based authoring environment for CMS-free websites and designed for managing content on GitHub. Use it to create, edit, or delete files.

Prose has advanced support for Jekyll sites and markdown content. Prose detects markdown posts in Jekyll sites and provides syntax highlighting, a formatting toolbar, and draft previews in the site's full layout.

Please note that Prose only has access to the `src/_posts` directory. 

**Instructions**:  
[Click here to authorize](https://prose.io) access to Github.

Be sure to check out the Prose [repo](https://github.com/prose/prose), and [wiki](https://github.com/prose/prose/wiki/Prose-Configuration) for more information.

### Configure Categories and Tags

This blog comes complete with Category and Tag pages thanks to the `jekyll-archives` plugin.

 `src/_data/catalog.yml`

You can change where Category and Tag pages are saved by editing the `jekyll-archives.permalinks` block in `_config.yml`

#### Configure Prose CMS
After editing your categories, you will need to update the prose block in `_config.yml`
```
prose:
  ...
  metadata:
    src/_posts:
      - name: "category"
        field:
          options:
            - name: "Category 1"
              value: "category1"
```

## Deploy

### Deploy to Github Pages from Travis

1. Point Travis to repository
2. Configure Travis
3. Generate a [Personal Access Token](https://github.com/settings/tokens) from Github
  - The only scope needed is repo:public_repo
4. Set `GITHUB_API=<token>` on Travis
  - Make sure `Display value in build log` toggle is set to `Off`!

### Deploy to Netlify  

  [![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/burden/jekyll-bulma-blog)
  
  #### Wait, what happens when I click that button?

  Good question. Here's what it will do...

  1. Netlify will clone the git repository of this project into your Github account. This action will require your permission from Github, and of course a Netlify account. 
  2. Netlify will then create a new site for you, and configure it to use your shiny new repo. Right away you'll be able to deploy changes simply by pushing changes to your repo.
  3. Enjoy your new blog 🎉