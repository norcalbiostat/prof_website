---
title: Rebuilding this Site, Again, from Near Scratch
author: Robin Donatello
date: '2020-06-07'
slug: rebuild2020
categories: []
tags:
  - DS
  - R Markdown
  - blogdown
  - hugo
subtitle: 'An annual adventure'
summary: ''
profile: false
editable: false
authors: []
lastmod: '2020-06-07T09:17:03-07:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

The last time I updated this website was in 2017 [link to other post]. I'm taking a full year sabbatical, and so I wanted to start by doing some updates to this site first. This post is a chronicle of my journey, mostly for my reference but also hopefully can help others. Technically I started tinkering about a week ago, but for the most part this post will be my 'real time' thoughts and experiments. _Edit: This is also serving as a self-reference "how did I do that?"_

## List of tutorials that helped me
* [Academic theme documentation](https://sourcethemes.com/academic/docs/get-started/)
* Allison hill - [Summer of blogdown](https://summer-of-blogdown.netlify.app/)
* A [community of users](https://spectrum.chat/academic/help?tab=posts)

## Start: Updating engines
Update all the things!

* Hugo: That's easy, `blogdown::update_hugo` gets me the latest and greatest, version 0.71.1
* Updating the academic theme -- not so easy. Had to start from scratch, but that [seems to be typical](https://community.rstudio.com/t/updating-academic-theme-woes/68224). Hard lesson learned, don't wait 3 years to update. 
* R Studio just came out with 1.3, AND R released 4.0.0 in April. Get those also. 


## Start customization (slowly)
The documentation has been the best starting resource https://sourcethemes.com/academic/docs/get-started/. I want through it slowly, to make sure i'm learning how this new theme fits together. Because FOR SURE the Academic theme is at least twice as complicated as it was 3 years ago. 

### Top level root
The only file to customize here is `config.toml`, and not much to do in here. Here's what I changed: 

* title: this shows up in the top left of the navbar, and your browser tab. 
* copyright: shows up at the bottom of every post & project
* post url: I came across some post, i can't recall where it now, that suggested a change to the URL for posts. The default was something like `/post/:year-:month-:day-:slug/:slug` - where there was a separate folder for the slug. I don't recall exactly, but here's a note from [the blogdown book](https://bookdown.org/yihui/blogdown/configuration.html)


### More top level configuration `config/_default/`
* `languages.toml` didn't need to change as i'm boring old plain english
* `menus.toml` Navbar! Comment out everything I don't need, change the order that it appears using weights. 
    - See here for [dropdown menu items](https://sourcethemes.com/academic/docs/get-started/#menu)
    
> :question: How to right justify? 

* `params.toml` More to do here. 
    - Theme: Green of course. Don't care about font face, but I went with the slightly smaller text ('M')
    - Basic info: Left most of this alone, but specified `site_type = "Person"` 
    - Site features: didn't change these. May do so later. Probably for the `edit pages` part. It depends on if I end up pulling my course materials over. 
    - Contact details: updated all of this
    - Social: Just added Twitter name
    - Regional: changed to 24 hour time - personal preference. 
    - Advanced: Updated `copyright_license` to add a creative commons license since I post course materials and code. 
    - Comments: disabled for now. 
    - Search: defaults are fine
    - Maps: defaults are fine
    - Marketing: default
    - CMS: default

> :question: What's the privacy pack? This site sets cookies? Need to look more into what this does. 

## [Introduce yourself](https://sourcethemes.com/academic/docs/get-started/#introduce-yourself)
The `content/authors/admin/_index.md` file controls the 'About me' section of the page. It has your avatar on the left, social icons underneath and a spot to the right for a paragraph of info. 

* You can't do markdown style links, but you can display URLs. 
* As you add more social icons to the space below your mugshot, the sizes automatically get smaller. Would be nice to have the option to wrap onto a second line. 
* The `avatar.jpg` goes in the same folder. 
* If you want an icon to show on your browser tab, put `icon.png` in `assets\images`.


## Host on Netlify
I don't recall where along this process I pushed to git and deployed on Netlify. It was for sure before i got too far down the customization rabbit hole. Don't forget to [specify your hugo build](https://bookdown.org/yihui/blogdown/netlify.html) - mine was 0.70.0 (need that last decimal).

## Remove widgets 

Unlike the 'delete all the things' approach that [Danielle Navarro](https://djnavarro.net/post/starting-blogdown/) takes, i'd rather just turn them off. 

Inside the `content/home` directory, there's all these `.md` files. Each one is a widget, and by default most of these are set to `active=true`. I turned most of them off, but I may turn some back on later. Supposedly you can have [widgets enabled on other pages](https://sourcethemes.com/academic/docs/managing-content/#create-a-widget-page), not just this landing/home page. I'll look into that later. Baby steps, start small then add incrementally. Like a `ggplot`, layer it on. 

## Adding content

### Projects
I already had a blogdown site that included projects. Migrating those over to this new format wasn't terrible. 

* Under `/content/project`, each project has it's own folder. 
    - Within each folder there is an `index.md` file. 
        - Each `index.md` file has a large YAML header section, 
* Modify the `content/home/projects.md` file to 
    - set the `[[content.filter_button]]` to add tag filters
    - set the display of projects (cards vs lists)

### Courses
Previously, I simply had separate 'simple' RMarkdown websites for my class pages [[ex Math 130]](https://norcalbiostat.github.io/MATH130/), and I linked to them from my main page. However, Academic has a whole different page layout called _docs_ for [writing and sharing documentation](https://sourcethemes.com/academic/docs/managing-content/#create-a-course-or-documentation), such as course materials. 

* In `content/courses`, there's an overall `_index.md` which is pretty plain, has the `docs` layout (which i gather is the important part) but this is where you can add some introductory text. that would apply to all courses. 

* Each course has it's own folder, which of course has their own `_index.md` files. These will automatically show up on the courses page, with a short summary that you specify in the course specific index md file. 

:question: Can i add direct links to these courses as a drop down in the navbar? 

The only thing i've done here so far is setup placeholder entries for 2 of my classes. 

### Blog posts 
This is about when I decided I needed to document what I was doing, and started this blog post. I did so by using the RStudio Addin, _New Post_. While most of the writing is just text, I opted for a `.Rmarkdown` file.

:question: What's the difference between `.Rmd` and `.Rmarkdown`

R code still works right? 

```r
2+2
```

```
## [1] 4
```

Okay, i'm tossing the blog posts that came along with the example/template files. Before I migrate my old posts over, time to re-read the ['Spoonful of Hugo' post by Allison Hill on page bundles](https://alison.rbind.io/post/2019-02-21-hugo-page-bundles/). Because there was something about the way posts are handled that is different from 'old' Hugo. 

Ah! This is where I got the info about the slug from!

**Attempt 1.**
* Make a new folder using the `YYYY-MM-DD-slug` format, and put my old `.Rmd` file into this folder, renaming it as `index.Rmd`. 
* Copy the YAML material from this page into that one. 
* Won't render -- because i was doing things with data and that data was stored under `../../static/data/`.. which is what the page bundles are designed to deal with. 
    - Move data into folder where the rmd file is at, and update path. 
    - This would be a HUGE PAIN if I had a lot of these... 
* Worked! okay.. not bad at all. 

**Attempt 2.** Too many manual steps above.
* Copy `.md`/`.Rmd` into `content/post`.
* Make a new folder
* Use copy/paste magic to rename folder the same as the prior post
* Rename content file `index`
* Use Rstudio Addin to _Update Metadata_

Serve site and... well turns out you don't even need that last step. Okay better. Posts are done. 

##### [Page features](https://sourcethemes.com/academic/docs/managing-content/#page-features)

* Turn off profile blurb that shows at the bottom of each post. Not necessary/desired for a single author page. You can also toggle off `reading_time`, `share`ing links, `commentable` and `editable`. 

:exclamation: You -can- Knit your `.Rmd` file to see what it looks like while working on it, just delete it before you save. It'll get re-rendered when you build site, in the 'proper' format that's needed for display on a Hugo based website. 


> :question: Each post has a "last updated on", and it's the date i 'created' the file - which in the case of this website update it's saying June 11, 2020. That's not the date i want to show. I've messed with the `date` and the `lastmod` date in the YAML header.. i've tried quotes and no quotes, i've tried updating the metadata. Nothing. 


### Publications

Interesting change. Before, this was just a folder containing one `.md` file per pub. The Academic theme now has three subfolders, `conference-paper`, `journal-article` and `preprint`. The examples for each are really good to keep, so I "commented out" each pub by renaming `index.md` to `_index.md` and changed the folder name to `example-`

> :question: - this doesn't remove it from the citation list. If you do the 'filter by pubs' they still show up. Hmm, how is this list built? 

For now i'm going to edit the `content/home/publications.md` to remove the alert note. While i'm here, i'm also modifying the view to a 'card' view.. not list. This way shows the full abstract, and the pub year (compact does not)

Lots of features here. If you're a python user, you can create a pub list based on a `.bib` file. For each pub you can also add a `cite.bib` file that ppl can use to easly get your citation. See the [docs page](https://sourcethemes.com/academic/docs/managing-content/#create-a-publication) for details. 

Now this is a ton of work to update :(

### Talks

* Same structure as publications. 
* `content/talk/` - one folder per topic
    - `index.md` in each folder 
* Old content files seem to work seamless also! 
  - Rename the old `YYYY-MM-DD-talk-title.md` to `index.md`
  - missing probably lots of customization pieces, but easy to do a simple migrate.
* files: `talk/folder/file` - no relative paths. 
* TOML vs YAML Hell.  TOML uses +++ at the top, YAML uses ---. TOML uses `=`, YAML uses `:`. And none can the two comingle. 

:question: how to get rid of the timestamp? 
:question: how to get rid of author bio at the bottom of the talk. This was an earlier question also. 

* **Conference Talks**
    - The `date` on line 4 is the start of the conference, the `enddate` is the last day. Remove the time, and set `allday` to `yes`. 

## Additional Content/Sections

I want to work on adding sections for the following areas. 

* Academic Advising (blog post template)
    - General info on letter of reference requests
    - Statistics/DS program guide
    - Academic life? 
    - Choosing graduate school? 
* Project advising (project template)
    - A place to showcase the work students are doing
    - Highlights the students work
    - Acts as a recruitment tool for prospective students. 
    - MS students: committee member only? - This could get really big. 
    

## Making a new section
I want a section on the homepage for teaching. I think I'm okay with just having a list like my old site, so I just copied `content/home/demo.md`, renamed it as `teaching.md`, then copied the content in from the old site widget. 

* Going to need subpages for this. Courses/Notebook/Data/Workshops... 


## Featured images

You'd think that adding a link to `image` into this section of the header would work, but no. 
```
header:
  caption: ""
  image: 
```

Add this to the header instead.
```
image:
  placement: 1
  caption: "test"
```

Read more [here](https://sourcethemes.com/academic/docs/managing-content/#featured-image). 

## Adding a student page
I did this using by creating a [new widget page](https://sourcethemes.com/academic/docs/managing-content/#create-a-widget-page)

* Make new folder under `content/` called `students/.`
* Add `index.md` 
* Move the `people.md` widget out of `home/` into `students/`
* Each person gets a folder under `/content/authors` - and is assigned to a `user_group`. 
    - This display is adjusted in the `people.md` file. 
* add a `weight: <number>` to the header after `title` to control order. [ref](https://github.com/gcushen/hugo-academic/issues/1080#issuecomment-528684130)

## In closing

That's it for now. I'll write more about the process of adding courses later, as I figure it out. 


