---
title: Guidelines for Creating a Good Scientific Poster
author: Robin Donatello
date: '2022-11-26'
slug: poster-guidelines
categories: [professional]
tags: []
subtitle: ''
summary: ''
authors: []
lastmod: '2022-11-26T10:33:34-08:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []

---


This post contains general guidelines on how to make a scientific poster. You should always check the standards and requirements for the specific conference, site or session where you will be presenting. _Updated 11-2023_

# Quick links to content on this page

* [Templates](#templates): Templates so you don't reinvent the wheel. 
* [Content](#content): Sections within the poster
* [Aestetics](#aesthetics): Font, tables, graphics, colors, logos, 
* [Printing](#printing): Guidance, location and prices
* [Evaluation](#evaluation-criteria): grading rubric
* [Examples](#examples): Selected examples with comments. 

# Templates

Powerpoint templates are the current standard method for creating scientific posters in many fields. 

* [Powerpoint template](http://www.posterpresentations.com/html/free_poster_templates.html). 
    - Trifold tabletop templates are seldom used. 
    - Common sizes are 36" x 48"
    - Choose either a three, or four column layout by following the instructions along the right sidebar. 
* Chico State Biology Student Research Symposium posters tend to be 4'x3'. See the 2022 [[event page here]](https://www.csuchico.edu/biol/events-seminars/student-research-symposium-2022.shtml) for guidance and templates. 

## Collaboration

* If you are working with a partner on this project, you can upload your powerpoint template to Google Drive. It will keep the correct scaling and allow you to simultaneously edit the file.



# Content
The following sections of information must be included in each poster. The choice of design, boxes, columns is up to you. The direction of the story should go top to bottom, then left to right. Read in columns, not rows. 

1. **Title**
    - Author list should have the form _Last, MI., First, Last, MI. First_ (last name, middle initial (optional), first initial or name)
    - Affiliations can be listed many ways. Your best bet is to look at other posters presented at the same event form a prior year. For a class project, simply state your year, class and section number. 
2. **Introduction**
    - Probably the only part that will be in paragraph form. 
    - This is your lead-in, the part that sets the stage for your analysis. 
    - Limited background and lit review go here also. 
    - Your research hypothesis should be clearly stated here. 
3. **Methods (Data collection and analysis)**
    - Where did your data come from?
    - Clearly state the variables that you are using, and any major recoding done (truncation, subsetting). 
    - Describe the statistical analysis methods you used. 
    - Include a sentence about what variables were tested as moderators and/or confounders. 
4. **Sample characteristics**
    - This is where _Table 1_ goes, a concise univariate description of your sample. 
    - Analysis sample size, N(%) for each categorical variable, mean(sd) (or mean/median) for each continuous measurement. 
    - Could be a candidate for [tbl_summary](https://www.danieldsjoberg.com/gtsummary/articles/tbl_summary.html)
5. **Results**
    - No more than 2 graphs or tables for bivariate comparisons
    - One multivariate table or plot. Here are some options
        - [tbl_regression](https://www.danieldsjoberg.com/gtsummary/articles/tbl_regression.html)
        - The `coefplot()` function in the `arm` package. [Example](https://friendly.github.io/VisMLM-course/examples/coefplots-demo.html)
        - [Forestplot](https://cran.r-project.org/web/packages/forestplot/vignettes/forestplot.html)
        
    - At least one coefficient, the primary explanatory variable, must be interpreted in context of the problem. 
    - You are just stating results here, not justifying, explaining or connecting any meanings. 
6. **Conclusions/discussion**
    - Summarize results in English sentences
    - Draw and describe the big picture conclusions. Connect the breadcrumbs discussed in the results section. 
    - Make sure every statement here is backed up with evidence shown in the results. 
7. **Implications**
    - Why should someone care about this research? 
    - Connect to current research. Possibly more citations here. 
8. **References**
    - Font size can be reduced to 8 or 6 minimum. 
9. **Acknowledgements & Contact info**
    - Any help you received from a person not listed as an author should be acknowledged.
    - You do not need to acknowledge your instructor for class projects.
    - The first author should include their contact email. 
    - If you have no acknowledgements, you can stick your email address in the bottom right corner as a footer. 


# Aestetics

### Font size
* Readable from 10 feet
* This tends to be at least 20-24 pt font. If using a template, stick with their defaults. 
* If presenting an e-poster err on the side of larger font, upwards of 30
* Bullets vs. Paragraphs: Pretty field specific. 
    - Often the introduction or abstract is the same paragraph used when submitting the abstract for consideration. 
    - Walls of text tend to not be read. 
* White space: Also somewhat field specific. You want the poster to be readable and eye catching. 


### Tables
* Build them in PowerPoint tables directly
* Use borders for the top, and bottom of the table
    - Use vertical borders sparingly. Probably only for the far left corner. 
    - Powerpoint has some good auto-formats you can use. 
* New (but untested) option as of 2023 - create regression tables using [tbl_regression](https://www.danieldsjoberg.com/gtsummary/articles/tbl_regression.html#gt-functions-to-format-table), then save as an image using [gtsave](https://gt.rstudio.com/reference/gtsave.html)

### Graphics
* Copy/pasted graphics do not scale up well and will print out very pixelated or blurry. 
* Guidance for using R: Finalize the plot, save it to an R object, then use `ggsave` to save the image to a file on your computer. Then import this plot into your powerpoint. 

```
plot1 <- ggplot(mtcars, aes(x=mpg, y=wt)) + geom_point() # save the plot
ggsave(plot1, # name of the plot
        "mtcars.pdf", # name of the file. This will export to your working directory. 
        width = 6, height = 6, units = "in") # size of the plot
```

* Always best to save the file larger rather than smaller, then manually shrink down in PPT
* You can increase the base size of text in your graphic (so it looks reasonable once you export) by adding a `base_size=` argument to your `theme()`. I would suggest starting at 18. I.e.: `theme_bw(base_size=18)`
* Want to see what it'll look like when scaled up? If you plan on getting your poster printed at twice the size of the file, make sure you zoom to 200% when checking that images look crisp.

### Campus Logos
Your poster is a professional publication. It should reflect your campus properly and following guidelines (where they are listed). Every campus has official logos, colors and instructions on how to correctly use these. Below I have linked the ones I could find for Chico State. 

* [[University Naming]](https://www.csuchico.edu/style-guide/visual/naming.shtml)
* [[Color Palette]](https://www.csuchico.edu/style-guide/visual/colors.shtml)
* [[Logo and Seal]](https://www.csuchico.edu/style-guide/visual/logos.shtml)
    - Note that certain logos are restricted for Athletics, or for official use. Use the institutional logo, or the institutional wordmark. 


### Colors in plots
* Colors are good - but stick to a theme/pallet. 
    - Make the colors meaningful. 
    - https://www.w3schools.com/colors/colors_groups.asp
    - http://paletton.com
* R Cookbook guide for colors in ggplot2: http://www.cookbook-r.com/Graphs/Colors_(ggplot2)/ 



# Printing (as appropriate - prices are as of 2022)

* Don't wait until the morning of to print - this is ESPECIALLY true in Spring when there are multiple poster symposiums being conducted. 
* Don't spend a fortune!
* **Recommended option** Copy & Print center in the Library [website](https://www.csuchico.edu/copycenter/index.shtml). Prices range from $20 (18"x24") to $72 (36" x 48")
* Staples $65
* Ellis Art (Esplanade) $50-60


# Evaluation Criteria
This is a general set of criteria commonly used to score posters. 

* **Appearance**
    - Display attracts viewer's attention.
    - Words are easy to read from an appropriate distance.
    - Poster is well organized and easy to follow.
    - Graphics and other visuals enhance presentation.
    - The poster is neat and appealing to look at.
* **Content**
    - Purpose of model (question being addressed) is stated clearly.
    - I understand why someone might be interested in the model results.
    - There is enough detail about methods (e.g., creating new variables) for me to understand the model and results.
    - The sample characteristics are fully described.
    - The approach taken is appropriate for the problem and technically sound.
    - Conclusions are stated clearly.
    - Conclusions are supported by model results.
    - Limitations of the study are clear. 
* **Presentation** 
    - Presenter's response to questions demonstrated knowledge of subject matter and project
    - The presenters conducted themselves professional during the presentation.
    - It was clear that all team members understood what was being presented and had an equal contribution to the data analysis. One member did not dominate the presentation and questions.
    
    


# Examples

This [Google Drive](https://drive.google.com/drive/folders/17KzZcFXnTevOi_hlVVNmdFPW_ngdqhFA) folder contains a selection of sample posters, from professional conferences, graduate and undergraduate class projects. Class projects have comments regarding what made them stand out, and what could be improved. 

## Professional Conferences

Professional Conference Presentations

* [Patterns of Sexual Experience Among an Urban Sample of Latino and African-American 9th Grade Students](https://drive.google.com/file/d/1bP-tZ1xMxeQ2vCXQDU3Hd0Un0p8fneC4) _Jeffries, RA., De Rosa, CJ., Moulton, B., Chung, EQ._
* [Sexual Identity and Associated Factors Among and Ethnically Diverse Sample of 9th Grade Public School Students](https://drive.google.com/file/d/153AHv6DArv7T3RvnjqFIWgvGAFrlmPFK) _Viola, R., Jeffries, RA., Moulton, B., De Rosa, CJ._
* [Pre-sexual behaviors as predictors of sexual risk in adolescents: Examining alternate outcomes in sexual health education programs](https://drive.google.com/file/d/1PukWu4HzfajVowyd_CBxS5UgZCM58gVx) _Moulton, BD., Donatello, RA., Rohrbach, L., Afifi, A., Meyer, KI., Leon, P., Lau, C._
* [Implementing a Flipped Classroom and Active Learning Techniques in General Chemistry to Augment Student Success at a Mid-Sized Rural University](https://drive.google.com/file/d/1LpsfwslrEUvZ9btRL379FhIJRIFflxg4) _Smith, M., Aguilar, R., Cherrette, V., Rose, A., Crane, J., Park, C., Bladorn, E., Mills, H., Sherry, S., Chatha, C., Park, H., Dailey, H., Donatello, RA., Wasinger, E._
* [The Impact of Supplemental Instruction on Student Success](https://drive.google.com/file/d/1YopFzpGNAqPfz_xLpwPK59IJvd6EF9o1) _Aguilar, R., Donatello, RA._


## Graduate class projects 

* [Relationship Between Alcohol Consumption and Among Gender and Age Groups](https://drive.google.com/file/d/1i2d5LqhB4zGaR6B-OeymCJninzUKw7AY) _Gonzales, J._
    - Good tables, could use larger font. 
    - Clearly stated research questions
    - Good balance of white space. Not entirely walls of text. 
* [Species-specific tree leaf comparisons in the absence of bird predation on caterpillars](https://drive.google.com/file/d/1myM_nrJP3bMW4TJvW9RqHM8DQ3VEOLz) _Parker S._
    - Excellent use of whitespace, balanced colors. 
    - Great table 1, bullet point results make it easy to read.
* [Effects of Childhood Social Support on Trauma](https://drive.google.com/file/d/1fHWFihLqhBBzedDIzVNYdxk4dN1WAxys) _Hostler, M., Thornton A., Wong R._
    - Clearly laid out variables of interest and RQ's. 
    - Good use of pie charts. 
    - The 3D scatterplot is not helpful. 
    - Model results presented in a nice table, but not explained. 
* [Using 2010 U.S. Census Demographics to Determine a Predictor for Beer and Wine Consumption](https://drive.google.com/file/d/1dcu7LBIyn-_BCOPNulztPSYzJBEBpeSQ) _Ellis, C., Esposito, C., LaGrange, A._
    - Great use of maps, model comparison table in the bottom middle. 
    - Bullet points clear and easy to read. 
    - Univariate summary statistics very clearly laid out. 
* [Moving away from BMI](https://drive.google.com/file/d/1dtJlamveAIQ0O37OnAVCbhBlDQN74gGR) _Brooke, C., Coronoa, J., Kessner, Sl, Lona, I._
    - Great modification of base plots to tell a story. 
    - Good use of middle two columns to explain two separate outcomes. 
    - Clean tables, sufficient whitespace


## Undergraduate class Projects

* [The Associations Between Familial Relationships, Daily Activities and Delinquency in Adolescents](https://drive.google.com/file/d/1rMn9o8jVSzL3mAwK9eeHnAXy_631PPsH) _Guetta, R._
    - Very clearly laid out RQ's and introduction. 
    - Discussion connects to current literature. 
* [The Effects of Voter Demographics on the 2016 Primary Elections](https://drive.google.com/file/d/1ua1xV5t3Y6BqChvpKaTGIQ1HKobzaZMq) _Jordan, A., Arriaza, L., Ejaz, N., Loeblich, A., Wain, C._ 
    - Watermarks on bottom corners make words difficult to read. 
    - Table under results not made in Excel. 
    - Not easy to follow direction of story 
* [Influence of drivers race on the outcome of a traffic stop](https://drive.google.com/file/d/14Hos0VCUMp8UemQkRXVsaM-tcG7juaPs) _Gomez, E._
* [Investigating the association between parental dynamics and adolescent deviant behavior](https://drive.google.com/file/d/1nfksc9ckdKXtkVnuwb8QP50bKBOMhWlc) _FLores, A., Turner S._
* [The relationship between one's self-image and feeling that they are liked by their peers](https://drive.google.com/file/d/1-QfkiWXl3R1uiPpYgYonnQiN7k4lJL0O) _Stainton, E., Simpson, B._
* [The relationship between sleep disturbance and mental health](https://drive.google.com/file/d/1I_zoEYcQzlnClbnaNNcbmhxVbhH0UJEh) _Myrick, S., Rizzo, S._
* [Crater Depth & Diameter and their Association with Hemisphere & Ejecta Type](https://drive.google.com/file/d/1ekNlBIMVjjCUMuNC1J6aJvCkC-7dOatC) _Huntington, C. and Mavis, E._
  - Clean borderless columns
  - Good modification of high density plots
* [Does tree type affect the type of caterpillars that are found in the presence of birds?](https://drive.google.com/file/d/1hSl0S7hw7MGvoVH95FuAzkX0w2zf4kVq) _Tucker, K., McKibben. C._



