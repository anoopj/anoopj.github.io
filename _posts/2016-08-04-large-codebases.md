---
title: Ramping Up on Large Codebases
author: anoopj
layout: post
permalink: /2016/08/large-codebases/
dsq_thread_id:
  - 3276951067
categories:
  - Blog
---

One of my colleagues asked for advice on ramping up on large
codebases. This is a complex topic where there is no right answer, but I'll
try to summarize what I learned over the years.

## Understand the software from the user perspective

Before you look under the hood, try to *use* the software as an end user and
gain an understanding of what it's supposed to do.

## Skim the docs

Read the available documentation (if there are any), but be aware that
technical documentation tends to go stale and is rarely kept
up-to-date. 

## Code reading

Reading and making sense of large code-bases is an art. A few tips:

* It is not realistic to read and understand a large part of the
codebase. Often times, you may want to focus on the most important parts of
the code that gives you the best ROI of your time.

* Figure out the important abstractions and try to create a mental model of
them.

* Look for invariants, pre and post conditions and side effects.

* Sometimes it's worth looking at the past checkins and understand how
  developers made changes to the codebase for specific projects.

## Use the right tools

You would want the right tools to navigate around large codebases. If
you're using Java or Scala, consider using an IDE. 

## Look at the tests

Unit and integration tests can provide insight into how individual
components are supposed to work.

## Use the Debugger

Sprinkle a few breakpoints and use a debugger to step through the code. 

## Learn by doing

Finally, the best way to learn is actually by working on specific
projects. Look at the roadmap/project list and pick tasks that balance
utility and your learning.
