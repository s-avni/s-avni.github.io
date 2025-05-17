---
title: 'Comparing My Farewell Letter Website to Other Services'
layout: post
categories:
  - personal development
  - website
  - coding
toc: true
---

As I detailed in my [previous post](https://www.shiriavni.org/google/2025/04/19/developing-epitaphs.html), a friend and I are currently developing a [website](https://epitaphs.pages.dev/) as a side project. The site we're developing lets you write farewell letters that will be shared with your loved ones after your death. I thought it would be useful to compare our website to other services, to see how the site stacks up.

## Table of Comparisons

| Site / Features: | [Dead Man's Switch](https://www.deadmansswitch.net/) | [My Wishes](https://www.mywishes.co.uk/) | [Afterwords.life](https://www.afterwords.life/) | [Go-Paige](https://go-paige.com/memories/) | [Our Website](https://epitaphs.pages.dev/) |
|---|---|---|---|---|---|
| Supports Public Messages | No | Yes | No | IDK, couldn't register <br>without<br>an American phone number. | Yes |
| Supports Private Messages | Yes | No | Yes |  | Not yet. |
| Message Release Mechanism | Service sends periodic emails to <br>your email address. <br>If you don't respond after X <br>time, messages are sent. | Assigned loved ones inform <br>the site of your death. | Assigned loved ones inform<br>the site of your death, or<br>you can have messages <br>sent at a certain date/location. |  | Assigned loved ones inform<br>the site of your death. |
| Cost | 50 USD  | Free | Free |  | Free |
| Message Content Limitations | Bare bones text only | Bare bones text + <br>upload up to 1 video | Upload a photo/video/<br>audio recording/document.<br><br>No option to write text<br> directly in the app. |  | Supports text in various <br>colors/fonts/sizes.<br>Supports<br>embedding photos and<br>uploading videos. |
| Platform | Website + <br>Android App <br>(app is buggy) | Website only | Android + <br>iOS App (no website).<br><br><br>App is pretty but is<br>buggy and randomly <br>crashes. |  | Website only |
| Other Features |  | Provides support for other <br>end-of-life services: <br>funeral planning, will writing,<br>etc. <br><br>Supports sending messages at <br>different intervals after <br>your death (e.g. 1 month after <br>your death, or on<br>specific desired dates). |  |  |  |

## Comparisons & Thoughts

Our site stands out in terms of the writing experience, offering a clean WYSIWYG editor (based on Facebook's [Lexical](https://lexical.dev/)), supporting custom fonts, colors, and media uploads including images and videos (though we’re still ironing out a few bugs).

Our site is running on a serverless architecture, which causes loading spinners to appear briefly on initial load. We'll need to work on that.

Other platforms offer other features that we lack: some have dedicated mobile apps, others allow you to schedule multiple messages to be sent at specific times after your passing. I also appreciate that the [MyWishes](https://www.mywishes.co.uk/) site includes message templates to help users get started.

A few of the services that I tested felt buggy or unreliable. That’s why I think our most meaningful contribution might be to open-source our project and focus on making it stable and trustworthy for anyone who wants to use it. An added bonus is that there will be less pressure on my friend and I to maintain the site entirely ourselves.
