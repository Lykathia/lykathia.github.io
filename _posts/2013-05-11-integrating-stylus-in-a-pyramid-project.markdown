---
layout: post
title: "Integrating Stylus in a Pyramid Project"
category: coding
tags: [python, css]
---

wip ... uploaded half done to be able to keep working on other aspects of site and jazz

### why stylus

### Installing Stylus
#### Getting Started
Some basics... you'll need:

+ [node js](http://nodejs.org/)
+ [pyramid_assetcompiler](http://pyramid-assetcompiler.readthedocs.org/en/latest/)

Best bet here is going to be to install Stylus globally with npm. If you're on shared hosting and this isn't an option for you, just pick a place in your project to install stylus.

`npm install stylus -g`

#### Converting previous CSS to STYL

Some stuff ...
`find -name "*.css" -exec stylus -C {} \;`

You could throw a delete in the above to remove the css files as well while you're at it, but I'm leaving that out incase someone reading this isn't using version control (stop reading this, go setup version control on your project).

Of course now that we're new age hipsters, we'll want to add *.css to our gitignore for cleanliness.

#### Adding Stylus to Pyramid

`stylus -c /path/to/css/`
