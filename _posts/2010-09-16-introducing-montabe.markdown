---
layout: post
title: Introducing Montabe
date: '2010-09-16 22:15:36'
---

[Not to bury the lede: Montabe is a new photo and gallery management web application I'm building. You can <a href="http://montabe.com">sign up for a beta invite</a>.]

"I'd work on this for free," I said more than once during my time at <a href="http://www.indystar.com">The Indianapolis Star</a> while working on <a href="http://photos.indystar.com">AutoFocus</a>, the photo and gallery system that still powers the photos and galleries across the bulk of Star Media sites (it's made it through two site redesigns and counting).

From my very first day working in media, back at the relatively tiny <a href="http://newsandsentinel.com/">News &amp; Sentinel</a> in Parkersburg, W.Va., I've had a fascination with how we manage photographs. The first day, sitting at the photo wire terminal and watching Associated Press photos fly in from around the world hooked me.

I spent almost all my time in online media building and designing web applications to handle photos and collections of photos. I built systems in PHP and later Ruby. It's something I love to do and something I like to think I've gotten pretty good at. I know a lot of the pitfalls and I know the workflow inside and out.

Now divorced from the media world, I've felt that itch to do something with photos again. And I started noticing a definite pain point associated with them in my own family's life.

We run a <a href="http://benvannoy.com">website filled with photos of our son, Benjamin</a>. My wife does a fantastic job a) shooting the bulk of the photos (I keep telling her she should investigate doing it semiprofessionally) and b) managing the website. But the open source software that runs it is kinda clunky, kinda slow and not ideal. More importantly: My wife and I aren't the only ones that take pictures of Benjamin.

My family, her family plus various friends and acquaintances have photos of Ben sitting around on hard drives and camera cards. Getting those photos on the site usually involves getting them to email them to us, then uploading them to the site. The process sucks.

It's a fairly common pain point anytime you deal with photo projects that involve multiple photographers. We went to a friend's wedding in the past where they asked attendees to take photos and send them to them. I built a quick website to allow them to upload them, but few people did because it required a manual upload.

I also thought about, given my journalism background, breaking news events that require a call for photos. The ability to quickly deploy and populate a gallery of camera phone input would be really killer. Less journalism-like, what about a silly gallery that just has random camera phone shots of a city's nightlife?

There are ways to do some of this now. But most of them suck for me, and certainly for the general public. I can deploy an open source software package; they won't. <a href="http://flickr.com">Flickr</a> pools require all the contributors to be members of Flickr and you can't skin them in a design of your choosing (without a lot of API hacking).

My vision for the photo and gallery management application I'm building on nights and weekends, montabe, is to ease these sorts of pain points. I want to be able to move Ben's website to it and then upload photos to it directly from iPhone via MMS or email ... and let my family know they can send their photos there as well, without having to require them to sign up for an account. I want to see budget weddings that eschew a traditional photographer be able to easily update a gallery of contributions from the wedding's attendees (and have the gallery look good, too).

So, long-term, that's what I'm building montabe to be: A dead simple way to update a photo gallery from multiple sources and input methods (direct upload, MMS, email, maybe twitter hashtag down the road) that's flexible and theme-able.

It's not going to have all of this at launch, but I will eventually.

Because this feels like what my professional life has been building toward ... and it's time to start working on it.