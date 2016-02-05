---
layout: post
title: "DIY: Kettle Etching"
category: homebrew
tags: [homebrew, beer, diy]
---

I just picked up a new brew kettle from the amazing [Everwood Ave Brew Shop](www.everwoodavebrewshop.com).
It's a pretty basic pot, with just a thermometer and ball valve ... a perfect staging point for some
fun upgrades and renovations!

The Problem
-----------

Since I'm doing mainly extract beers at the moment, I'm often filling the pot with 23L (6 gallons) of
water or more! Ends up being a real nightmare for me, because I only have a 500ml (1 pint) measuring
cup.

Turning the kettle itself into a measuring cup is just the thing I need to solve this painful
filling experience.

The Solution
------------

Inspired by this [cool article](https://byo.com/stories/issue/item/3113-etch-your-kettle-projects)
I decided to give it a go.

The details are listed in the link, so I won't go over it in too much detail -- but one thing that
bugged me was the method of just filling up the pot to mark measurements. Why are people always so
afraid of math!

It should be noted that where the bottom and wall of your pot meet might not be a 90 degree angle,
so the water method is the best way to get your baseline marking.

The Implementation
------------------

First things first, get some measurements of the pot!

My pot has a 35cm diameter (17.5cm radius).

To know the height we have to put each marking, just solve for a volume of a cylinder... for example,
with 1 litre markings (1 litre is 1000cm^3):

```
V = Height * π * r^2
1000cm^3 = Height * π * (17.5cm * 17.5cm)
1000cm^3 = Height * π * 306.25cm^2
1000cm^3 = Height * 962.112750162cm^2
Height = 1000cm^3 / 962.112750162cm^2
Height = 1.03937922019 // cm per litre
```

Always remember to track your units of measurement.

WIP BELOW THIS POINT
====================

I created this little [template generation](/etcher.html) tool... 
