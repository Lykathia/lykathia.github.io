---
layout: post
title: "Window Managers: An update [first impressions]"
comments: true
categories: software
tags: [xmonad, dotfiles, bspwm]
---

My [dotfiles](https://github.com/Lykathia/.dotfiles) aren't anything
too special. I've had a few [Haskell](http://www.haskell.org/haskellwiki/Haskell)
enthusiasts come by and clone / checkout my [xmonad](http://xmonad.org/)
configurations, which has been kind of cool -- and also [kind of
awkward](https://twitter.com/Lykathia/status/492275684476084224).

XMonad has been serving me extremely well as a window manager, and my
productivity in coding has never been higher since switching to a tiling
window manager. However, I sadly do not get to do much Haskell in my spare
time -- with [Scala](http://www.scala-lang.org/) becoming the functional
language of choice for me (mostly due to it being a viable alternative
to Java, which I've been trying to get pushed in at work for a while now.)
As such, my Haskell'ing skills never really got to grow, on top of  a lot 
of the xmonad configuration stuff really being it's own special API in some
ways (which is fine, just need the time to learn it).

So some astute amongst you will have noticed this post tagged with bspwm. So, yes,
I am making the transition over to [bspwm](https://github.com/baskerville/bspwm).

### Why

While xmonad has been amazing for coding productivity, getting it to play nicely
with video games has always been something of a nightmare. I'm going to place
the blame for this squarely on my own configuration, but I could not figure out how
to solve the following: when having a full screen video game open, and switching desktops,
the game window expanded in size, no longer fitting the native resolution.

Weird, eh?

There had been a lot of talk over on [/r/unixporn](http://www.reddit.com/r/unixporn)
about bspwm, so with some frustration over not really being able to play DoTA2 for the last
~year+ (I no longer own any windows machines, or duel boot), I decided to give
bspwm a go, and see if it fixed my fullscreen woes.

### The switch

I installed ```bspwm-git``` and ```sxhkd-git``` from the [AUR](https://aur.archlinux.org),
copied the example configuration provided in the bspwm repository, updated my xinitrc to 
comment out the xmonad launch and put in sxhkd and bspwm, and restarted X. (The hotkeys
for sxhkd I did modify / borrow from some other configs to make them more like the ones
I had been using in xmonad).

First impressions -- fucking awesome. Solved the window bleeding issue I was having with
xmonad as described above. Window splitting felt more natural then it did on xmonad, and
toggling fullscreen applications was also a lot cleaner looking.

Second impressions -- multi monitor support is not on par with xmonad. This is somwhat
annoying, and I'll follow up with some kind of fix to this once I figure it out.

### Conclusion

XMonad still feels more flexible and powerful to me. If I had more time to play
with the configuration, and was using Haskell on a more day-day operation, I
highly doubt I would be switching.

bswpm is fast, small, sleek and works very well out of the box. I look forward
to making it behave like xmonad does ;)
