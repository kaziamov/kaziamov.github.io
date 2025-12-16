---
layout: post
title: Experiment with Return Values Performance
date: 2023-11-08 19:03
category: development
author: Ilia Kaziamov
tags: [python, performance, optimization]
---

Today conducted an interesting experiment, after words from a team colleague that returning a value with creating a variable and without differs in performance.

At first I thought the difference can't be too big, and you can forget about it. But as a result of measurements, it turned out that returning values without variables in two sequential function calls gives a speed increase of ~27%.

I don't yet know how to relate to this information, strive for speed increase or stick to better code readability, but in general, I'll consider this and apply it. And I'll try to delve into studying code execution speed and optimization.

Code and measurement results here: https://gist.github.com/kaziamov/d863ca91ed24034b22fb3e7a5d748bf2
