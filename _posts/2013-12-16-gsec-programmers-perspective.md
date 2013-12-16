---
layout: post
title: "GSEC: A Software Engineers Perspective"
category: security
tags: [giac, security]
---

After finishing up my GSEC Certification and the OnDemand SANS401 course, I 
figured it was worth a retrospect. The course and certification are aimed at
IT professionals, so taking the course as a software engineer means I'm not
quite the target market they're looking to capture.

### Course Focus
A quick glance at the [course ciriculum](http://www.sans.org/ondemand/course/security-essentials-bootcamp-style)
gives a pretty good overview at the overall direction of the course.

I found the focus of the course to be very catered to corporate IT -- being 
the target audience of this course and all, it should come as no surprise.
Many topics are given a 65/35 split between the technology and the corperate
politics one would expect to face when implementing it. This was actually 
kind of interesting coming at it from a programmers perspective, although
at times (especially in the risk assessment sections) it got a little 
overboard.

The GIAC exam was *very* windows heavy. Something to note for
anyone looking to take the exam.

##### Course Strengths
The entire first section is excellently done. The defense in depth stuff
and the first half of the third section I also found to be particularly
well done.

##### Course Pitfalls
The linux section was so base level I skipped the entire section (If you
know how to use chmod and partitions, you're almost finished).

I have a feeling SANS is sponsored by vmware, as all the quiz questions
in that section were really obscure vmware specific things ... coming from
a kvm/xen background, I was kind of disappointed the concepts weren't more
generic.

### OnDemand

I took the course thru the OnDemand online system SANS offered. Not too
much to say here, it is quite good. A somewhat edited version of a 
conference Dr. Eric Cole had taught earlier in the year. The quizes were
a great help, and much more difficult than the GSEC exam itself.

For anyone wondering, Eric's style of teaching was pretty awesome, 
I would not pass up the opportunity to attend a live lecture with him.

### GSEC Exam

GSEC is a proctored exam, pretty standard stuff. The testing center out
here is fairly bad, and had no knowledge about the course. **Make sure 
you print off the email GIAC sends you if you're taking this exam**. It
saved me a tonne of headache.

That headache would have came in convincing the exam center the exam was
open book -- which it is. You will use the books. A lot. The GSEC exam
isn't particularly difficult if you've studied and done the practice exam,
but there is just a metric fucktonne of information.

#### Exam Tips
##### Book Indices
Nothing major needed here, but will be the biggest lifesaver of the exam.
The books SANS give you are fairly flimsy, and not easy to quickly scim.
Having a reference index of what each page is clipped to the front of each
book is mandatory (IMO) for this exam.

##### TCP/IP + UDP Headers
Especially IPv6. Don't cheap out on your math skills, there will be
questions on this stuff. (Easy points)

##### List of Windows Programs
There are a hilarious amount of windows command line programs. There are a 
significant number of questions on the exam that ask about these. Having a
quick table lookup for sanity will save you time.

##### Incident Response Stages
While you could easily look this up, I think knowing all the stages and 
what to do (and what not to do) in each stage is worth knowing inside out.
Lets face it, creating references is just another way to teach yourself the
material, so may as well cash in here.

### Worth it?
Financially... no. At least, not if you're paying for it yourself. Time
spent? Yeah, maybe. Coming at it from a software engineering angle,
there is little to be gained besides a new perspective ... but perspective
is a powerful thing, especially in security. I don't think I would recommend
it to anyone who wasn't already looking at it however.

Would I recommend this course to someone with an IT background? Oh hell yes,
and I already have recommended it to a couple friends.

### Aftermath

I ended up scoring high enough on the GSEC exam to be invited to the GIAC
advisory board. Kind of a cool perk to doing well. Since you have to sign
a NDA to get access to it, can't really go into detail. You'll just have
to get 90%+ on a GIAC exam and come see for yourself ;)
