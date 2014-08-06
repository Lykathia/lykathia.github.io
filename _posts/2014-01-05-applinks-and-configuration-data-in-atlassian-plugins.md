---
layout: post
title: "Atlassian Stash Hooks: UI, applinks and configuration data"
category: programming
tags: [atlassian, scala, javascript, closure]
---

**Preface**: This article is mostly discussing UI related annoyances
when dealing with Atlassian Stash hooks. Their javadoc is *alright* if
you can find what you're looking for, so I'm skipping that part.

Also, this is all based around Stash ~2.8. A lot of my complaints have
been getting a lot better with each successive release.

### Background

Why scala? Why not! I've been in love with the language, and was looking
for something to create in it. The request for this plugin came up at
work, and I figured it was a good time to start learning.

### Getting Setup

As an Arch Linux user... just install the SDK from the [AUR](https://aur.archlinux.org/packages/atlassian-plugin-sdk/).

    /opt/atlassian-plugin-sdk/bin/atlas-run-standalone --product stash


Now that all that is out of the way, lets move on to the technologies
that Atlassian is using for UI.

### Components
In order to have a plugin come together there are a couple components
you need to include or be aware of. I'm not sure that there is a 
definitive list out there as to what all is available, but here is
what I used to get things done.

* applinks - API for talking to other linked Atlassian products.
* soy - Markup/templating for creating configuration screens.

#### Applinks

There are many ways to skin a cat. Getting data from applinks seems
to follow that idelogy.

My first thought process was to somehow pass the data into the soy
templates directly. This seems to be possible, but with an insane
amount of overhead... I didn't persue this road.

Getting the data thru some kind of rest controller and filling it in
via javascript was the next best bet. A quick look at the stash rest
documentation gave me zero direction. A quick look at the applinks
rest documentation gave me zero direction. I wrote my own rest controller
to pass the jira url to javascript but both [JIRA](https://jira.atlassian.com/browse/JRA-30371)
and [STASH](https://jira.atlassian.com/browse/STASH-3826) are missing 
[CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing)
headers.

Of course it's possible to reinvent the wheel and use the applinks API
to get all the data the built in JIRA rest API provides. Luckily 
I came accross [this post](https://answers.atlassian.com/questions/222396/applinks-in-javascript-get-project-keys-from-jira) which confirmed my suspecions that I shouldn't have to.

Yay easily searchable documentation...

#### Soy

Speaking of documentation, Atlassian has close to zero documentation 
around their soy implimentation. It **is** marked as experimental
however... although it seems to be the proper direction to move in.

Soy, also known as [closure templates](https://developers.google.com/closure/templates/)
compile down to javascript files that are used to render the configuration
screen when a user turns on the plugin. Since it's dynamically generating
the HTML whenever the user activates it, any javascript has to be hooked
right into the templates.

Since the documentation around this stuff doesn't exist, going directly
to the [source](https://bitbucket.org/atlassian/aui/src/1e089a5d956f3ee3e936600b48c2becb84695c7f/auiplugin/src/main/resources/soy/atlassian/?at=auiplugin-5.3.x) is required to know what is available.  
Since I'm only dealing with forms, there are a slew of awesome helper
methods defined as *aui.form.thingField*, where thing is your standard
slate of form related DOM objects (select, password, file, radio, etc).  
Calling these follows a pattern, and generally will look like this:

    {call aui.form.selectField}
        {param id: 'unique-identifier' /}
        {param labelContent: 'Label for unique-identifier' /}
        {param descriptionText: 'Description for unique-identifier' /}
        {param options: [
            [ 'text' : 'Select option 1', 'value' : '1', 'selected' : true ],
            [ 'text' : 'Select option 2', 'value' : '2']
        ]/}
        {param errorTexts: $errors ? $errors['unique-identifier'] : null /}
    {/call}

The error messages as defined above are for the users benifit. The errors 
you get from the stash UI during development are pretty useless. Don't even 
waste your time there. ```tail -f amps-standalone/target/stash-LATEST.log```
will be your best friend.

#### And for everything else there's ~~masterc~~ javascript

As a huge fan of [noscript](noscript.net), turning to javascript is never
my first choice. Even though these soy templates compile down to javascript
-- meaning that nothing will work without it anyway. Sigh!

##### Select Fields
It doesn't look like there is any good built in way to set what data 
is persisted with with soy. Perhaps using switch cases... but I haven't
looked into that yet.

##### Atlassian Select2 Fields
Again, something that is [marked as experimental](https://docs.atlassian.com/aui/latest/docs/auiselect2.html).
But this just looks and feels so much better then the default ctrl+click 
multiselect.

Pretty easy to initialize if we're following the template from above.

{% highlight js %}
exports.postLoad = function() {
    ...
    AJS.$("#select-soy-id").auiSelect2();
}
{% endhighlight %}

However there is something to be warned about here. If you're doing any
select field manipulation in the rest of your javascript, it has to be
done **BEFORE** you transform the field into a select2 input. The 
transformation changes all of the identifiers and does a bunch of DOM
manipulation.

### Conclusion
With all that said and done, you can check out the Stash hook I'm currently
working on [here](https://github.com/Lykathia/stash-jira-hook).
