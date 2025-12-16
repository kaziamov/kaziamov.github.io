---
layout: post
title: Tried Vibe Coding with CursorAI
date: 2025-05-23 13:26
category: ai
author: Ilia Kaziamov
tags: [ai, cursor, development]
---

Probably can already write about trying vibe coding with CursorAI.

The last year or two I've just used Copilot in my work, but working with an agent system I never got around to. One fine evening I paid for Cursor and decided to check its capabilities. First I wanted to make a pet project for my own needs, a link shortener with analytics and other extended capabilities. The ideal for me is Yourls, which I deployed back in 2018 when I tried WordPress. There are no Yourls alternatives in Python.

Without thinking long, I uploaded their repository and asked to rewrite everything to Python. Without delving into what was happening, I only checked functionality and pointed out shortcomings. Basic functionality was transferred in 4 hours, which is generally impressive. Don't think anyone could have written from scratch or rewritten from PHP to Python a full application with templates in such time. If you want to see what happened, the repo link is here -> [Yourls Python](https://github.com/kaziamov/yourls-python).

I also tried to write a PyCharm plugin, which I never got around to. After two hours, the agent still couldn't launch an environment where the plugin would work, so you can consider this wasted time. You could say this isn't the vibe coding process and you need to figure out what and why Java isn't working there. Surprisingly, I also tried creating Android applications in Java, and an application with a conditional one button compiled and launched without problems. Apparently this is a simpler task than a plugin for another program.

Another project was my pet, which I write to practice and implement my wishes. After the first wow experience with stacks I don't master, I started checking how it works with what I understand.

The first couple of hours I was honestly spitting, because it just changed any parts of code not considering context and breaking tests. Tried to adjust code to tests, for example, rewriting initialization logic instead of fixing test fixtures for new functionality.

Conclusions: when working where you need a result that needs to be maintained, you need to formulate tasks in full and very specifically. If there are examples of tests or ready logic, need to attach them and tell the LLM to orient on them. Limit the field of action to those models that should be affected, so there are no attempts to rewrite what shouldn't be rewritten. In general, probably these are already well-known tips when working with ChatGPT.

This is generally a cool activity and you can generally use things like Cursor for some tasks, but not for tasks that require deep immersion and understanding of the subject area, because redoing will be more painful, and formulating longer than writing it yourself.

For me, vibe coding will remain the process when you just write code, there's a cup of hot coffee nearby, your favorite playlist plays in your ears, and you have control over the process and you create something new with your own hands.
