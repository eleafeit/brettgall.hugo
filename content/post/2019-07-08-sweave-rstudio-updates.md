---
title: (S)weaving in RStudio when you've updated TeX
author: Brett J. Gall
date: '2019-07-11'
slug: sweave-rstudio-update
categories:
  - Programming
tags:
  - RStudio
  - Reproducibility
  - TeX
  - Dynamic Documents
  - Programming
  - R
  - MikTex
  - IDE
  - Sweave
---

RStudio is a popular, well-supported IDE for R programmers. While a number of text editors with steep learning curves and direct interaction with command line may offer more power and flexibility, RStudio facilitates completion of common tasks with minimal investment.

One reason to use RStudio is the ease with which researchers can embrace literate programming to create dynamic documents. Dynamic documents are attractive because they promise reductions in human error and time costs for researchers. Ever wonder how you calculated a number or produced a figure in one of your own papers, months or years after you first wrote the paper? Dynamic documents shows you the exact code: rather than manually copy and paste text, code, and the outputs of code across multiple documents, well-designed dynamic documents automatically update reported results, references, and other quantities of interest because they directly tie the natural language of your documents to the code generating the language and code. Even Stata is [now on](https://www.stata.com/features/overview/markdown/) the bandwagon of dynamic documents.

RStudio is well-suited for producing dynamic documents with R code from two types of file extensions: .rnw and .rmd. The .rnw files - known as Sweave files - effectively let you write a file using the [TeX](https://www.tug.org/begin.html) typesetting system while directly incorporating the results of your R code into your TeX file. The .rmd files - known as [RMarkdown](https://rmarkdown.rstudio.com/) files - let you write Markdown files similarly incorporating your R code into the file. Your need for control over typesetting or journal requirements will typicically determine which you want to use.

## Getting it to work

The instructions for installation are pretty straightforward and found via the linked sites. However, one of the bigger issues with compiling .rnw or .rmd files in RStudio is that errors often arise when you update something. You might update your distribution of R, RStudio, TeX, etc. and suddenly you face a number of errors that lead to your documents not compiling into pretty PDF, HTML, or Word files. I have found myself Googling solutions to various errors any time I update my MikTeX-based TeX distribution. 

A few quick tips and links to resources in case you suddenly find anything broken. These are as much for my own future reference as they are resources for others:

- Download a .tex editor (e.g. [TexStudio](https://www.texstudio.org/)) and try to build a simple file in the editor. If it compiles, that means it's an issue with RStudio and not your TeX distribution. You can also check this from the [command line](https://tex.stackexchange.com/questions/132704/how-to-build-knitr-document-from-the-command-line). If you fail to build, make sure you not only have a distribution installed, but that you also have the packages you need installed or have enabled on-the-fly installation of packages. Some TeX distributions have accompanying graphical interfaces for package management while others may be most conveniently used via R or the command line.
- If you have no issues compiling outside of RStudio, check you have the correct working directory. Maybe you can't build because you are in the incorrect directory.
- The most common issue following updates is that RStudio fails to detect the updated TeX installation or is directed at an old installation path. Old installs - even uninstalled - can linger around for various reasons and you may also experience problems if you have multiple TeX distributions (e.g. different versions). This typically leads to RStudio failing to find the programs/packages it needs. If this happens (often you'll see "exit code 1" in the error message), follow [these steps](https://tex.stackexchange.com/questions/429706/rstudio-not-detecting-miktex). 
