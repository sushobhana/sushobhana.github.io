---
title: "The first phase ends"
layout: post
date: 2018-06-26 22:44
image: /assets/images/astro.png
headerImage: true
tag:
- gsoc-2018
- astronomy
- programming
star: true
category: blog
author: sushobhana
description: Whole freaking month.
---
These last two weeks have been a roller coaster ride in terms of both of my
coding and personal experiences.

The first evaluations went well , and for the first time someone credited to my
bank account other than my father. These are the few moments in life where you
feel genuinely happy, no excitement, nothing, just a sense of accomplishment.

In terms of progress , I think I have also managed pretty well. The objective of
the first phase is completed now and successfully merged to the master trunk.

Last week, I managed to complete the writer for CRTF Format
[https://github.com/astropy/regions/pull/186](https://github.com/astropy/regions/pull/186).
The whole serialization/deserialization of CRTF files now uses the Shape layer
like DS9.There is nothing much to do here in this section apart from improving
the tests and docs.

Another thing I successfully completed is replacing pyregion with regions
package in Spectral-cubes for extraction of a subcube from a region. The
`regions.Region` object,now, helps to select in the spatial dimension of the
cube and also determines the slab range in the spectral dimension of the cube
through it’s `range `key in `meta `dict
.[https://github.com/radio-astro-tools/spectral-cube/pull/488](https://github.com/radio-astro-tools/spectral-cube/pull/488/files)
I spent some time getting acquainted with the architecture of the package
.Besides that, I also had a great time learning about FITs cubes, masking,
cropping that were important to re-factoring the `subcube_from_ds9region()
`method and implementing the additional parts.During this I also managed to find
and fix a lot bugs such as
[https://github.com/astropy/regions/pull/185](https://github.com/astropy/regions/pull/185)),
[https://github.com/astropy/regions/issues/184](https://github.com/astropy/regions/issues/184)
in the io part which was exhilarating.

I have also started improving the docs w.r.t the recent changes made in the code
and aim to extensively document things that I have already implemented which is
way harder than it seems
[(https://github.com/astropy/regions/pull/188](https://github.com/astropy/regions/pull/188)).
Also, since the last few days I am trying to get my hands around the photutils
package .Since our next aim is to replace the photutils aperture with regions.
Although some part of them are similar to each other, there are subtle
differences which makes it difficult to trade off designs.This may take little
more time to come up with a specific approach.

Thus, next week , I aim to continue improving the docs and find ways to remove
the photutils apertures with regions. The plotting method of the apertures seems
to be more matured . I think it would not be bad to tinker with the plotting
methods and make them similar to that of aperture, and also make use of the
visual attribute of the regions class . I have already started learning more
about the matplotlib library. These days I am getting to learn so many new
things which manages to keep my adrenaline rush!

Now, that Git and github has been a part of my development workflow, I was
wondering how little did I know of how git actually works internally. Rebase,
reset and merge seems all magical to me now. I work with a lot of branches
simultaneously now. Though I am pretty much clear of the basics and use the
internet (Oh! I meant stackoverflow) in case of any issue, I am unaware of the
advanced features/techniques of using git. I feel it would be useful to devote
some of my time reading a book on it. I have read the first three chapters of
this awesome book
[https://git-scm.com/book/en/v2](https://git-scm.com/book/en/v2) which is
officially recommended and also free. Also, I found this blog post,
[http://tom.preston-werner.com/2009/05/19/the-git-parable.html](http://tom.preston-werner.com/2009/05/19/the-git-parable.html)
very interesting. Do give it a read.

Looking forward to this week!
