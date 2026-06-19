---
title: "Polluter Finder"
description: "A tool that hunts down the PR or commit that polluted your build by breaking the tests."
pubDate: "Jun 19 2026"
heroImage: "/blog-placeholder-1.jpg"
---

**Polluter Finder** is a project that helps you find the commit responsible for your test failures. When a test suite goes red, the hardest question is usually *which change broke it?* — and Polluter Finder is built to answer exactly that.

## The idea

Think of a broken build as a polluted one: somewhere in the stream of merged pull requests, one change introduced the failure. Polluter Finder finds the polluter.

## How it works

For a range of suspect changes, Polluter Finder automates the tedious detective work:

1. **Clone each PR / commit.** It checks out every candidate revision, one at a time.
2. **Build it.** Each revision is built in a clean state so results are reproducible.
3. **Run the tests.** The suite runs against that exact revision.
4. **Identify the culprit.** By comparing which revisions pass and which fail, it pinpoints the PR or commit that first introduced the failure.

## Why it helps

Instead of manually bisecting history, rebuilding by hand, and re-running tests over and over, you let Polluter Finder do the loop for you. The result is a clear answer: *this* commit is the one that broke things — so you can revert, fix, or follow up with confidence.

It turns "something in the last dozen merges broke the build" into "here is the exact change to look at."
