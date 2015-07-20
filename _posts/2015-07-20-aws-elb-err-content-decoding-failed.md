---
layout: post
title: "Gotcha: AWS ELB ERR_CONTENT_DECODING_FAILED"
comments: true
categories: programming
tags: [aws]
---

NEVER DO DEPLOYMENTS BEFORE YOU WANT TO SLEEP
=============================================

A simple statement that everyone understands. Nods. Agrees. Then ignores.


AWS ELB ERR_CONTENT_DECODING_FAILED
-----------------------------------

This was a real tricky one, and it took almost an hour of being in chat
with AWS tech support to figure it out. The AWS ELB is extremely sensitive
to malformed headers, so while chromium/firefox and others may willingly
accept some malformation (such as multi-line headers), Amazon's ELB most
certainly will not.

Hope this helps someone, sometime.
