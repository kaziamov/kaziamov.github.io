---
layout: post
title: Refactoring Lessons from Work
date: 2023-09-13 19:42
category: development
author: Ilia Kaziamov
tags: [refactoring, best-practices, work]
---

At work got a task where the code had a lot of duplicate code from 6 years ago.

I decided to take this on, and here are the conclusions I made for myself:
- Refactoring should be done in small parts (yes, an elephant piece by piece)
- Code duplication is not the main problem. If code repeats but has simple logic, then no problem. Shouldn't fix this
- Decorators are most often not needed in code because they add non-obvious behavior. If behavior applies to all inherited objects, better to extend the class, if in one or several, then override
- Most of what in theory is divided into bad and good practices is all individual
- Typing and documentation. If you decided to make old code section good, then need to add all necessary tools so it's clear next time when you have to get into this code section. And so the editor pulls all types and the logic is clear why everything was done exactly this way
