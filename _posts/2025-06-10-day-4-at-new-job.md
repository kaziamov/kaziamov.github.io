---
layout: post
title: Day 4 at New Job - First Task Completed
date: 2025-06-10 19:59
category: work
author: Ilia Kaziamov
tags: [work, development, django]
---

I finished the task simply because I decided not to complicate things given the incomplete requirements picture. I sent it to the team lead for review and voiced three variants of how I planned to do it. Eventually, I needed to redo it to another voiced variant. I rewrote the code and fixed tests in half an hour, but ran into a 500 error from the server. I fixed it and sent for review. I got approval and sent the task to testing. Then I took the next task to work on.

While working on the task, I noted that the frontend was written very well and allows dynamically forming data depending on types of incoming data. That is, the frontend doesn't know what fields it will render, and expected fields don't appear in the code at all - only their types. I really liked such implementation.

In the Python code, I encountered such a construction: `dict1 |= dict2`, as a short form of `dict1.update(dict2)`. Nice surprise to learn something new. Together with the fact that I'm now actively using Podman and trying to work with clusters in GCP, I had a desire to record new training videos for YouTube.

Yesterday I set up a 4K monitor, which made it comfortable to work. You could say I bought it purely so that PyCharm with all sidebars fits on the screen. That's all for now, keeping you posted.
