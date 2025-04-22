---
title: 'Lessons from Building a Farewell Letter Website'
layout: post
categories:
  - google
toc: true
---

After losing several family members without getting a proper goodbye, I was inspired to create a website for farewell letters - messages that could be delivered to loved ones after one’s passing. I’ve been building this site with a close friend, and it’s been my first major personal project since leaving Google.

In this website, you can write letters to your loved ones, assign trusted contacts to update the site admins upon your death, and then have the letters be released to your close ones. For example, you can write a letter to your children, your partner, your friends and family.

It's been exciting to learn how tech things work "in the real world"! I wanted to share a few of my learnings.

## AI Agents

I've been using [Cline](https://cline.bot/) in VSCode to write my code, and it's been a superb help!

Cline is like a personal coding partner / tutor, which helps me learn the ropes of full-stack development. Cline saves me SO much time on tedious refactorings / setting up [language internationalization](https://react.i18next.com/) / boiler plate code. And Cline has been great at helping me learn new fullstack libraries!

Although I'm sure this comment will become obsolete quickly, as of April 2025, I think Cline (powered by Claude) can still improve a lot in generating meaningful unit tests. A lot of the tests Cline generates aren't actually helpful nor check what I actually care about. Cline also sometimes uses React hooks like [`useEffect`](https://react.dev/reference/react/useEffect) in unexpected and suboptimal ways.

## Add Dev Workflow Improvements Early On

There are a few features that I added to my development workflow that I’ll definitely incorporate earlier in future projects:

- **Husky precommits:** these are incredibly useful for ensuring code quality and catching issues early. They help with:

  - Running unit tests before committing code to ensure that they aren't broken by the changes.
  - Running linters to keep the codebase clean and consistent.
  - Auditing npm packages for known vulnerabilities or important updates.
  - Checking TypeScript type safety by compiling the code. Initially, I skipped this because the dev servers (e.g. Vite) ran fine without it—but that meant missing bugs that TypeScript would have caught at build time.
  - Enforcing commit message conventions, which makes it easier to track changes and understand what collaborators are working on.

  Setting up Husky in a monorepo took some trial and error - the documentation was a bit lacking. I ended up creating a Husky config at the top of the monorepo that delegated to Husky scripts in each subdirectory (e.g. frontend, backend).

- **Github Actions:** This one is important!

  - For running longer tests: e.g integration tests (Playwright or Lighthouse). It would be annoying to wait on these to run locally before committing.
  - For catching everything you would like to catch with Husky precommits, but on the server side. This is vital because you might have a collaborator who doesn't have Husky set up (that happened to us!)

- **Environment variables validation**: I'll elaborate on this in the next section!

## Silent Errors are a Killer

There were a few times when I was debugging issues with silent errors. You know something is wrong, but the error messages are entirely unhelpful!

- Frontend example: [Lighthouse](https://developer.chrome.com/docs/lighthouse/overview) is a great tool for analyzing a site's performance/SEO/accessibility. I was using it to improve my website, and Lighthouse tests were executing fine in my local environment. However, in Github Actions, Lighthouse kept failing to detect the site, with cryptic [NO_FCP errors](https://github.com/GoogleChrome/lighthouse-ci/issues/766). I spent hours trying to figure out what was wrong, only to discover that was missing environment variables in Github Actions so the site was failing to load. The error message was completely unhelpful and didn't point me in the right direction.

- Backend example: As my partner and I began transitioning our [NestJS](https://nestjs.com/) backend application to a serverless architecture, we faced challenges adapting the existing codebase to fit this new model. At some point we ran into silent errors that were difficult to debug. At some point we realized that the new [serverless.yml](https://www.serverless.com/framework/docs/providers/aws/guide/serverless.yml) file was missing a single environment variable (that we hadn't copied over from our [Yup env flag schema](https://github.com/jquense/yup) file).

The summary, and the lesson: validate for environment variables early on and ideally during build time! It's better than running into errors during runtime, especially when those errors can get obfuscated! I'm actually surprised that the popular Vite / NestJS templates don't come prepackaged with this.

## Hosting Platforms

I was surprised by how widely hosting platforms can vary in cost and usability.

- **Frontend hosting:** we initially started with a free month of Github Enterprise and hosted our frontend on [Github Pages](https://pages.github.com/). However, after the trial month, Github wanted to charge us $21/month _per collaborator_! So we moved to [Cloudflare](https://www.cloudflare.com/), which has a:

  - a free tier
  - a better GUI
  - doesn't charge per collaborator.

  Deployment with Cloudflare was also more straightforward. GitHub Pages, especially for organization-owned repos, required us to add an additional base path in the URL (configurable in `vite.config.ts` files). This nuance isn’t necessary when hosting from a user repo, but the documentation around this was confusing and wasted several hours of our time.

  On the other hand, when we switched to deploying on Cloudflare in coordination with [Github Actions](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions) (via [Wranglers](https://developers.cloudflare.com/workers/ci-cd/external-cicd/github-actions/)), we ran into some internal errors on Cloudflare that offered no indication of the core issue.

  So for now we have decided to stay with Github Actions for our CI/CD, and to build directly in Github Actions as well. We upload the `dist` output to Cloudflare directly. As a result, we are setting up our Frontend's environment secrets/variables in Github environments rather than in Cloudflare, which is a bit awkward. It works though, so we'll keep this setup for now.

- **Backend hosting:** we started with [Railway](https://railway.com/), which has a very nice GUI. However, they charged us a lot! We ran into one of those oh-so-classic Google "new-vs-legacy" scenarios: the new service Railway advertised, called [Railway Metal](https://docs.railway.com/railway-metal) was cheap, but it missed crucial features (such as static IP addresses). So we stayed with the old Railway service, which was much too expensive. We were paying about 1$ a day, although it was only me and my partner working on the site.

In addition, Railway's fine print was confusing; we thought we would pay $20 for the team, but it ended up being $20 _per collaborator_! (Silent groan).

We thus switched our backend to AWS Amplify.

## Running into Documentation Troubles

One of the biggest issues we faced was the lack of clear documentation for some of the libraries we used. For example, we use [NestJS](https://nestjs.com/) (based on [Express](https://expressjs.com/)) for our backend, since it promotes good structure for codebases. However, the template NestJS gives is for a "serverful" application. That's fine for local development, but when deploying to AWS, we needed to use a serverless architecture. This meant we had to figure out how to adapt the NestJS template to work with serverless, and that didn't come with detailed enough documentation.

## The Search for a WYSIWYG Editor

For our website, we wanted to let users write letters using a rich-text (WYSIWYG) editor. There are many editors out there - [this list](https://github.com/JefMari/awesome-wysiwyg-editors) gives a great overview. I was suprised that none of them quite matched what we needed.

- Some editors were beautifully designed but closed-source and/or came with steep licensing fees. As we don't necessarily intend to monetize this project, we wanted to avoid steep fees. We also want this site to run in 50+ years, so we wanted to avoid closed-source software that could become obsolete or unsupported.
- Some editors were open-source, but they were either too basic or too complex. Some of them apparently had breaking changes every few months, which is too risky for a long-term project.

We ended up using [Lexical](https://lexical.dev/), which is a free and open-source WYSIWYG editor developed by Meta. It has a lot of features and is very customizable, but has sparse documentation and can be quite overwhelming to polish.

Takeaway: as always, there is no such thing as a silver bullet. Finding the right tool often means compromising between features, cost, and ease of use.

## What Next?

I'm excited to wrap up this project and release it publicly. My partner and I are considering open-sourcing it, so that others can contribute as well. If we do open-source it, we'd love feedback or contributions from others interested in promoting death acceptance and death positivity. After that, time for the next project!
