---
layout: post
title: Vapor and Swift on the server
date: '2016-09-14 09:01:25'
thumb: http://jekyll-blog-cv.s3.amazonaws.com/swift-og.png
---

Between cohorts at [The Iron Yard - Indianapolis](https://www.theironyard.com/indy), I've been playing around a bit with other languages and frameworks in preparation for the [PLIBMTTBHGATY](http://plibmttbhgaty.com/) shindig I'm hosting on September 24, 2016 at the TIY campus here in Indy.

I wanted to throw together a small web app where attendees could register themselves and list what languages they were interested in exploring so some groups can form naturally (and I might be printing nametags from that information as well).

Since I'm hosting things, I figured I won't have much time to explore at the event so I'm doing my exploring ahead of time - building the backend with something new and then exploring a frontend using [Elm](http://elm-lang.org/).

Along the way, I tried [Crystal](https://crystal-lang.org/) & [Kemal](http://kemalcr.com/), [Elixir](http://elixir-lang.org/) & [Phoenix](http://www.phoenixframework.org/), [Rust](https://www.rust-lang.org/en-US/) & [Iron](http://ironframework.io/), [Go](https://golang.org/) & [Gin](https://gin-gonic.github.io/gin/), and a few oddball experiments in Haskell.

The combination that got me across the finish line, however, surprised me: [Swift](https://swift.org/) & [Vapor](http://vapor.codes/).

Surprised because while I knew Apple had announced Swift's move to open source and the promise of having it running on Linux servers, I hadn't thought to check in on progress for these fronts since.

With all of these experiments, it was a bit of a bear. I'm a Rubyist by heart and I haven't worked with a compiled language since my freshman year of college - nearly twenty years ago at this point. All of these combos (outside of Elixir/Phoenix) are also fairly young and have _lots_ of rough edges here and there - especially when it comes to documentation.

Vapor, however, hit the right sweet spot for me of a familiar-seeming language and just enough [docs](https://vapor.github.io/documentation/) and [community](http://vapor.team/) for this to be challenging but doable without too many frustrations.

Here are some initial impressions and tips:

### Vapor

At the moment, Vapor really only works out of the box with [MySQL](https://www.mysql.com/). There are [providers](https://github.com/vapor?utf8=%E2%9C%93&query=-provider) on the way for things like [Postgres](https://www.postgresql.org/) but they're not [fully baked yet](https://github.com/vapor/postgresql-provider/issues/1).

Depending on how you have MySQL set up (notably, if you did so using [Homebrew](http://brew.sh/)), the regular `vapor build` will not work and you instead need to dip into `swift build` directly with something like this: `swift build -Xswiftc -I/usr/local/Cellar/mysql/5.6.25/include -Xlinker -L/usr/local/Cellar/mysql/5.6.25/lib -Xswiftc -DNOJSON` to get around MySQL not being compiled with JSON storage types.

The DSL for routing I found particularly interesting as a combo of [Sinatra](https://sinatrarb.com) (just declare the routes and actions right in your `main.swift` file) and [Rails](https://rails.org) - with controllers and actions and all the rest.

The other bit I found intriguing is [type-checked params](https://vapor.github.io/documentation/routing/parameters.html#type-safe) - deciding ahead of time what the type of the params should be - all the way to declaring that a param on a `show` action will be a Model, and Vapor automatically loads the Model instance from the database based on the param.

Some things I didn't particularly like:

- The SQL behind all this is _very_ obfuscated. No queries are logged, there are no migrations to speak of. It's all a bit magical and unless you know going in what's _likely_ going on, you're going to be lost.
- A lot of the documentation outlines many different ways to accomplish something rather than showing off the really nifty ways to accomplish the same thing. Such as: serializing a collection of objects to JSON ([`return try Attendee.all().makeNode().converted(to: JSON.self)`](https://github.com/dummied/plibmttbhgaty_vapor/blob/master/Sources/App/Controllers/AttendeeController.swift#L13)).
- The boilerplate `vapor new <app name>` project includes a lot of demo code that needs deleted before you can really get started. Again, it's nice to show off features, but to actually start working, there's a lot of deleting going on. In fact, my completed app at the moment still has a ton that I need to delete out of there - starting with the README.
- What Vapor (and almost of all of these) need in addition to documentation are tutorials - much like Rails' from scratch-to-blog-in-15-minutes from back in the day. Something that can get interested folks to successful in a short, straight line.

One of the biggest tips I have is to borrow _liberally_ from this [ToDo App example](https://github.com/vapor/todo-example).

### Swift

One of the other big advantages to this is Swift itself. Swift on the server is still a bit of a novelty, but the language itself is in heavy use by Apple app developers and it's exceptionally Google-able.

As a Rubyist, the language as well feels pretty comfortable and familiar. It supports a [block-like syntax](http://fuckingswiftblocksyntax.com/) that feels like a Ruby block in all the right ways. The compiler error messages are reasonably helpful (I saw better in my explorations, but they're generally fine).

One short recommendation: you can write all of this in Vim and the like, and I started that way, but using XCode instead is unsurprisingly a better experience.
