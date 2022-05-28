---
layout: page
title: Contributing to DevXOps
---

The DevXops community site is hosted on [GitHub pages](https://pages.github.com) and developed using [Jekyll](https://jekyllrb.com) static site generator such that contributers only need to focus on writing markdown files. The primary consideration for using Jekyll instead of [other SSG](https://jamstack.org/generators/) like NextJS or Gatsby, is the integration with GitHub pages. Jekyll does have good a ecosystem of themes, including the [Doc theme](https://preview.themeforest.net/item/docs-responsive-documentation-manual-jekyll-theme/full_screen_preview/21131076?_ga=2.108511234.1642576812.1652670429-1193949032.1652515315) that we are using.

We are looking for content writers for our community site for writing blog post and also contribute to our documents. In order to contribute, you will need a GitHub account and be able to run Jekyll locally to test how your article looks liking before sending in your pull request.


## Using Jekyll Locally

1. Pre-requisites:
- you will need a GitHub account.
- Jeyll requires Ruby. [Install Ruby](https://www.ruby-lang.org/en/documentation/installation/).

2. Cloud the repo:
```
$ git clone https://github.com/htxsg/htxsg.github.io.git
```

3. Install Dependancies with [Bundler](http://bundler.io/):
```
$ cd htxsg.github.io/docs
$ bundle install
```

4. Generate the site with the following command:
```
$ bundle exec jekyll serve
```

4. The site is now running locally on your computer. Navigate to [http://127.0.0.1:4000/](http://127.0.0.1:4000/).


## Registering as a contributor

1. Go to the **authors** section in  `_config.yml` to insert your record. The key will be the short name for example `panyong`.
```
    panyong:
      name:         Ng Pan Yong
      title:        The Cloud Guy    
      avatar:       avatar-py.jpg
```

2. Place your avatar in the directory `/htxsg.github.io/docs/uploads/`.


## Writing a Blog Post

1. Blog should be written in markdown format.

2. Name your file yyyy-mm-dd-\<name\>.md

3. Add Front matter to the start fo your markdown file. Here's an example:

```
---
title: Developer Machine
author: panyong
categories: [news, updates]
tags: featured
---
```

4. Place your markdown file in the directory `/htxsg.github.io/docs/_posts/`.

## Contributing to Documentation

1. Doc should be written in markdown format.
   
2. Add Front matter to the start fo your markdown file. Here's an example:

```
---
title: AKS Provisioning Error due to NSG
subtitle: Issues encountered during the setup AKS in Level 4 using CAF codes.
author: panyong
tags: [AKS, Troubleshoot]
---
```

3. Place your markdown file in the directory `/htxsg.github.io/docs/_docs/`. 

4. Edit the YAML file `/htxsg.github.io/docs/_data/navigation_docs.yml` to reference new file in the side navigation bar.

```
- title: Azure Troubleshooting Guides
  docs:
  - AKS-Error-NSG
```

[More Information](https://preview.themeforest.net/item/docs-responsive-documentation-manual-jekyll-theme/full_screen_preview/21131076?_ga=2.108511234.1642576812.1652670429-1193949032.1652515315)

## Join as Contributor
[Sign Up](https://go.gov.sg/joindevxops) and we will get back to you.