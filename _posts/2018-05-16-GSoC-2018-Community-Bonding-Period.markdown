---
title: "GSoC-2018 - Community Bonding Period"
layout: post
date: 2018-05-16 22:44
image: /assets/images/markdown.jpg
headerImage: false
tag:
- gsoc-2018
- astronomy
- programming
star: true
category: blog
author: sushobhana
description: The beginning of my summer with OpenAstronomy.
---

Hi World,

I am a 19 year old undergrad student from India majoring in Computer Science. I
have been selected in **Google Summer Of Code** as a student developer this
summer under the umbrella organization Open Astronomy.I will be spending the
next three months improving and implementing new functionalities to the
**regions**, an **astropy** affiliated python package. I will be explaining all
about this and my project with complete details in my further posts. Here is a
link to a short summary :

[https://summerofcode.withgoogle.com/projects/#5210718853398528](https://summerofcode.withgoogle.com/projects/#5210718853398528)

If you want to dive deeper , here is the link to the project proposal :

*****

You must be thinking, why didn’t I just describe my project and dive into
technicalities?? Well, we have the whole summer to discuss that !

In this post, I just want to focus on the GSoC part and how much this program
means to me. For those of you don’t know about GSoC, it is an international
program sponsored by google where students are paid over to work on various open
source projects over their summer vacations.

You get to work on projects used by thousands of people, interacting closely
with the open source community and you are paid for this! I couldn’t think of a
better summer. If you are a university student who happens to love programming
and solving bugs you might consider applying for GSoC next year.

The journey so far in the astropy community has been splendid.I initially
started contributing a few PRs to the astropy core around december.The community
was very welcoming and patient enough to review my PR for several iterations.I
was completely new to git and github’s workflow and was working on a public code
base for the first time. I was simultaneously learning Python . And to add on
top of that I was completely new to the jargons used by the astronomers.It all
had a very steep learning curve , but it was worth it. I learnt a lot, starting
from documenting the code to writing test cases for it. I understood how to
write clean codes with better design and how much important it is to write
readable code. These things may seem trivial to many but avoiding premature
optimization is an art in itself!!

Jokes Apart, I am grateful to taldcroft and Simon for initially reviewing my PRs
without losing their temper!😀The initial kick-start was very important for me.

When I started looking for projects after the org announcements, the regions
project seemed very interesting to me and I started writing a proposal for it. I
would like to thank Adam Ginsburg(also my mentor), the project lead for regions
package who responded to each of my queries , helping me understand the scope of
the project. He was also kind enough to review my proposal for a couple of
times. I would also like to thank Miguel , my second mentor for reviewing the
proposal and providing me with valuable inputs.

I would also like to thank Brigitta and David , the org admins for making this
whole process easier.

*****

The results were announced on 23rd April,2018 .The community-bonding period
began and ended on 14th May. I was on cloud nine for a couple of days and it
took me around a week to actually sync that in. This was the time to learn more
about my community , setting developement installs , chalking out the objectives
and learning new things that I might need while coding away this summer. I
pretty much did everything in these three weeks. Also I have my end semester
exam starting this week , so I ensured I started out little early so that I
could be on schedule.

The first part of my project is to implement CRTF File reader(It is a region
file format having a specific syntax). This needed some regular expressions for
string matching. Regular expression is an awesome language for string matching
and is provided in Python through the re module. I spent some time understanding
this and started writing the skeleton of the parser.

The parser is close to complete now. There are a couple of issues that needs to
be addressed along with writing tests. I will be writing more about how I
approached to the design and my experience with regular expression, in the next
week along with my PR details.

So far it is all nice. The experience has been amazing . Looking forward to all
the challenges ahead!!!

Adieu!
