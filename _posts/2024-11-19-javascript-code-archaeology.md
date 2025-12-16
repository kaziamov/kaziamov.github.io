---
layout: post
title: Continuing JavaScript Learning - Code Archaeology
date: 2024-11-19 14:27
category: development
author: Ilia Kaziamov
tags: [javascript, learning, security]
---

Continuing the topic of learning JS. Yesterday had a call with a mentor, as I'm going through training related to this and some questions accumulated that needed to be discussed. The code we were analyzing is a service written by another developer that needs to be refactored, and I had difficulty understanding how authorization works in a full-stack application.

Sometimes it's not always clear why certain decisions were made by the previous developer, and when there's a mentor, they can guess based on experience why it was done exactly this way. This is such code archaeology and mind reading by code in one bottle.

The most critical bug found in the process of these excavations is an endpoint that accepts data from the frontend and generates tokens for client login. It turns out an attacker could simply create an account for themselves and grant access rights to the service with one request to the backend. This is my next task - to refactor this section so everything is protected.

The second potential refactoring candidate is a created authorization adapter that mixes user data with actions that can be performed during authorization. This can potentially create bugs if you don't know how to use this crutch. Ideally, authorization logic should be isolated and not depend on working with authorized user data.

Six months ago I might have rushed to refactor all this, now I seem tired of it and maintain a balance that probably should just patch critical places.

This is another thought I took from this call - fixing all problems is not required, it's enough to just do better than it was.
