---
title: "The Continuum"
layout: post
date: 2018-06-11 22:44
image: /assets/images/astro.png
headerImage: true
tag:
- gsoc-2018
- astronomy
- programming
star: true
category: blog
author: sushobhana
description: The first month.
---

In the last post, we discussed on how to integrate the CRTF file format in the
regions package. The parser that I implemented seems to work and catches most of
the syntax errors pretty well. The test cases that I have added seems to be
proof of it. It has been merged to the master trunk now.

Since the last blog post, I have done a couple of things.

Earlier there was no method to convert regions object to Shape object. The Shape
class was only used to deserialise io file format but not the other way around.
The writer for DS9 file format is being directly converted to string from
regions object for now.

But, it is important that we need to use the Shape layer while serialisation for
a couple of reasons. Most importantly, it helps to interchange file formats
seamlessly. How? You convert regions object to Shape object . There are methods
for Shape objects to convert from CRTF to DS9 format and vice-versa. Then there
are to_ds9 and to_crtf methods to convert them into respective strings. I
implemented methods such as to_shape_list that were not present before , and
refactored the ds9_objects_to_string methods without breaking things down. I
have proposed it in the following pull request which is under scrutiny now, but
I believe it’s going to be merged
soon.([https://github.com/astropy/regions/pull/179](https://github.com/astropy/regions/pull/179))Another
challenging part was to convert meta data in one file format to another file
format. To solve this, I created RegionMeta and RegionVisual subclasses from
Python dict, which checks the validation of the keys.It contains methods which
returns io format compatible meta dictionaries which eases the serialization
process.

Meanwhile, I had my first video chat with my mentors Adam and Miguel. Apart from
a few technical glitches initially and me being little nervous and blabbering
throughout, it turned out pretty well , all thanks to my cool mentors. The
thirty to forty minutes conversation has setup our course for the next two
phases of coding period.

The first one was to create a test suite for CRTF , making sure that everything
works as expected. It is big of a deal, because we have very limited samples of
the region files and we need ample of them to test them regressively . Until we
collect them , we decided to test some part by converting DS9 files to CRTF and
then checking them.

Now, comes handling of the third dimensions (spectral) of the regions. This was
a very broad and challenging question because there are no specific standard for
handling them , and implementing them without any motivation is certainly a not
wise way. So, we decided to interface the regions with spectral-cube. In this
way, regions object object can be used to mask data cube , and we will have
another real application of regions package. Now, to extract a subcube from a
ds9 region, we use pyregions to parse it. Our motive is to replace it wih the
regions package . Also, we would want to use CRTF regions and use the spectral
parameters to extract a spectral slab . In this way, we can come up with ways to
handle the spectral parameters in regions as suitable.

We also discussed to completely replace photutils aperture machinery with
regions shapes.But, our first priority is to integrate spectral-cubes.

My summer vacations have started , and I am back home. So, I have decided to
escalate things up . To setup milestones in the progress , I have decided to
come up with weekly blog posts and so that I become a little more motivated.
This week, I have decided to implement the writer of CRTF (now that I am clear
of it’s design) which will be a matter of day or two. Also, I will be tinkering
with the spectral-cubes so that I have a better understanding of its working
under the hood and come up with ways to integrate with the regions. It’s going
to be a very steep learning curve for sure , but that’s what challenges me and
makes this whole thing exciting and thrilling.

Time to convert some caffeine into code, see you next week!

Valar Morghulis!
