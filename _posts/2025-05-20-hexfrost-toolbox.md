---
layout: post
title: Writing Open Source Library - Hexfrost Toolbox
date: 2025-05-20 16:48
category: development
author: Ilia Kaziamov
tags: [opensource, python, library]
---

Writing an open source library that simplifies work (database, queues, testing, etc.).

Because if you want to create some pet project, writing boilerplate code takes a lot of time. There are special templates on GitHub, but this is again about copying, not about batteries included.

For example, if you need to get a client for requests to backend during testing, with the ability to debug code (as in Django, in FastAPI there's no such client out of the box and every time you need to copy-paste):

```python
@asynccontextmanager
async def debug_client(app, app_path: str = "http://test"):
    from httpx import ASGITransport, AsyncClient
    async with AsyncClient(
        transport=ASGITransport(app=app), base_url=app_path,
    ) as client:
        yield client
        pass
```

The standard client in FastAPI, for example, doesn't allow debugging code because the client works separately, backend - separately. Solution for me - take the client out to a library and in tests just pass a link to the application that will be tested.

Other cases for which there is/will be a solution in the library:
- Creating database connection, settings template and depends function for issuing connect, so you don't have to write it anew each time
- During testing, raising a separate database for running tests (again as in Django out of the box)
- Working with data encryption that can't be stored in open form and decryption back
- Code for working with authorization, middlewares and logic, so you don't have to write it from scratch
- Clients for working with queues (redis, rabbitmq) and their test analogs
- Decorators for logging and profiling
- Utilities for converting code to sync/async and back

Install and check functionality from the list above, possible from version 0.1.4b:

```bash
pip install hexfrost-toolbox
```

In the process it turns out that to write this library, functions from the library itself are used. Since to test part of functions, you need to raise a database or send requests through a client, it uses itself.

The first version of the library was released almost a year ago, and it had the most basic utilities, and I didn't have enough understanding how to do this better. Now it seems this understanding exists.

[Link to code](https://github.com/hexfrost) on GitHub, MIT license, so you can use however you want.
