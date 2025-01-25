---
title: '4 Years Later: Back to Blogging'
layout: post
categories:
  - life
tags:
  - google
toc: true
---

It's amazing how time flies. The last time I posted on an earlier version of this blog was in August 2020, shortly after I was accepted to Google. Fast forward nearly 4 years, 3 teams, and 1 continent later, and the itch to restore my blog has returned.

# Content Updates

I didn't migrate all my old posts - most of the book reviews, math/physics musings, and miscellaneous Python experiments didn't make the cut. I also found an old post about the reactions to my short haircut! I enjoyed re-reading it, but didn't bother to port it over. In short, Israel is still quite conservative in many ways, and the response to my short hair was (and still is) surprisingly strong.

I did keep the old posts about my Oxford and Google applications, as I still get asked about those quite frequently.

What's next? Going forward, I plan to write more about my experiences & learnings at Google. I'm also planning on dabbling in some open source projects, and I'll write about that as well.

# Infrastructure Changes

## ~~Trying Out Wordpress~~

For the first incarnation of this blog back in 2018, I used Jekyll & Markdown, and hosted my site on Heroku. Without proper templates, I found it frustrating that my website wasn't very mobile-friendly.

Now, in 2024, I decided to try to avoid the UI headaches and check out WordPress. I signed up for the $80 WordPress annual subscription, knowing it was refundable within the first two weeks. It took me just over 2 hours to realize that WordPress was a mistake.

As I began porting my blog posts from Markdown to WordPress, I encountered one post with mathematical expressions. To my surprise, Wordpress doesn't support that out of the box. Instead, I needed some math plugin for it, but installing plugins isn't included in the $80 subscription! I would need to upgrade to the $300 subscription in order to be able to use plugins, but that felt too excessive when I can get that for free in so many other places.

I also quickly realized that, in the future, porting content out of Wordpress would be a huge pain. There does appear to be a plugin for exporting content in Markdown format, but it's not trivial.

I found the process of adding tags and categories to be a tedious, post-by-post manual task. I already missed the flexibility of tweaking layouts and canceled the subscription.

## GitHub Pages & Remote Themes

And so, I've decided to return to Jekyll, preferring its UI challenges over those of WordPress. I needed to refresh my knowledge of Jekyll, but fortunately, it's a fairly intuitive generator. It was great to discover that GitHub Pages could host my blog for free and that I could easily use [remote themes](https://talk.jekyllrb.com/t/github-pages-use-of-remote-theme/1737), which saved me a lot of UI hassle. It seems like this functionality was already supported when I started my old blog in 2018, but I must have missed it.

I've also decided to use the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme. The downside is that it's not immediately clear how to change the layouts for all my posts at once, as the theme handles a lot behind the scenes. While the mobile pages aren't perfect, they are significantly better than what I would have created myself.

All in all, a good compromise on quality vs time!

## Domain Registration

In 2018, I used GoDaddy domains to register my domain. This time I wanted to try out Google Domains, but unsurprisingly, I found out that Google Domains is no longer available (see https://killedbygoogle.com/ if you haven't already!). I went with Squarespace this time. :)
