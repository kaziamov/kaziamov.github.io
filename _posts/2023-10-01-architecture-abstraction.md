---
layout: post
title: Architecture and Abstraction Layers
date: 2023-10-01 12:16
category: development
author: Ilia Kaziamov
tags: [architecture, refactoring, planning]
---

Well, continuing to write backend for the volunteer project - logic is getting more complex.

I understand that abstraction layers have started to leak.

And here the question arises in my head, what to do, and such options come:
1) Draw a diagram of how the application works. At the beginning the logic was simple and you could do without a diagram.
2) Leave as is and forget about technical debt, finish the project, and leave all refactoring problems to Ilia from the future.

Option 2 is simpler, but I don't like it. First, because come on, I can do better. The second moment is that the project is potentially growing and in the future, if everything goes well, we'll need to expand. Which means there will definitely be problems. If I was writing a project that no one needs and won't grow, you could stop at the moment "don't start writing code" or "thanks, I'll decline participation in your project".

Option 1: Breathe out. Accept that it will take some time, that playing with architecture will 100% save time in the future and just start doing it. Draw a diagram, lay out by layers what sends requests where. Anticipate taking into account expansion plans, how it will work later and lay straw in advance. Plus, most likely change the structure of some database tables because it seems I overcomplicated it (or not - hard to know and no one to consult with).

I like option 1 because it's not slapdash, and in the process I'll clearly level up, so I'll choose it.
