---
title: "My Technical Journey at Google: Comparing Teams/Projects"
categories:
  - google
  - code
tags:
  - teams
toc: true
---

In my team at Google, I've been on 3 vastly different teams. Each team has varied in culture & style, and each team had its strengths and weaknesses. I'm grateful to have been able to be a part of each, and wanted to share a breakdown of what I did and learned in each one.

# Team 1: Android/iOS Notifications

In my first team, I developed new features for sport and weather notifications to Android and iOS phones. For instance, XXX.

What I especially appreciated about this team was:
 
 - open communication and receptivness of the other devs and management chain
 - my manager's technical expertise on the product (she had been a developer before becoming a manager)
 - fantastic unit tests: our customers were "the real world" and our unit tests tested each setting meticulously. 
 - the opportunity to learn about A/B testing and see it's impact
 - the opportunity to learn about the importance of slowly rolling out features in order to prevent large blast radiuses for hidden bugs.
 - the importance of being in touch with customers to understand what they need. Someone else on my team developed a [Word of the Day](https://9to5google.com/2022/06/22/google-word-level/) daily notification, and the words were human approved. The early experiments showed that the initial words selected were too easy, and users required more challenging words to hold their interest!

# Team 2: CodeSearch Backend

In my second team, I worked on the backend of [CodeSearch](https://developers.google.com/code-search), which software developers at Google use to search through the massive Google codebase. CodeSearch is responsible for both indexing and searching.

I joined the team looking for a challenge and passionality excited about this product - it's one that I use every day at work!

What I appreciated about this team was:

- the incredibly high technical skills of the other devs. Seeing them debug issues and design algorithmic solutions was very inspiring.
- working on a product that I was so excited about! It's so motivating when I'm passionate about the product.
- learning to be onduty and triage incoming bugs.
- learning about indexing safety: e.g. the real-time indexers to index new code submissions, but also the "catch all" periodic back-up indexers who make up for any issues that stopped the real-time indexers from indexing the changes.
- learning about how to configure alerting for batch metrics which may hint at problems. Ee.g. a drop in the # of submissions indexed per 3 days - note this normally alerts during Christmas!
- learning about 'probers' or 'service monitors' to sanity check complex systems by issuing a user-like interaction request.

# Team 3: Sescuring Google Usage of GCP

GCP....