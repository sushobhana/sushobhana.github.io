---
title: "The First Two Weeks Of GSoC"
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

![](https://cdn-images-1.medium.com/max/1300/1*ilEYYOomG-6Xmj4SoZ2S2g.png)

Hey, it’s Sushobhana. Sushobhana Patra. That’s right. Don’t adjust your…whatever
device you’re reading this on. It’s me, live and on medium. No return
engagements, no encore, and this time, absolutely no requests. Get a snack.
Settle in. Because I’m about to tell you the story of my summer. More
specifically, what code did I develop this week under GSoC.

The coding period with astropy’s regions has started since the last two weeks.
It’s has been amazing since then.

What is Astropy? It is a community effort to provide core packages for astronomy
using python. The core package contains tons of various classes, utilities, and
a packaging framework intended to provide commonly-used astronomy tools. Just a
random fact, there are currently 10,000 active github original repositories
using Astropy out of which more than 1000 are on PyPI. Isn’t it amazing?

Regions is an *astropy affliated package* which deals with handling
regions(off-course!). Now, what are regions ? It is any considerable and
connected part of a space or surface studied in astronomy. It is basically used
to define an part of an image while analyzing and processing them.So, it
provides classes to handle regions with fixed shapes either using pixel or
celestial coordinates. There are several standard formats to express regions and
our package should be able to read as well as interpret those so that it gives a
common interface to many users.

CASA , the *Common Astronomy Software Applications* package, is a software which
focuses on various kinds of data processing from various radioastronomical
telescopes. It has several image processing tools and has CRTF format, CASA
Regions Text Format which provides flexible region definitions syntax for their
internal use. Now, being able to read this file format in the regions package
will gradually encourage/help the CASA users to experience similar tools that
Astropy provides.

My Project’s Title , “CASA CRTF REGION FILE HANDLING” pretty much sums off the
overall objective. Not only I have to implement an efficient Parser for reading
that file format, but also to implement the CRTF regions which are not presently
available in regions package. The CASA’s regions apart from describing the
euclidean geometry, also has spectral dimensions (the third dimension) which
needs to be implemented. The regions package aims to support various file
format(DS9 is already available) . Most of the parts are incontrovertible with
one another and it aims to provide interfaces and methods to do so.

For the first two weeks , I was focused to write a parser to convert CRTF region
strings to `Shape` objects. `Shape` is an intermediate class which holds
sufficient information about the region from the deserialization of specific
file format. It contains method to convert them to `region` objects. I have
mostly used python’s regular expressions . There are few reason why I chose so.
First, It is an awesome, tiny, highly specialized language which is very
powerful. It lets you do all type of godly things with strings such as helps us
to match certain part of any crazy strings(people even parse html and xml codes
with this) and also extract particular parts of it. So, it does lexical analysis
very well. Since CRTF has a very simple one line syntax, the syntactical
analysis isn’t that big a deal. And the regex engine of python is completely
written in C which makes it super efficient. `re` module seemed to be a perfect
match for this job. Oh!.. I forgot another reason, regex expressions are
difficult to understand to anyone who hasn’t seen this before, this makes me
look like a super coder!

![](https://cdn-images-1.medium.com/max/1040/1*1wpnzKE3PuhrQMzZrQXufw.jpeg)

Actually, it contains a lot of meta-characters which have special meaning to
it.There are ways to dissect the strings by dividing the RE into groups. There
are many cool features such as look-ahead asssertions , greedy vs non-greedy
search, splitting , replacing to name a few. If you are in any way interested in
learning them, there is an official python HOWTO (
[https://docs.python.org/3/howto/regex.html](https://docs.python.org/3/howto/regex.html)).It
is crisp, clear ,explains most of the features of `re` module and a perfect
tutorial for beginners.

Now, the two weeks have been pretty rough,with the end-semester exams and all,
still, I have not let myself hamper the development pace.I implemented the whole
CRTF parser. Apart from a few issues such as mapping of CASA’s coordinate
systems to that of Astropy’s that needs to be addressed , it is almost
complete.I have also added documentations and tests to it. Here is the link to
the pull request:
[https://github.com/astropy/regions/pull/173](https://github.com/astropy/regions/pull/173).

This week I am focusing on to handle meta attributes of the regions. There are
currently no documentations present so as to what kind of keys it allows and
also their domains. So, we have decided to work on creating a `dict` subclass so
that validity of the keys and values can be checked. We also have to make sure
that it is compatible with all the file formats that are present.Second thing
would be to work on serialization of DS9 region. Currently, it doesn’t use the
`shape` layer which is kind of important if we want to convert from one file
format to another, such as CRTF to DS9 or vice-versa. Next thing would be to
implement regions that are currently not available such as symbol, text, vector,
box.

Thats all for now, I just hope that I don’t get baked up in this 43 degree
Celsius hot and dry summer.
