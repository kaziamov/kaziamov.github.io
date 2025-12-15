---
layout: post
title: Ideal Jira Workflow
date: 2024-11-26 11:24
category: development
author: Ilia Kaziamov
tags: [workflow, jira, process]
---

If we imagine that tasks in Jira are code, we can describe their proper functioning using a state machine. With proper implementation, a task can only be in one state. If a task has two significant features that determine status, it most likely means these are two different statuses.

Here's what an ideal task flow looks like using an example from my previous job:

To Do > In Progress > In Review > In Testing > Approved > Done

This flow is logical and intuitive. Task completion implies merging into the main branch and deploy, which provides an asynchronous format of working with the task. An error at each step resets progress to one of the previous stages.

For example, if the solution is written and goes to review, but the code is dirty or insufficiently covered by tests, this will be immediately clear and the task can be returned to work with minimal costs. After approval in review, the developer moves the task to "In Testing" status, and people responsible for testing can take over work with this task. If testing is not passed, the task returns to work, and after rewriting code, review will need to be passed again. If everything is ok, the task gets approval and becomes a candidate for merging into the main branch.

Now let's imagine the situation if we swap testing and review. People who test spent time confirming that the task's functionality is ready, and in review it turns out the solution is not very good. If tests are written, rewriting the solution to a new one won't be much trouble - a kind of refactoring. But the weak point is time, since it was already spent checking functionality and will require repeating the check to get approval. This doesn't mean users and testers can't try new functionality before this stage (each branch with properly configured CI/CD will be deployed separately from others). The question is in acceptance of this functionality, because this is the step that tells the developer everything is ok, and the task is completed, no need to slip into endless corrections.

Speaking about such an aspect as asynchronicity of work, for teams working in different time zones, Jira becomes a place where you can track task development. Conditionally, completed a task in the evening, sent for testing, came in the morning - it can still be in the testing queue, be approved, or return to "In Progress" status with indication of reasons what's wrong. In such conditions, it's very convenient to plan your work time because everything is clearly visible.

This is my opinion on this matter, what work organization have you encountered?
