---
layout: post
title: Introducing PinboardDigest
date: '2013-10-18 16:00:00'
---

[PinboardDigest](http://cvprojects.s3.amazonaws.com/PinboardDigest.workflow.zip) is a small OSX System Service intended to take a lot of the drudgery out of producing roundups of links, such as posts like my [Around the Web roundup](http://blog.chrisvannoy.com/around-the-web-hiring-and-management-links-for-october-17/) earlier this week.

Essentially, it allows me to feed links into [Pinboard](http://pinboard.in) through the week and tag them with "blog_roundup".

When it comes time to write the roundup, I open up [Byword](http://bywordapp.com) (my writing editor of choice) and hit this Service to pull down the 10 most-recent Pinboard bookmarks with that tag in my account, convert them into a [Markdown][0161-001] formatted list and stick them right where my cursor is in the document.

I wrote this primarily because producing those sort of posts before was a pain in the ass: I'd gather links over days or weeks and stick them in Pinboard, and then need to head into Pinboard and do all the aforementioned by hand. If I know anything about myself, it's that any amount of friction to producing something means I'm less likely to do it.

## Features

* The Service is available in every OSX application. It works (or is intended to work) anywhere you have a cursor in a text box.
* Can pull from 0-3 tags with each pull. So, you can pull from none to get just your 10 most recent bookmarks, or combine a few of them.

## Installation

**Dependency:** To decode the response from the [Pinboard API][0161-002], this workflow relies on the <code>json</code> gem, so you'll need to install that if you haven't already.

Of note, you'll need to have the [XCode Command Line Tools](https://developer.apple.com/xcode/) installed to do this.

Open a Terminal window, and type:

<code>sudo gem install json</code>

And you should be good to go. If you're a Ruby developer using [rvm][0161-003] or [rbenv][0161-004], make sure you install <code>json</code> in the system Ruby, since the Service uses <code>/usr/bin/ruby</code>.

On with the show:

1. [Download the workflow file.](http://cvprojects.s3.amazonaws.com/PinboardDigest.workflow.zip)
2. Double-click the zip file you just downloaded to extract the <code>.workflow</code> file.
3. Place that workflow file in <code>HOME/Library/Services</code> (or just double click it). It should become available immediately.

## Configuration

![](http://jekyll-blog-cv.s3.amazonaws.com/automator_screenshot.jpg)

You first will need to give the script your [Pinboard auth token](https://blog.pinboard.in/2012/07/api_authentication_tokens/). Once you have that, open the Service in Automator (by double-clicking the file in the aforementioned <code>HOME/Library/Services</code> folder).

In the second step of the workflow ("Run a Shell Script"), you should see a line that reads:

<code>AUTH_TOKEN = "YOUR\_AUTH\_CODE\_GOES\_HERE"</code>

Put your Pinboard auth token in between the quotes, save and close the file.

If 10 bookmarks at a time is not your style, you can also adjust the number of links the Service pulls on the next line.

## Usage

![](http://jekyll-blog-cv.s3.amazonaws.com/service_screenshot.jpg)

In your editor of choice (or a web form, or whatever), put your cursor where you'd like your digest to start (I'm usually starting from a fresh document, but your mileage may vary and PinboardDigest don't care).

In the app menu (upper left), you should see a Services item. Inside that, you should find PinboardDigest.

Click that and it asks you for any tags you'd like it to pull and then whisks off to fetch them for you and format everything up nice and neat.

## Caveats and Miscellany

* The guts of this Service are written in Ruby and are [available as a gist](https://gist.github.com/dummied/7051472).
* To enable the Service to work with almost any app that has a text field and a cursor, it uses the system clipboard to move some of the text around. Obviously, any text you have in your clipboard when it starts is going to get wiped out.
* Taking a moment to give a big thank you to [Brett Terpstra][0161-005], [Dr. Drang][0161-006] and others for the inspiration.

## ToDos

* The Service doesn't really have any error handling to speak of at the moment.
* The clipboard bit I mentioned above feels like a kludge, so I'm [open to suggestion](mailto:chris@chrisvannoy.com) if anyone has better ideas.

[0161-001]: http://daringfireball.net/projects/markdown/
[0161-002]: http://pinboard.in/api
[0161-003]: https://rvm.io/
[0161-004]: https://github.com/sstephenson/rbenv
[0161-005]: http://brettterpstra.com/
[0161-006]: http://www.leancrew.com/
