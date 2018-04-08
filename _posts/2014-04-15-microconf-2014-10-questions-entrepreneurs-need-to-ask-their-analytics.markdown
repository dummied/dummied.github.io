---
layout: post
title: 'Microconf 2014: 10 questions entrepreneurs need to ask their analytics'
date: '2014-04-15 19:09:33'
tags:
- microconf2014
thumb: http://jekyll-blog-cv.s3.amazonaws.com/250px-Welcome_to_fabulous_las_vegas_sign.jpg
---

_NOTE: These recaps are a bit more for me than you. I’ll skip over stuff, include asides that are more personal notes to me, etc. Your mileage may vary. More detailed/sanctioned recaps will be available at http://microconfrecap.com at some point._

**Presenter:** [Annie Cushing](https://www.twitter.com/anniecushing)

* <http://annielytics.com>
* <http://bit.ly/tons-of-tools>
* <http://bit.ly/audit-checklist>
* I don't monetize anything. Anything to help people. Don't take business advice from me.

1. Which marketing channels are your unsung heroes?
	* Last-click attribution = all the credit goes to the last refer, doesn't matter what got them to that point. Don't sue it.
	* Multi-click attribution = gives equal allocation to each channel (social, organic, email, CPC) that user went through. So you can tell which channels are actually effective.
	* Assisted Conversions Report in Google Analytics (under Conversions > Multi-Channel Funnels). Last click or Direct Conversion value is last-click attribution.
	* If you have ecommerce tracking, deselect goals - they muddy the water. Bump the lookback date range to 90 days. API doesn't have the ability to change this lookback date range, limited to 30 days. Use the interface.
	* Social revenue almost always under reports in last-click
	* <http://bit.ly/ga-campaign-tagging>, skip to the "Fixing Your Default Channel grouping" section of the guide. Need to adjust campaign tracking.
	* Caveat: Multichannel funnels are not the same thing as the standard funnels.
	* Direct didn't get credit for last-click. With MCF it does get attribution. Its the main reasonMCF is its own little ecosystem.
2. Where do your best links come from?
	* There are no standard reports for the job. Custom report instead.
	* The standard reports aren't Google Analytics. They're templates. Rely more on custom reports.
	* Using "Full referrer" dimension. Some sources don't have a full URL (Facebook, Youtube, inbound.org). If you need to know, tag the links.
	* <http://bit.ly/referring-urls>
	* <http://bit.ly/api-help>
	* <http://bit.ly/custom-ga-reports>
3. What do visitors to your site search for?
	* Site search is your visitors' wishlist.
	* There is gold in these hills.
	* More sophisticated visitors use search.
	* Search terms report in GA. 
	* Do a search on your site. Need to be fullpage, not AJAX with a url. Note the query parameter. Admin > View, Site search settings, drop in query parameter, strip query parameters out of URL
4. How many pages does it take to convert?
	* You can find days/visits to conversions (Conversions > Time to conversion). Not a standard way to find out how many pages a person has to drill through the site to convert.
	* Apply an advanced segment. Builtin > Visits with transactions, close out all visits. That way you just have visits with conversions.
	* Then go to engagement to see how many pages it takes to convert.
	* Might have an issue is if it takes 37 pages to convert.This isn't high user engagement if you have a 0.02 conversion rate.
5. Should you consider going responsive?
	* Device Category > Landing Page
	* Then you can see bounce rate, revenue, conversion rate per mobile/tablet/desktop
6. Are you tagging all of your email?
	* Desktop apps don't pass referrer data (i.e.. Outlook, Mail.app)
	* Secure webmail providers don't pass referrer data
	* Mobile doesn't pass very much/most data
	* If you don't tag, it shows up as direct.
7. Which product categories convert?
	* Conversion by product category
8. Should your site go multi-lingual/national?
	* Check visitor countries and browser languages
	* <http://bit.ly/language-codes>
9. Which competitors are stalking you?
	* Network domain is the domain name of the registered service provider (ISPs). Larger orgs show up as own ISP.
	* Can also check for .gov/.edu visits.
	* Them group them with a segment, then stalk your stalkers
10. Are sites scraping your site?
	* Hostname report. Shows you all domains that have your GA tracking code. Scrapers aren't the sharpest knife in the drawer, they leave that code in there.
* <http://bit.ly/microconf-bundle>

# Q&A

* Search for brand, registers as organic, how to differentiate? Before not provided, you could set up a rule to change that to direct, but now you can't because "not provided" means you don't know what they searched for necessarily.
* How to get the original tweet from the t.co link? You should be tagging social links. Twitter used to show up as direct, then Twitter added a wrapper around all links. Check the full referral report, you'll get the link. 
