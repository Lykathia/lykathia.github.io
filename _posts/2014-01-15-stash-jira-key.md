---
layout: post
title: "Quick Tip: Stash/JIRA Integration Key"
categories: software
tags: [atlassian, stash]
---

Stash comes with case insenitivity on jira matching. Very annoying if you're 
lazy ;). Luckily there is a way to change this... however there was an 
undocumented change in Stash 2.8 that caused things to stop working.

Previously if you had wanted case insensativity:

    JVM_SUPPORT_RECOMMENDED_ARGS="-Dstash.jira.key.pattern=\"((?<!([A-Za-z]{1,10})-?)[A-Za-z]+-\d+)\""

Stash 2.8+

    JVM_SUPPORT_RECOMMENDED_ARGS="-Dintegration.jira.key.pattern=\"((?<!([A-Za-z]{1,10})-?)[A-Za-z]+-\d+)\""

Seems like Atlassian updated their [documentation](https://confluence.atlassian.com/display/STASHKB/Integrating+with+custom+JIRA+issue+key)
after we contacted them. Cheers guys!
