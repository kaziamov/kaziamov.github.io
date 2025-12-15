---
layout: post
title: Planning Personal Finance Pet Project Stream
date: 2023-09-27 10:22
category: development
author: Ilia Kaziamov
tags: [fastapi, pet-project, stream]
---

Since Monday will be a holiday and I got a spontaneous day off, I'll probably try to do a stream where in real-time I'll write a pet project that I've been putting off for a long time.

This will be a backend on **FastAPI + Aiogram + SQLalchemy + PostgreSQL**.

For web page rendering, I know **jinja** or making frontend as a separate project, don't know yet, will decide later.

Deploy **Railway** or **Heroku** (haven't decided yet whether to use familiar Railway or try Heroku, don't want to stumble during stream), locally in **Docker**.

About the project itself, the problem:

Finance tracking is tedious when you have several cards in several currencies. Especially if it's a family budget and there are many incoming/outgoing payments and they intersect. Using Excel for this is inconvenient because when it comes to analytics, making slices by dates, filters, currencies, accounts is painful.

Quickly making changes is also inconvenient, especially when cash payment happens, so a Telegram bot will be used where you can pass data and write to the database.

So if you have ideas or questions about the project/stack, you can write under the post.
