---
layout: post
title: The Wild West of Remnant Advertising
date: '2010-02-24 22:13:08'
---

First a little context: <a href="http://startribune.com">The Minneapolis Star-Tribune website</a> earlier this week had <a href="http://blogs.citypages.com/blotter/2010/02/star_tribune_in.php">an advertisement</a> that included a bit of a social engineering hack related to viruses (according to a Twin Cities blog).

Said post also includes an offhand mention of other newspaper websites owned by Gannett having a similar ad.

As soon as I saw the headline come across my feedreader, I thought, "Goddamn remnant ads."

I can nearly guarantee no one at The Star Tribune approved, scheduled or even saw the ad before users started complaining. And you might be wondering how that sort of thing could happen.

Web advertising at large newspaper and media websites (at least the ones I've worked at), works something like this:

The newspaper website has a lot more ad inventory than its salespeople can sell. Especially in non-local areas such as Nation/World.

Each ad position on a page calls the main ad server (in Gannett's case, <a href="http://gannett.gcion.com">gannett.gcion.com</a>) through javascript and says, "Give me an ad." Said ad server checks to see if it has any local- or network-scheduled ad. If it does, that ad, which generally has been seen, approved and checked, is sent down to the user.

Failing that, it will pass the request for an ad on to another server to fill the spot, sight-unseen.

And these third-party, or "remnant" (because they get the leftover) ad providers are unscrupulous customers.

You've seen these ads. The dancing mortgage people. The teeth-whiteners.

The sketchiest of the sketchy.

And the dirtiest of the dirtiest.

In my time at The Indianapolis Star, we saw remnant ads include large files intended to do nothing but <a href="http://antivirus.about.com/od/securitytips/a/historysniffing.htm">sniff your browser history</a>.

Eighty-percent of the time, when users or staff would complain about page speed, we knew without looking there was a third-party ad to blame.

They're either bloated with logic to sniff out users' information or coded so poorly that it just takes forever to load.

As an example, a lot of remnant ad designers think of their little ad box as a separate little webpage: including their own javascript libraries, regardless of whether or not the site they appear on already has those libraries installed. Worse yet, they sometimes will include them in a such a way that they conflict with the libraries on the parent page and wreck the whole thing.

These ads are bad, and they don't make publishers much money, bringing in a significantly lower CPM than local- or network-sold advertising.

So why do newspaper websites (and large media websites in general) continue to use them and continue to increase ad inventory with no hope of ever selling ads in those spaces?

Because it's free money.

It's not much money, granted, but you have zero overhead. Slap an ad position on a page and you get back fractions of a penny every time that ad gets viewed.

No local salesperson is needed or involved. The third-party ad network takes care of sales, scheduling and delivery.

When you lose that local overhead, though, you also loose something more important: control over the ads your users see.

When you have a bad ad, how do you turn it off? You have to call somebody, wait on hold, explain the ad, get them to understand the problem and then turn it off. You can't turn the ad off, the third-party advertiser has to do that work.

Meanwhile, the whole time you're on hold and haggling, that damn ad will still be on your site, ruining your good name and permanently driving away readers.

Or you do what The StarTrib did: you turn off <em>all your ads</em> and bleed money by the second and pageview until you get everything resolved with the ad providers.

I will argue (and have argued), that what newspaper and other media websites need, financially, is fewer ad positions, not more. It reduces the reliance on untrustworthy and damaging third-party ads and can help drive up the CPM-per-ad on those locally sold.

Better yet, put pressure on your ad departments: You only get ad positions you have sold. If you don't have an ad for this spot, it goes away.

Fill the spots, for whatever price you can get, because we aren't going to let somebody else do it for you anymore.