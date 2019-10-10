---
title: The Conditional Missingness of Missing Values in R
author: Brett J. Gall
date: '2019-07-11'
slug: missing-values-in-r
categories:
  - Programming
tags:
  - R
  - NA
  - Missing Values
  - Programming
subtitle: ''
summary: ''
authors: []
lastmod: '2019-07-11T17:59:44-04:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

Many data analysts often wish to examine subsets of data or otherwise manipulate data using indicators of data missingness. Luckily, R features a number of different ways of designating a value as missing. Unluckily, some of the interactions with popular functions are not always intuitive and this can produce unintended results.

I wrote a demonstration of this awhile back. The below showcases behaviors of missing values many R programmers likely expect and also some surprising results. One way to potentially avoid disastrous consequences - as a consequence of these behaviors or other causes - is to establish tests to make sure your code does what you want it to do.

<script src="https://gist.github.com/bgall/1de4e8e741491ed478554b3c5259f8d7.js"></script>
