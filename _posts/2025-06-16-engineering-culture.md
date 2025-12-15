---
layout: post
title: What Is an Engineering Culture Indicator for Me?
date: 2025-06-16 17:14
category: development
author: Ilia Kaziamov
tags: [engineering, culture, process]
---

You can start with the most banal - there's code review, tests are written (both on backend and e2e for frontend) and own QA in the team.

For tasks there's a simple and clear flow (it's close to ideal, which I described [here](./2024-11-26-ideal-jira-workflow)).

Good versioning. Due to the fact that this is gamedev and the main product is an online game, the rollout of new versions with new features and events is clearly defined. Therefore, you can roll out some parts of the application both into the past and two months into the future. A custom service was written to manage environments, where from the admin panel you can see the status of all stages and deploy the needed version, get logs, etc. In this example, the level of engineering culture for me is that a special service was written to automate this and it itself is an indicator of the team's expertise.

High level of automation in other things like CI/CD, i.e. between code in a branch and on the server - one button.

Besides this, there's also an internal library storage used for a compatible interface between applications. Some of them are auto-generated and created for different programming languages (python, go, js) so that access to functionality is available from any language to game interfaces, all covered by tests and will highlight if the interface in related services becomes outdated.

Part of the libraries remove code duplication, they're moved to an internal registry and added to the project as dependencies. This is also a very cool approach in my opinion.

And the last thing is probably high delivery speed as a result of all tools and approaches.

What's an engineering culture indicator for you?
