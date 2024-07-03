---
title: 'Google: My Journey Across Multiple Teams'
categories:
  - google
  - code
tags:
  - team culture
  - work
toc: true
---

During my time at Google, I've had the privilege of working on 3 vastly different teams. My motivation for this post is to give you a glimpse into the diverse working environments within Google. My work on each team varied widely, and so did each team's culture!

# Team 1: Android/iOS Notifications

In my first team, I developed features for sport and weather notifications for Android and iOS phones. For example, I worked on migrating certain iOS sport notifications to a pub-sub model to ensure users receive game results more quickly. Android already had the pub-sub model, but iOS features often lagged a bit behind Android ones.

I also launched several new variations of weather and sport notifications. These included weather notifications detailing forecasted temperature deltas for the next day and sport notifications with post-game video links. It was especially interesting to analyze the variance in notification results across sport types and countries!

Several of my projects focused on improving infrastructure and fixing up technical debt. For instance: migration to smaller [protocol buffers](https://protobuf.dev/) reduce SSD usage server migrations.

## A Day in the Life

On this team I spent a lot of time writing design docs and coming up with A/B experiments. I regularly met with Product Managers to brainstorm what new features users would enjoy, and collaborated with our partner team in the USA. My time alternated between spending weeks or days on feature design and idea brainstorming, followed by periods dedicated to implementing the features

## What I Especially Loved

- The open communication and receptiveness of the other devs and management chain.
- My manager's superb technical expertise (she had been a developer on the team before becoming the team's manager).
- A very healthy code base & great test coverage!
- Designing, launching and analysing multi-armed A/B testing.
- Learning how to slowly & safely roll out new features to reduce blast radii.
- Extremely organized feature launch process: the team had a superb culture of clear design docs, e.g. containing sections for motivation / experiment plan / hypotheses / legal / privacy / bandwidth / qps / storage analyses.

# Team 2: CodeSearch Backend

In my second team, I worked on the backend of [CodeSearch](https://abseil.io/resources/swe-book/html/ch17.html), the tool that Google software developers use to search through Google's massive codebase. You can think of Codesearch a bit like [Github's CodeSearch](https://github.com/search?type=code&auto_enroll=true) tool.

I joined the team seeking more algorithmic work and was very excited about the product itself, as I use it as a Google developer every day. I spent most of my time developing features for the team-wide "Git multibranch project". This project would enable indexing and serving of hundreds of projects in Git, and be especially important for git-using Google teams such as Android or Chromium.

Among other things I:

- Introduced and implemented support for new search atoms ('repo', 'branch'). It was challenging coming up with search logic that would be both (a) intuitive/straight-forward to the user and (b) require readable code logic. For instance, we had to decide if these new search atoms should have support for negation, if the 'repo' or 'branch' atoms could stand alone, and how nested queries would work. The edge cases were a fun challenge to ponder!
- Developed probers to monitor the health of the Git indexing and serving stack. Different probers were required to answer different questions, e.g:
  - Is there any (new or old) code that isn't being surfaced at all (i.e. a completeness issue)?
  - Is there any newly submitted code that is taking too long to be processed and surfaced to users (i.e. a freshness issue)?
- Modified the search results returned by the backend so that frontend developers could surface all Git branches for a given file to the user in the GUI.

I also worked on improvements for a batch service that processes queries periodically on the entire [Google3 codebase](https://news.ycombinator.com/item?id=39052528). The batch service is cheaper to run since latency is not a priority and many interesting metrics can be gleaned with it (e.g. how many usages of the Java function X appear in in the codebase over time).

## A Day in the Life

Lots and **lots** of code! I normally spent 80% of my day writing code, reading code, designing algorithms, or handling bugs as part of my onduty shift. It often felt like bootcamp!

I worked on interesting algorithmic challenges and in comparison to my first team, I had limited interaction with other teams. An exception was my regular interactions with our [SRE team](https://cloud.google.com/blog/products/devops-sre/how-sre-teams-are-organized-and-how-to-get-started), who are oncall for the tool and handle emergency alerts or pages.

As a side note, I believe it was detrimental that we had such limited interaction with other teams. Our team was siloed, and there was too much work for too few people. I also encountered some interpersonal issues within the team, which ultimately led to me look for a new team at Google.

## What I Especially Loved

- The incredibly high technical skills of other developers: seeing them debug issues and design algorithmic solutions was very inspiring.
- Working on a product that I was so excited about.
- Learning to be onduty and triage incoming bugs.
- Learning about indexing safety: e.g. requiring both real-time indexers for new code submissions and periodic (batch) back-up indexers to cover any oversights of the real-time indexers.
- Learning how to set up batch metrics, alerting, and 'probers' or 'service monitors' to sanity-check complex systems by issuing a user-like interaction request.

# Team 3: Securing Google's Internal Usage of GCP

In my current team I focus on [GCP firewall management](https://cloud.google.com/security/products/firewall?hl=en) for Google-internal teams using GCP. My teammates and I are responsible for an intermediary layer between GCP and the Google internal teams using GCP firewalls - this layer oversees and facilitates how the teams manage their firewall policies in GCP, ensuring they adhere to Google's security and reliability specifications.

On this team, I've finally had the chance to design and implement a large, multi-person project from scratch. The challenges involved in starting a project from zero compared to developing features for an existing project were of a different caliber and instructive!

When I joined the team, it was an [SRE](https://cloud.google.com/blog/products/devops-sre/how-sre-teams-are-organized-and-how-to-get-started) team, so I had the opportunity to learn about being oncall and to gain my first holistic view of products at Google. This experience has helped me understand products more comprehensively end-to-end (e.g. monitoring, alerting, reliability), which was something I missed in my first two SWE teams when I worked on specific features in a more narrow-focused manner.

By now the team has become a SWE team as well yet it retains a lot of its great SRE culture.

## A Day in the Life

Code-wise, I code about 50% of my time - more frequently than in my first team but less frequently than in my second team. I've been doing a lot of interesting design work focusing on infrastructure challenges, and as TL of my sub-team I'm also busy with ensuring that all the other teammates have clear projects and are unblocked.

Compared to my previous teams, in this team I have the most cross-organizational partnerships and associated meetings. I collaborate with Security Engineering teams, the Google internal client teams, and our numerous dependency teams.

## What I Especially Love

- The incredible willingness of teammates to help each other, even on completely unrelated tasks. I think this is part of the SRE culture that I appreciate so much...
- The diverse expertise among teammates, in contrast to more uniform expertise in my previous SWE teams. Since the teammates on this team were each previously SREs for different products owned by different teams, the teammates together encompass a broad range of knowledge, making brainstorming sessions very enjoyable.
- Learning how numerous partner teams can collaborate and align, and understanding the challenging requirements and political patience for successful collaboration.
- Coding in Go! It's my favorite language at Google so far. In my previous teams I coded in C++ or Java, and while I could go back to those languages, I would rather not!
