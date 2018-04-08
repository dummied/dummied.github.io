---
layout: post
title: rvm and SearchLink, can't we all just get along
date: '2013-10-15 21:05:02'
---

Just a quickie post in case somebody else runs into this problem (and to see if anyone has a better solution).

I'm a Ruby developer part of the time, so I manage my rubies through [rvm][8474-001] most of the time.

I'm also increasingly a writer, and one that _loves_ him some [Markdown](http://daringfireball.net/projects/markdown/), so I wanted to try using [Brett Terpstra][8474-002]'s [SearchLink][8474-003] so I don't always have to break flow to go hunt down a URL or go back in later to add them.

However, the stock set up kept failing. And after opening up the Automator workflow file, I found the problem.

The workflow is, by default, set up as inline Ruby code using the <code>/usr/bin/ruby</code> path to the system Ruby install. Which meant the <code>json</code> gem wasn't installed as far as that particular bit of Ruby (and the script) is concerned.

I spent a bit of time trying to just get <code>json</code> installed in the system Ruby before throwing up my hands and doing the following instead:

1. Download Brett's [gist of the Ruby code](https://gist.github.com/3900158).
2. Take note of where that file lands (or put it where you'd like).
3. <code>which ruby</code> in a terminal window. Take note of the value.
4. Edit the workflow or set up a fresh one to look like the following:

![Screenshot of Automator workflow](http://jekyll-blog-cv.s3.amazonaws.com/Screen_Shot_2013_10_15_at_4_55_30_PM.png)

Where the first bit is the Ruby path and the second is the path to the gist.

###### One other odd bit

I suspect this is more a problem with the [Ghost](http://ghost.org) interface than Brett's script, but when running SearchLink on text directly in the admin interface, it borks the whole thing, replacing the text with a "_". Luckily, it's easily undoable, but it might not hurt to have it stashed in your clipboard, or to save a draft before trying it out there.

For now, I'm writing in [Byword](http://bywordapp.com/), running SearchLink and then pasting the Markdown into Ghost.

[8474-001]: https://rvm.io/
[8474-002]: http://brettterpstra.com/
[8474-003]: http://brettterpstra.com/projects/searchlink/
