---
title: 'Reliable Code'
categories:
  - misc.
tags:
  - life
  - google
toc: true
---

After 4 years in the industry, I still have so much to learn. At the same time, I've definitely come a long way in terms of writing reliable code.

After 4 years at Google, this is some of the rules of thumb I use when coding. None of these are original insights, but it took time to cluster them together in my head:

Embrace your tests! Specifically:

Make sure to have good test coverage for both unit and e2e tests. The time you'll spend developing them will pay dividends later on.

(Almost) never submit a code change without an associated test.

Prefer to use real implementations in tests over mocks/fakes.

Prefer to split test cases into success and failure groups. This makes the assertion testing logic simpler.

If possible, prefer state verification over interaction verification.

Create custom error types, to ensure your code isn't returning an unexpected error (hiding a bug).

Code submissions:

Submit small changes as much as possible! This makes code review easier for the reviewer, resulting in speedier and more thorough reviews.

Don't submit code changes on Friday or have weekend release blocks! Although it can be tempting to push out that feature, it can be quite frustrating to deal with an outage over the weekend when you have other plans...

Code design:

Stick to SOLID!

Avoid mutable global state, to prevent spooky action at a distance und unpredictability in your code execution.

Embrace refactoring:

Code is living thing, and ....
