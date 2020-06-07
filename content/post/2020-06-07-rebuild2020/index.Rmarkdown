---
title: Rebuilding this Site, Again, from Near Scratch
author: Robin Donatello
date: '2020-06-07'
slug: rebuild2020
categories: []
tags:
  - ds
  - R Markdown
  - website
subtitle: ''
summary: ''
authors: []
lastmod: '2020-06-07T09:17:03-07:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

The last time I updated this website was in 2017 [link to other post]. I'm taking a full year sabbatical, and so I wanted to start by doing some updates to this site first. This post is a chronicle of my journey, mostly for my reference but also hopefully can help others. Technically I started tinkering about a week ago, but for the most part this post will be my 'real time' thoughts and experiments. 

## List of tutorials
* [Academic theme documentation](https://sourcethemes.com/academic/docs/get-started/)
* Allison hill - [Summer of blogdown](https://summer-of-blogdown.netlify.app/)

## Start: Updating engines
Update all the things!

* Hugo: That's easy, `blogdown::update_hugo` gets me the latest and greatest, version 0.71.1
* Updating the academic theme -- not so easy. Had to start from scratch, but that [seems to be typical](https://community.rstudio.com/t/updating-academic-theme-woes/68224). Hard lesson learned, don't wait 3 years to update. 
* R Studio just came out with 1.3, AND R released 4.0.0 in April. Get those also. 


## Start customization (slowly)
The documentation has been the best starting resource https://sourcethemes.com/academic/docs/get-started/. I want through it slowly, to make sure i'm learning how this new theme fits together. Because FOR SURE the Academic theme is at least twice as complicated as it was 3 years ago. 

### Top level root
The only file to customize here is `config.toml`, and not much to do in here. Here's what I changed: 

* title, copyright, 
* post url: I came across some post, i can't recall where it now, that suggested a change to the URL for posts. The default was something like `/post/:year-:month-:day-:slug/:slug` - where there was a separate folder for the slug. I don't recall exactly, but here's a note from [the blogdown book](https://bookdown.org/yihui/blogdown/configuration.html)


### More top level configuration `config/_default/`
* `languages.toml` didn't need to change as i'm boring old plain english
* `menus.toml` Navbar! Comment out everything I don't need, change the order that it appears using weights. 
> :question: How to right justify? 
* `params.toml` More to do here. 
    - Theme: Green of course. Don't care about font face, but I went with the slightly smaller text ('M')
    - Basic info: Left most of this alone, but specified `site_type = "Person"` 
    - Site features: didn't change these. May do so later. Probably for the `edit pages` part. It depends on if I end up pulling my course materials over. 
> :question: What's the privacy pack? This site sets cookies? Need to look more into what this does. 
    - Contact details: updated all of this
    - Social: Just added Twitter name
    - Regional: changed to 24 hour time - personal preference. 
    - Advanced: Updated `copyright_license` to add a creative commons license since I post course materials and code. 
    - Comments: disabled for now. 
    - Search: defaults are fine
    - Maps: defaults are fine
    - Marketing: default
    - CMS: default
    
## Individual widget level configuration




