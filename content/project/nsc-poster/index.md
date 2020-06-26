---
title: College of Natural Sciences Poster Session
author: Robin Donatello
date: '2018-05-29'
slug: nsc-poster
categories: []
tags:
- Data-Science
summary: 'Streamlining abstract submission, processing, and judging for the annual College Poster Session at CSU, Chico. Pipeline uses Google Forms, R, Markdown, Sweave, LaTeX, GitHub, and Shiny. '
authors: []
external_link: ''
image:
  caption: ''
  focal_point: ''
  preview_only: yes
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''
slides: ''
---


The annual College of Natural Sciences Poster Session is an established event where students, faculty and clubs have the opportunity to present their original research or student activities to the College, University and Chico Community. See more about the College Poser Session Event at the [College of Natural Sciences Poster Session event page](https://www.csuchico.edu/nsci/event/poster.shtml). 

This project streamlined the submitted abstract processing, and provided the authors with a website to view their submission. Another result from this project was the creation of a judging app that reduced the burden of vote tallying for multiple categories, provided real-time score graphs, and an instant display of winner titles and authors.


### Abstract Submission processing

Abstracts are submitted using Google Forms. They are then processed using R (`googlesheets`, `stringr`, `dplyr`), turned into a webpage using `rmarkdown` with a few fancy visual aids using `ggplot2` and `kable`. 

The webpage is re-built nightly during the open abstract submission period and can be seen here: https://norcalbiostat.github.io/CNS-Poster-Session/

After the abstract submission period closes, the poster ID's are finalied and abstracts reviewed by members of the poster session committee. The `rmarkdown` file gets compiled to PDF format and turned into a [program booklet](https://www.csuchico.edu/nsci/_assets/documents/NSC-poster-session-2018-abstract-booklet.pdf) with only minimal manual processing of latex symbols. 

### Judging Shiny App
https://norcalbiostat.shinyapps.io/CNSPosterJudgingApp/ 

The app was originally created for the 2017 session by Aaron Shaffer [@ClassicSours](https://github.com/ClassicSours), and updated by me for 2018. Feel free to play around, the data is not stored on app shutdown. The poster ID's are listed on the abstract website. 

This judging app 

* reduced the burden of vote tallying for multiple categories (judge votes, peoples choice)
* showed real-time vote scoring results as bar charts that could be viewed by anyone with the link (committee members only) during the session (an unexpected but amusing side-result)
* provided an instant display of winning poster titles with authors to be read off by the Dean during the awards ceremony (a mere 30 minutes after the voting period closes)
* allowed for the download of merged voting data so
    - certificates could be made via mail merge by the next day
    - The [Gateway Scinece Museum](http://www.csuchico.edu/gateway/) has the contact information for authors for whom their posters have been chosen to be displayed in the Museum over summer. 
