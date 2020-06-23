---
title: Getting Started with R and R Studio
author: ''
date: '2017-08-06'
slug: software-overview
categories:
  - programming
tags:
  - Rstudio
  - Rmarkdown
  - LaTeX
---

# Overview
Instructions and links for downloading and installing the R Studio suite of awesomeness. Includes a brief walkthrough of R Studio

1. **R**  -- The programming language.
2. **R Studio** -- A fantastic interface for coding in R.
3. **LaTeX** -- Required to create PDF reports. 
4. **R Commander** -- A true to form GUI (point and click) for using R. (Optional)

# Program Installation

## Windows

* Download R from https://cran.r-project.org/bin/windows/base/ 
* Download **R Studio Desktop (Free License)** from http://www.rstudio.com/products/rstudio/download2/

Double clicking on these will start the standard installation process.

[Video walkthrough](http://www.youtube.com/watch?v=Ohnk9hcxf9M)

## Macintosh 

* Download R from https://cran.r-project.org/bin/macosx/
* Download **R Studio Desktop (Free License)** from http://www.rstudio.com/products/rstudio/download2/

[Video walkthrough](http://www.youtube.com/watch?v=uxuuWXU-7UQ)

Optional: Install via [Homebrew](http://datascience.csuchico.edu/materials/install_r_with_homebrew.md). Guide courtesy of Justin Bankes (2017).


# R Studio - A tour

###  Initial Start

When you first (like very first time) open R studio you will see three panels.
![](/img/rstudio/rstudio-start.png)

###  Console

The *console* is the full panel on the left
![](/img/rstudio/rstudio-console.png)

- Everytime you launch RStudio, it will have the same text at the top of the 
console telling you the version of R that you're running.  
- Below that information is the *prompt*, `>` . As its name suggests, this prompt is really a request, a request for a command. 
- Initially, interacting with R is all about typing commands and interpreting the output. 
- These commands and their syntax have evolved over decades (literally) and now provide what many users feel is a fairly natural way to access data and organize, describe, and invoke statistical computations.


The console is where you type commands and have them immediately performed. 

![](/img/rstudio/rstudio-console-add.png)

###  Environment
The panel in the upper right contains your *workspace* (aka Environment)

![](/img/rstudio/rstudio-env.png)


- This shows you a list of objects/variables that R has saved. 
- For example here a value of 3 has been _assigned_ to the object `a`.

![](/img/rstudio/rstudio-env-items.png)

###  History

Up here there is an additional tab to see the *history* of the commands that you've previously entered.  

![](/img/rstudio/rstudio-history.png)

###  Files
The files tab allows you to open code/script files within R studio.

![](/img/rstudio/rstudio-files.png)

###  Plots
Any plots that you generate will show up in the panel in the lower right corner.

![](/img/rstudio/rstudio-plot.png)


### Getting Help
To check the syntax of any function in `R`, type `?` in front of the function name to pull up the help file. 

![](/img/rstudio/rstudio-help.png)

For example here I typed `?mean` to get the help file for the `mean` function. Admittedly these aren't the most helpful of files at times. This is where Google / stack overflow / R help list serves and [R user groups](https://groups.google.com/forum/#!forum/chico-rug) can be your friend. 


### Script file (a.k.a code file)
* Most often your R studio window will have 4 panels. 
* The top left is your editor window, where you write code or script, the console is now at the bottom. Sometimes it's minimized, you can use the boxes in the top right corner of the console window to bring up the console. 

![](/img/rstudio/rstudio-working.png)

When we type R code in a specific way up here, the results show up both 
right below the code you just typed, and in the console itself. 
```r
2+2
```

![](/img/rstudio/rstudio-working-command.png)

## Setting Preferences to retain sanity

### R Studio Preferences

To avoid some of the most common errors when learning R let's set some preferences in RStudio. 

1. On your computer, create a folder for your specific course in an easy to locate place. 
    - Recommended paths are short, such as `C:/School/R` or `~/rdonatello/School/MATH315`
    - You will store all files associated with this class here.
    - Do not use any spaces in the folder name, and keep it simple.

### Finding your path on a Mac

1. Select the file or folder in the OS X Finder, then hit Command+i to summon Get Info
2. Get Info can also be accessed by the control-click and right-click menus.
3. Click and drag alongside "Where" to select the path, then hit Command+C to copy the full path to the clipboard 
4. Paste this into `R` for your path. 
5. Make sure all slashes are forward slashes `/`.

Mac Reference link: <http://bit.ly/1NxF9eu>


### Finding your path on Windows
1. Open Windows Explorer and browse to the folder or file of your choice.
2. The path to the folder/file will be indicated in the Address bar of Windows Explorer.
3. To copy it, simply right-click on the Address bar and select _Copy address as text_.
4. Paste this into `R` for your path. 
5. Make sure all slashes are forward slashes `/`.


Windows Reference link: <http://bit.ly/1NxFeir>


### R Studio Preferences

Continuing with the R Studio preferences, 

2. In RStudio the file menu go to _Tools_ then _Global Options_. 
3. Uncheck "Restore .RData into workspace at startup" and "Always save history"
4. Where it says 'Save workspace to .RData on exit:" Select 'Never'
5. Click _apply_ then _ok_. 


## R packages: How things get done.

#### Installing R Packages 

Packages are sets of predefined code, functions and data sets. They provide additional functionality and goodies beyond what is included when you download Base R. 

* Packages are only installed once per computer (until you update R).

* To install the `knitr` package type the following command at the prompt `>` and hit enter to submit the command.
```r
install.packages("knitr")
```

* Repeat the above to install the following packages, remembering `R` is case sensitive: `rmarkdown`, `kableExtra`, `gridExtra`, `tidyverse`, `knitr`, `nycflights13` and `hflights`. 

#### Installing R Packages - Shortcut
You can install multiple packages at once by combining the list of package
names using the collection operator `c()`.

```r
install.packages(c("rmarkdown", "tidyverse", "gridExtra", "kableExtra",
      "knitr", "nycflights13","hflights"))
```

# LaTeX - professional reporting

### Make nice PDF reports and presentations.
LaTeX allows you to turn your reports into a nicely formatted PDF document. 

* Install once and forget about it. 

Download from: https://www.latex-project.org/get/

* Windows: I have had best luck with proTeXt
* Suck it up and get the 2G download for less headache later. (Don't do this on the campus wifi during class time.)

You can edit *tex files directly in R Studio, a separate tex editor is not necessary. 


# R Commander: Pointing and clicking your way along
#### A Basic Statistics GUI for R
<center>
<img src="https://socserv.mcmaster.ca/jfox/Misc/Rcmdr/Rcmdr-screenshot.jpg" style="width: 500px;"/>
</center>

#### Additional setup for R Commander

* Install via the `Rcmdr` package. 
* Website: http://socserv.mcmaster.ca/jfox/Misc/Rcmdr/
* You will need to install Pandoc converter engine if you want to create PDF
  output as Rcmdr uses the old markdown package which only can create HTML output.


# More help
For more help and/or places to start learning, I would recommend starting with the resources R Studio already has curated for you. 
https://www.rstudio.com/online-learning/

