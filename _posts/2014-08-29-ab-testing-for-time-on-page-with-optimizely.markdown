---
layout: post
title: AB Testing for time on page with Optimizely
date: '2014-08-29 20:39:44'
thumb: http://jekyll-blog-cv.s3.amazonaws.com/opt_circle_mark_BLUE.jpg
---

Sometimes, like say if you go with a [longform landing page](http://www.groovehq.com/blog/long-form-landing-page), a metric of success is going to be just how many folks stuck around long enough to read.

After all, if you put your call-to-action in the footer, there's no sense optimizing it if 90% of your visitors aren't on the page long enough to get there in the first place.

It's also a handy metric for AB testing your messaging and copy. Is it more engaging? Do more people actually read it? Time on page works as a nice proxy for those as well.

However, most AB testing platforms are optimized for more tangible actions - clicks, form submissions and the like.

At the day job, we do most of our AB testing through [Optimizely](http://www.optimizely.com), a platform that I can (and do!) highly recommend.

Here's how you would set up time on site as a goal in Optimizely; I'd imagine/hope most other platforms would be similar.

1. First, you need to figure out what the threshold time you're aiming for should be. You can eyeball it, time yourself reading your copy, run your copy through any number of libraries and services (this library looks particularly interesting: <https://github.com/hswolff/read-time>) or simply divide your number of words by 200 - the average words per minute speed for an adult.
2. Since we're going to be setting this up in javascript, You're next going to need to convert the number from No. 1 (let's call it 6 minutes) into milliseconds.

	`6 * 60 * 1000`

3. Now that we have a number for the average adult's time to read your text, I'd suggest lowering it by about a quarter or third. Even your most-attentive readers are going to skim at least a little (and if they don't, all the better!). 
4. Now we're going to add a bit of code to your page (which should already have the Optimizely code on page, naturally). There are probably ways to do this directly in the Optimizely interface (in fact, I'm sure of it), but I tend to find this approach a bit cleaner.

	Somewhere in your header or footer (below the Optimizely snippet), add the following, but with your milliseconds replacing the YOUR_MILLISECONDS area:

        <script type="text/javascript">
		  $(document).ready(function () {
            window['optimizely'] = window['optimizely'] || [];
		    setTimeout(function () {
			  window.optimizely.push(["trackEvent", "threshold"]);
		    }, YOUR_MILLISECONDS);
		  });
        </script>

	What the above block does is wait for YOUR_MILLISECONDS and then ping Optimizely with a [custom event](https://help.optimizely.com/hc/en-us/articles/200039925-Custom-event-goals) called "threshold". That custom event can actually be called whatever you'd like, but I feel that "threshold" seems to fit fairly well.

5. Now we're ready to set up our goal in Optimizely itself.

	![](http://cl.ly/image/0L2S3t150u3o/Screen%20Shot%202014-08-29%20at%204.22.24%20PM.png)

	Create a new goal. Under "What to Track," choose "Custom events."

	In the "Custom Event to track" field, enter the custom event you chose in Step 4 ("threshold" in the example case).

	Save that puppy and you're ready to start your experiment.

From this point, Optimizely will track the goal like all the others. Each time a visitors sticks on the page longer than your threshold, it will count as a conversion.

<hr />

Hope you like the above. A lot of my day job these days has been wrapped up in metric optimization and analytics.

Because I'm not quite busy enough, if you would like me to work my magic on your site - whether that's just suggesting AB tests, or implementing them, or simply digging into your analytics - do [get in touch](mailto:chris@chrisvannoy.com)

<hr />

**Update:** In case you were wondering how to do the above directly in the Optimizely interface, here's how:

Instead of Step 4 above, we're going to add our javascript to the Global Javascript area in the Optimizely interface (found under "Options", screenshots below.

![](http://cl.ly/image/2r2d2A0Y1u14/Screen%20Shot%202014-09-03%20at%204.39.12%20PM.png)

![](http://cl.ly/image/2m3o3h0R1k0X/Screen%20Shot%202014-09-03%20at%204.39.33%20PM.png)

Since Optimizely will wrap the code in a `<script>` tag for you, you'd paste the following in there instead:

		  $(document).ready(function () {
            window['optimizely'] = window['optimizely'] || [];
		    setTimeout(function () {
			  window.optimizely.push(["trackEvent", "threshold"]);
		    }, YOUR_MILLISECONDS);
		  });

Other than that, the procedure is exactly the same.
