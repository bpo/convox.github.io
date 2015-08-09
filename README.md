# Convox Docs

This repo contains the source files for `https://docs.convox.com`.

Documentation is written in Markdown (with options similar to [Github's Flavor](https://help.github.com/articles/github-flavored-markdown/)).

[Middleman](https://middlemanapp.com/) is used to generate static HTML files.

Please let us know about any issues, either via [issues](/issues) or by emailing [support@convox.com](mailto:support@convox.com)

Pull Requests are also welcome!

## Usage

Ruby and bundler are required to run Middleman.

```shell
$ bundle install
$ bundle exec middleman
== The Middleman is standing watch at http://localhost:4567/ (http://127.0.0.1:4567/)
```

Please send updates to documentation as [Pull Requests](/pulls).


### Frontmatter

Each page in the documentation has a header, called frontmatter, this controls where it's displayed and it's title.

e.g.

```
---
title: "Custom Domains"
sort: 40
group: "Getting Started"
---
```

### TOC

All pages are in groups, as specified in the frontmatter, groups are shown in the sidebar navigation in the order they exist in `source/data/toc.yml`.


### Project Structure

```
.
├── Gemfile
├── Gemfile.lock
├── Procfile
├── README.md
├── config.rb
├── data
│   └── toc.yml # table of contents for side navigation
└── source
    ├── assets # contains all layouts, css, javascript and static images.
    ├── documentation
    │   ├── concepts.md
    │   ├── creating-an-iam-user-and-credentials.md
    │   ├── deleting-an-iam-user.md
    │   ├── troubleshooting-apps.md
    │   ├── troubleshooting-install.md
    │   ├── uninstall-convox.md
    │   └── updating-convox.md
    ├── getting-started
    │   ├── custom-domains.md
    │   ├── deploying-an-application.md
    │   ├── environment-variables.md
    │   └── getting-started-with-convox.md
    └── index.md
```
