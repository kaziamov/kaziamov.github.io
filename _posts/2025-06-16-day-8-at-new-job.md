---
layout: post
title: Day 8 at New Job - Debugging and Gemini
date: 2025-06-16 18:55
category: work
author: Ilia Kaziamov
tags: [work, debugging, ai, django]
---

Was figuring out a debugger bug. Suspicion was on Django RQ, which runs a separate thread, the Redis library that does the same, and middlewares, but they quickly got out of suspicion by simple elimination. Used corporate Gemini to speed up the solution. Because my own attempts to find what's wrong with threads didn't succeed. Several deep researches went down the drain because with his reasoning he found errors that weren't in the original query and tried to solve them. Tried with both models 2.5 and 2.5 Pro. Eventually, in one of the simple answers was a variant with a bug in the pytest-timeouts library, and that was bingo. Updating from 2.3.1 to 2.4.0 solved the problem.

As a result, debugged with the debugger a test that needed to be done for the task, and sent the task to testing. The previous task was already tested and merged into the main branch. So far this is a record for the speed of adaptation and getting into work.

From non-work: mounted 5 videos for my Python course that I filmed on the weekend and uploaded to YouTube and Stepik. Stepik doesn't please me honestly, don't think I want to develop all this on it, but I don't see alternatives yet.
