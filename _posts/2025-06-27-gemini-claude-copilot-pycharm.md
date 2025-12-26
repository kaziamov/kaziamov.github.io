---
layout: post
title: About Gemini, Claude, Copilot and PyCharm
date: 2025-06-27 13:12
category: tools
author: Ilia Kaziamov
tags: [tools, ai, development]
---

I tried corporate Gemini as a copilot. The PyCharm plugin installed and login was ok, but VSCode - no, gives an error and says no rights, although authorization through the browser passed.

The first task I suggested was to find an error in a .vue template. Result: three attempts in a row, it returned an answer in XML format. Among the scarce three settings, I didn't find what to change. In general, combined with non-working autocomplete and absence of agent mode, this was the last attempt with it.

Plus, when I tried to get an answer through the web version, it's also not inspiring - doesn't know how to read documentation and argues that it's not possible (although the documentation says it is). On the example of DRF, it turned out that reading the documentation and doing as planned is faster than arguing with AI. My conclusion: for code, Gemini doesn't work.

Another interesting observation is that fresh models like Claude 4 are brought to the Copilot plugin for VSCode faster. I noticed this three days ago; for PyCharm I didn't see updates or the model. Only 3.5 and 3.7 as it was. And subjectively, in VSCode copilot works faster than in PyCharm.
