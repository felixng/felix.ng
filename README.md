## https://felix.ng

[![Build Status](https://travis-ci.org/jekyller/jasper2.svg?branch=master)](https://travis-ci.org/jekyller/jasper2)
[![Ruby](https://img.shields.io/badge/ruby-2.4.2-blue.svg?style=flat)](http://travis-ci.org/jekyller/jasper2)
[![Jekyll](https://img.shields.io/badge/jekyll-3.6.2-blue.svg?style=flat)](http://travis-ci.org/jekyller/jasper2)

My personal [GitHub Pages](https://pages.github.com/) built on [Jekyll](https://jekyllrb.com/) with the [Jasper2](https://github.com/jekyller/jasper2) theme, a full-featured port of Ghost's default theme [Casper](https://github.com/tryghost/casper)

## Getting Started

### Deployment

**Important:**  For security reasons, Github does not allow plugins (under `_plugins/`) when
deploying with Github Pages. This means:

**1)** that we need to generate your site locally (more details below) and push the resulting
HTML (the contents of `_site/` or `../jasper2-pages/`) to a Github repository, that GitHub Pages
then host;

**2)** built the site with [travis-ci](https://travis-ci.org/) (with goodies from
[jekyll-travis](https://github.com/mfenner/jekyll-travis)) automatically pushing the
generated HTML files to a *gh-pages* branch.
This later approach is the one I am currently using to generate the live demo.

**3)** deploy the static website with Jekyll-compatible hosters, such as https://www.netlify.com/, that allow for deployment from the Github repo and publish the website using CDNs. Netlify has a free starter offer.

For option **1)** simply clone this repository (*master branch*), and then run
`bundle exec jekyll serve` inside the directory. Upload the resulting `_site/` (or `../jasper2-pages/`)
contents to your repository (*master branch* if uploading as your personal page
(e.g. username.github.io) or *gh-pages branch* if uploading as a project page
(as for the [demo](https://github.com/jekyller/jasper2/tree/gh-pages)).

For option **2)** you will need to set up travis-ci for your personal fork. Briefly all you
need then is to change your details in *[\_config.yml](_config.yml)* so that you can push
to your github repo. You will also need to generate a secure key to add to your
*[.travis.yml](.travis.yml)* (you can find more info on how to do it in that file).
Also make sure you read the documentation from
[jekyll-travis](https://github.com/mfenner/jekyll-travis). This approach has clear
advantages in that you simply push your file changes to GitHub and all the HTML files
are generated for you and pushed to *gh-pages*. Also you get to know if everything is
still fine with your site builds. Don't hesitate to contact me if you still have any
issues (see below about issue tracking).

### Author Pages

In order to properly generate author pages you need to rename the field *author* in the
front matter of every post to match that of your each author's *username* as defined
in the *[\_data/authors.yml](_data/authors.yml)* file.
With the latest update, multiple author blogs are now supported out of the box.

### Compiling Styles

Following on the way Casper styles are compiled as [described here](https://github.com/tryghost/casper#development):

Jasper2 styles are compiled using Gulp/PostCSS to polyfill future CSS spec. You'll need Node and Gulp installed globally. After that, from the theme's root directory:

```bash
$ npm install
$ gulp
```

Now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.