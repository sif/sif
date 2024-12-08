---
layout: post
title: "How the Projects Are Built"
categories: projects
tags: sifer_aseph afterlife_song sites project skunkworks
---

* TOC
{:toc}

Short post.

## Building Afterlife Song

I just used <a href="https://pages.github.com">GitHub Pages</a> and set the theme to <a href="https://github.com/jekyll/minima">Minima</a>. That was mainly it.

Minima is a minimalist Jekyll theme. Jekyll is a static site generator written in Ruby. It uses the Liquid template language to generate the site files, meaning Liquid serves as the web templating system. 

Don't do this: `brew install ruby`

To install chruby: `brew install chruby`

To run it locally:

```
source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh
chruby 3.2.2
bundle exec jekyll serve
```

For tagging, I followed <a href="http://www.jasonemiller.org/2020/12/23/tagging-posts-in-jekyll-minima.html">this</a>.



<img src="https://github.com/sif/sif/raw/main/files/post_files/side-project.jpeg" />
