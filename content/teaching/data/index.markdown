---
title: Data
author: Robin Donatello
date: '2020-07-08'
slug: data
categories: []
tags: []
linktitle: Data
summary: Wherever possible I try to use real world, non pre-processed data in the classroom. The [Data](data/) page provides links to download data, codebooks where available, and code to import these data sets into R. 
lastmod: '2020-07-08T13:48:47-07:00'
toc: yes
type: docs
menu:
  example:
    name: How to use this sidebar
    weight: 1
---


This page contains links to data sets I commonly use across classes. Most data sets are real world data, and are as such not fully prepared for analysis. Data preparation tasks such as creating new variables, refactoring categorical variable and dealing with missing values may be necessary. 

Each entry contains the following pieces. 

1. Information about the data set and where it comes from. Citation/credits where possible. 
2. The link to the **data** set. ❌ Right click to save this file to your class folder. Do not left click to open. 
    a. [optional] A link to the **raw data** file. There may be times when the raw, or unprocessed, data is needed. 
3. A **codebook** where available. Also called a **data dictionary** this document tells you what data  This will most often be the codebook for the raw data (will not include variables created by me in the data management script).
4. A **data management script** where available. Presented as a RMarkdown script, this will show you exactly what data processing steps have been taken already. 
5. The code to read the data into R and any notes that may go along with it. ⚠️ You will always have to change this path to your specific data location. 
6. The dimensions (number of rows and columns) of the data set. You should use this information to confirm that the data set you download and import into R matches this information. 

---

## AddHealth

The National Longitudinal Study of Adolescent to Adult Health (Add Health) is a longitudinal study of a nationally representative sample of adolescents in grades 7-12 in the United States during the 1994-95 school year. The Add Health cohort has been followed into young adulthood with four in-home interviews, the most recent in 2008, when the sample was aged 24-32. Add Health is re-interviewing cohort members in a Wave V follow-up from 2016-2018 to collect social, environmental, behavioral, and biological data with which to track the emergence of chronic disease as the cohort moves through their fourth decade of life. More info at: http://www.cpc.unc.edu/projects/addhealth 

* [Clean Data](../../../data/addhealth_clean.Rdata), [Raw data](../../../data/AddHealth_Wave_IV.csv)
* [Codebook](../../../data/AddHealth_Wave_IV.pdf)
* [Data Management script](../../../data/dm_AddHlth.html)
* The cleaned AddHealth data set is provided as an R data file, not single external data set. The code below uses the `load()` function to load the data directly into your environment. ⚠️ Note the absence of the assignment arrow `<-`. This is intentional and your data will not load correctly if you try to use the arrow. 


```r
load("../../../static/data/addhealth_clean.Rdata")
dim(addhealth)
```

```
## [1] 6504  992
```

----

## Ames

* [Ames](../../../dat/ames.csv): All residential home sales in Ames, Iowa between 2006 and 2010. The data set contains many explanatory variables on the quality and quantity of physical attributes of residential homes in Iowa sold between 2006 and 2010. Most of the variables describe information a typical home buyer would like to know about a property (square footage, number of bedrooms and bathrooms, size of lot, etc.). A detailed discussion of variables can be found in the original paper: _De Cock D. 2011. Ames, Iowa: Alternative to the Boston Housing Data as an End of Semester Regression Project. Journal of Statistics Education; 19(3)_.

```r
ames <- read.csv("../../../static/data/ames.csv", header=TRUE)
dim(ames)
```

```
## [1] 2930   82
```


## countyComplete

* [countyComplete](../../../data/countyComplete.csv): Characteristics of different counties in the United States. Information on this data set can be found in the full [Open Intro Data Codebook](../Open Intro Data Codebook.pdf). Just search for the data set name. 

```r
county <- read.csv("../../../static/data/countyComplete.csv", header=TRUE, stringsAsFactors = FALSE)
dim(county)
```

```
## [1] 3116   56
```

## Crime Data

* [Crime_Data](../../../data/Crime_Data): State and regional level information on crime and murder rates. 

```r
crime <- readxl::read_excel("../../../static/data/Crime_Data.xlsx")
dim(crime)
```

```
## [1] 51 11
```

## Depression
* [Depress](../../../data/depress_081217.txt) Tab delimited text file. The depression data set is from the first set of interviews of a prospective study of depression in the adult residents of Los Angeles County and includes 294 observations. More details on the origin and study design can be found in Practical Multivariate Analysis, 5th edition by Afifi, May and Clark. The [codebook](../DepressCodebook.txt) can be downloaded as a text file. 

```r
depress <- read.delim("../../../static/data/depress_081217.txt", header=TRUE,sep="\t")
dim(depress)
```

```
## [1] 294  37
```

## Download Times

* [Download Times](../../../data/DownloadTimes.txt) An experiment run by a student to detect if his internet speed varied across different times of the day. This tab-delimited data set contains two variables: `time` as a categorical time of day (Early, Evening, Late), and the time (in `sec`) it took to download a particular file. The file downloaded was the same each time to the same computer. 

```r
dt <- read.delim("../../../static/data/DownloadTimes.txt", header=TRUE, sep="\t")
dim(dt)
```

```
## [1] 48  2
```

## Diamonds (small)

* [dsmall](../../../data/dsmall.txt) This is a randomly drawn sample from the `diamonds` data set found in the `ggplot2` package. For those not using `R` I have provided a tab delimited text file for download. For those using R, use the code below to create the `dsmall` data set. The [codebook](http://ggplot2.tidyverse.org/reference/diamonds.html) can be found on the ggplot2 documentation site. 


```r
set.seed(1410) # Make the sample reproducible
diamonds <- ggplot2::diamonds # load the data without loading the ggplot2 package
dsmall <- diamonds[sample(nrow(diamonds), 1000), ] # create the subset
dim(dsmall)
```

```
## [1] 1000   10
```



<!---
* [Northridge Earthquake](../Earthq.txt) **Right Click and select `save link as` to save this file to your class folder.** The Northridge earthquake data set comes from a set of telephone surveys on the experiences of Los Angeles, CA county residents following the 1994 Northridge earthquake. Subjects were asked for their demographic information and about damage to their home, sustaining injury, and psychological responses to the earthquake. The data used here include 506 randomly selected subjects with relevant variables for the problems. The data is owned by Professor Linda Borque of the UCLA School of Public Health, Department of Community Health Sciences and used with permission in conjunction with the textbook Practical Multivariate Analysis by Afifi et.al. The [codebook](../EarthqCodebook.txt) can be downloaded as a text file. 


```r
quake <- read.table("C:/GitHub/website/../static/data/Earthq.txt", header=TRUE, na.strings=".")
dim(quake)
```
--->

## Email

* [email](../../../data/email.txt): **Right Click and select `save link as` to save this file to your class folder.** These data represent incoming emails for the first three months of 2012 for David Diez's (_An Open Intro Statistics Textbook author_) Gmail Account, early months of 2012. All personally identifiable information has been removed. [Email Codebook](../EmailCodebook.html)

```r
email <- read.delim("../../../static/data/email.txt", header=TRUE, stringsAsFactors = FALSE, sep="\t")
dim(email)
```

```
## [1] 3921   21
```

## Dementia

* [Full moon on Dementia](../../../data/dementia_moon.txt) A study observed 15 nursing home patients with dementia and recorded the number of aggressive incidents each day for 12 weeks. Then they totaled the counts of aggressive incidents per patient on "moon" days (full moon +/-1 day) and "other" days. 

```r
moon <- read.delim("../../../static/data/dementia_moon.txt", sep="\t", header=TRUE)
dim(moon)
```

```
## [1] 15  3
```

## HS and Beyond

* [High School and Beyond](../../../data/hsb2.txt). The High School and Beyond (HS&B) Longitudinal Study was the second study conducted as part of NCES' National Longitudinal Studies Program. This program was established to study the educational, vocational, and personal development of young people, beginning with their elementary or high school years and following them over time as they take on adult roles and responsibilities. http://nces.ed.gov/statprog/handbook/pdf/hsb.pdf 
  

```r
hsb2 <- read.delim("../../../static/data/hsb2.txt", sep="\t")
dim(hsb2)
```

```
## [1] 200  11
```

## Lung Function

* [Lung](../../../data/Lung_081217.txt) Tab-delimited text file. This data come from a study on chronic respiratory disease and the effects of various types of smog on lung function of children and adults in the Los Angeles area. More details on the origin and study design can be found in Practical Multivariate Analysis, 5th edition by Afifi, May and Clark. The [codebook](../LungCodebook.txt) can be downloaded as a text file. 

```r
fev <- read.delim("../../../static/data/Lung_081217.txt", header=TRUE,sep="\t")
dim(fev)
```

```
## [1] 150  32
```

## NC Births

* [NCbirths](../../../data/NCbirths.csv): Publicly released data on a random sample of births recorded in North Carolina in 2004.[Codebook](../NCBirthsCodebook.html)

```r
ncbirths <- read.csv("../../../static/data/NCbirths.csv", header=TRUE, stringsAsFactors = FALSE)
dim(ncbirths)
```

```
## [1] 1000   13
```

## Parental HIV

* [ParentalHIV](../../../data/PARHIV_081217.txt): Data collected as part of a clinical trial to evaluate behavioral interventions for families with a parent with HIV. The data include information on a subset of 252 adolescent children of parents with HIV. The [Codebook](../ParhivCodebook.txt) describes the variables and gives a brief description of their meaning. The data is owned by by Dr. Mary Jane Rotheram-Borus, Professor of Psychology and Behavioral Sciences, Director of the Center for Community Health, Neuropsychiatric Institute, UCLA and used with permission in conjunction with the textbook Practical Multivariate Analysis by Afifi et.al. 


```r
parHIV <- read.delim("../../../static/data/PARHIV_081217.txt", header=TRUE, stringsAsFactors = FALSE, sep="\t")
dim(parHIV)
```

```
## [1] 252 123
```

## Physical Activity & BMI

* [Physical Activity and BMI](../../../data/PABMI.txt) Physical activity measured as the number of steps in thousands. 

```r
pabmi <- read.delim("../../../static/data/PABMI.txt", header=TRUE,sep="\t")
dim(pabmi)
```

```
## [1] 100   3
```

## Police Shootings

* [Police Shootings](../../../data/fatal-police-shootings-data.xlsx): Excel file on police shootings in 2015 as compiled by the Washington Post. Data downloaded from https://github.com/washingtonpost/data-police-shootings on 9/11/16. 

```r
washpost <- read_excel("../../../static/data/fatal-police-shootings-data.xlsx")
dim(washpost)
```

---

_This page last updated on2020-08-14 16:13:23_

