---
layout: page
title: Contributing to DevXOps
---

The DevXops community site is hosted on [GitHub pages](https://pages.github.com) and developed using [Jekyll](https://jekyllrb.com) static site generator such that contributers only need to focus on writing markdown files. The primary consideration for using Jekyll instead of [other SSG](https://jamstack.org/generators/) like NextJS or Gatsby, is the integration with GitHub pages. Jekyll does have good a ecosystem of themes, including the [Doc theme](https://preview.themeforest.net/item/docs-responsive-documentation-manual-jekyll-theme/full_screen_preview/21131076?_ga=2.108511234.1642576812.1652670429-1193949032.1652515315) that we are using.

We are looking for content writers for our community site for writing blog post and also contribute to our documents. In order to contribute, you will need a GitHub account and be able to run Jekyll locally to test how your article looks liking before sending in your pull request.


## Using Jekyll Locally

1. Pre-requisite
- you will need a GitHub account.
- Jeyll requires Ruby. [Install Ruby](https://www.ruby-lang.org/en/documentation/installation/).

2. Cloud the repo
```
$ git clone
```

3. Install Dependancies with [Bundler](http://bundler.io/):
```
$ pwd
$ bundle install
```

4. Generate the site with the following commmand.
```
bundle exec jekyll serve
```

4. The site is now running locally on your computer. Navigate to [http://127.0.0.1:4000/](http://127.0.0.1:4000/).


## Writing a Blog Post


## Contributing to Documentation

```
- title: Getting Started
  docs:
  - introduction
  - onbaording

- title: Azure Landing Zone
  docs:
  - iac

- title: AWS Landing Zone
  docs:
  - awsdesign

- title: Cloud Native Design
  docs:
  - serverless
  - commonservice

- title: DevSecOps
  docs:
  - codescan
  ```

## Pushing Updates to GitHub

