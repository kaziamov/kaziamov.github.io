---
layout: post
title: Broke 3811 Tests and Volunteer Project
date: 2023-10-10 08:29
category: development
author: Ilia Kaziamov
tags: [testing, volunteer, fastapi]
---

Yesterday broke 3811 tests, but no I don't write code that badly. Some strange bug appeared on CI. Just an interesting situation, wanted to share.

On the weekend continued writing a volunteer project. In total spent 68 hours on it already, according to wakatime (of course it doesn't account for time reading documentation and thinking through solutions). The essence of the project is that it's a system for moderating chats for a non-profit organization with an ML model for content analysis. All this is written on FastAPI + SQLalchemy2.0 + Aiogram3, plus for registration there's a self-written system for authorization and token issuance, and for registration notifications a small library for email distribution. The ML model is moved to a separate API, I didn't really participate in writing the backend, only helped with asynchronous database work and a bit with small things.

In general, after such experience, there was a desire to write an open source library for chat moderation, where you can connect various platforms like Telegram, Discord, and others, and manage all this through a single interface.
