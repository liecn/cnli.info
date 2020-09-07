---
layout: post
title: What is Data Science?
image: /assets/img/blog/Data_Science_VD.jpg
description: >
  When I first became interested in Data Science, the first thing I did was try to
  understand exactly what it was.  Googling around, I found an article that included an interesting [Venn Diagram](http://drewconway.com/zia/2013/3/26/the-data-science-venn-diagram).
sitemap: false
---

This diagram does a pretty nice job is showing the constituent parts of "Data Science".
{:.lead}

<!--- Comments are Fun  ![image-title-here](/assets/img/blog/Data_Science_VD.png){:class="img-responsive"} --->

<!--- ![image-title-here](/assets/img/blog/Data_Science_VD.png){:height="700px" width="400px"} --->



The diagram shows that Data Science really needs a combination of three skill-sets: [Hacking Skills](#hacking-skills), [Math and Statistics Knowledge](#math-and-statistics-knowledge), and [Substantive Expertise](#substantive-expertise).
True Data Science would be where these three disciplines intersect:

<p align="center">
  <img alt="img-name" src="/assets/img/blog/Data_Science_VD2.jpg" width="410">
  <br>
    <em>Real Data Science</em>
</p>

<!---  ![image-title-here](/assets/img/blog/Data_Science_VD2.jpg){:width="410px"} --->

Drew Conway, Co-author of Machine Learning for Hackers [^1], makes special mention of what he calls
the [Danger Zone](#danger-zone), or where he classifies people who know "enough to be dangerous":

<p align="center">
  <img alt="img-name" src="/assets/img/blog/Data_Science_VD3.jpg" width="410">
  <br>
    <em>The "Danger Zone"</em>
</p>
 

- Table of Contents
{:toc .large-only}

## Hacking Skills

You could consider Hacking Skills to be a flavor of programming skills, but more specifically
the skills necessary to "ready" the data necessary for any data analysis project.
Sometimes this is referred to as [Data Wrangling](https://en.wikipedia.org/wiki/Data_wrangling), or Data Munging.
As a Data Analyst, you are going to spend a lot more time finding data and preparing data than you
might have originally thought (sometimes up to 80% of your time on a project will be spent
doing data clean-up and preparation).

These two terms (***Wrangling*** and ***Munging***) are worth further defining, because each is slightly
different.  Wrangling refers to what is necessary to identify, gather, clean, sort, and format data so
it is suitable to use in your analysis.  The meaning is in the sense of [wrangling cows](https://www.vocabulary.com/dictionary/wrangle).
Mungling is a bit more obscure.  The orginal meaning goes back to an old 60's acronym for "Mash Until No Good" (MUNG).
Data that has been though a lot of transformations, using different edits and formats, passed
from system to system, database to database, can become degraded or Mung'ed.  Maybe you could more correctly
call Data Mungling Data Un-Munging, since you are attempting to reverse the degradation so the data is more useful.

 
## Math and Statistics Knowledge

Enough knowledge of statistics is required so you can extract meaning from your data.
So you will need to know enough statistical and mathematical methods to gain 
insights, reveal patterns and predict outcomes. Academic types are usually very strong in this
area, but being an expert in statistics is not necessarily required.  But you will need to
know which techniques to apply, and most importantly will need a good understanding of the 
meaning of the statistical outcomes of each technique.   

 
## Substantive Expertise

Without subject matter expertise in the area in which you are doing Data Science, pretty
much all you will be able to do is to crunch the data you have gathered using some sort of
mathematical model, maybe making predictions or decisions based on your input data (sometimes 
called a "training set"). This could be described generally as machine learning, shown in the Venn
diagram as the intersection between Hacking and Statistics Knowledge.

But for Data Science to really be a Science, it needs to include more than just data and statistical technique.
Conway specifially defines Science as:

> Science is about discovery and building knowledge, which requires some motivating questions about the world and hypotheses that can be brought to data and tested with statistical methods.

To know what questions to ask, and to fully engage in a process of testing and validation, you will need
to know a lot about the subject area in which you are working.  Gaming Payments in different than
Viticulture (grape growing), is different than Pharmaceutical Distribution. 

Conway also show the intersection between statistical skills and substantive expertise as
"Traditional Research".  This might have been true at one time, but from what I can tell from
reading a bunch of real blog posts, academic Data Science practitioners seems to have some pretty
good Hacking Skills! 
   
 
## Danger Zone

This is the area Conway identifies as the most problematic.  It consists of people
who know the business (Substantive Expertise), who also skillful enough programmers to prepare
some data for analysis (Hacking Skills), but aren't sufficiently knowledgable about
Statistics and Math to really understand the output of tools they may be using.

I believe the reason this "zone" even exists is because there are tools that make it fairly
easy to digest and process raw data, and to produce some type of output which might look like
it means something.  Tools such as R language IDE's (e.g., RStudio) and Python IDE's (i.e., Rodeo or Spyder) make
it pretty easy to generate some output which could be easy to misinterpret unless the
mathematics and statisical theory behind the algorithms is understood.

Fortunately, the more you work with these tools and the more time is spent on understanding
the underlying mathematics, the less likely this problem is to occur.

[^1]: [Machine Learning for Hackers](https://www.oreilly.com/library/view/machine-learning-for/9781449330514/) by Drew Conway, John Myles White
