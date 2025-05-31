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

<div class="overflow-table-wrapper">
<table>
  <thead>
    <tr>
      <th>Site / Features:</th>
      <th><a href="https://www.deadmansswitch.net/">Dead Man's Switch</a></th>
      <th><a href="https://www.mywishes.co.uk/">My Wishes</a></th>
      <th><a href="https://mygoodtrust.com/future-message">My Good Trust</a></th>
      <th><a href="https://www.afterwords.life/">Afterwords.life</a></th>
      <th><a href="https://epitaphs.pages.dev/">Our Website</a></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Supports <br>Public Messages</td>
      <td>No</td>
      <td>Yes</td>
      <td>No</td>
      <td>No</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Supports <br>Private Messages</td>
      <td>Yes</td>
      <td>No</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>Not yet.</td>
    </tr>
    <tr>
      <td>Message <br>Release Mechanism</td>
      <td>Service sends periodic emails to <br>your email address. <br>If you don't respond after X <br>time, messages are sent.</td>
      <td>Assigned loved ones inform <br>the site of your death.</td>
      <td>Assigned loved ones inform<br>the site of your death, or<br>you can have messages <br>sent at a certain date/location.</td>
      <td>Assigned loved ones inform <br>the site of your death.</td>
      <td>Assigned loved ones inform<br>the site of your death.</td>
    </tr>
    <tr>
      <td>Cost</td>
      <td>50 USD</td>
      <td>Free</td>
      <td>Free</td>
      <td>Free</td>
      <td>Free</td>
    </tr>
    <tr>
      <td>Message <br>Content Limitations</td>
      <td>Bare bones text only</td>
      <td>Bare bones text + <br>upload up to 1 video</td>
      <td>Upload images and videos of up to 5 minutes. Also supports basic text.</td>
      <td>Upload a photo/video/<br>audio recording/document.<br><br>No option to write text<br>directly in the app.</td>
      <td>Supports text in various <br>colors/fonts/sizes.<br>Supports<br>embedding photos and<br>uploading videos.</td>
    </tr>
    <tr>
      <td>Platform</td>
      <td>Website + <br>Android App <br>(app is buggy)</td>
      <td>Website only</td>
      <td>Website only</td>
      <td>Android + <br>iOS App (no website).<br><br>App is pretty but is<br>buggy and randomly <br>crashes.</td>
      <td>Website only</td>
    </tr>
    <tr>
      <td>Other <br>Features</td>
      <td></td>
      <td>Provides support for other <br>end-of-life services: <br>funeral planning, will writing,<br>etc. <br><br>Supports sending messages at <br>different intervals after <br>your death (e.g. 1 month after <br>your death, or on<br>specific desired dates).</td>
      <td>Provides other end-of-life <br>services</td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>
</div>

## Comparisons & Thoughts

First off, I'll say that [My Future Message](https://mygoodtrust.com/future-message) seems like the clear winner. It has a lot of neat features and has a great GUI.

Our site does stand out in terms of the writing experience, offering a clean WYSIWYG editor (based on Facebook's [Lexical](https://lexical.dev/)) with custom fonts, colors, and media uploads including images and embedding video links (though we’re still ironing out a few bugs).

Our site is running on a serverless architecture, which causes loading spinners to appear briefly on initial load. We'll need to work on that.

Other platforms offer additional features that we lack: some have dedicated mobile apps, others allow you to schedule multiple messages to be sent at specific times after your passing. I also appreciate that the [MyWishes](https://www.mywishes.co.uk/) site includes message templates to help users get started.

A few of the services that I tested felt buggy or unreliable.

## Bottom Line

Given that [My Future Message](https://mygoodtrust.com/future-message) is a neat and ready product, I think our most meaningful contribution would be to open-source our project and focus on making it stable and trustworthy for anyone who wants to use it. An added bonus of open sourcing this project is that there will be less pressure on my friend and I to maintain the site entirely ourselves.
