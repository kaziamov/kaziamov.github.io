---
layout: post
title: How to Delete Git Branches Locally and Remotely
date: 2023-09-21 11:52
category: development
author: Ilia Kaziamov
tags: [git, tips, workflow]
---

How to delete a branch locally and from GitHub.

I already create extra branches accidentally not for the first time and this then hangs in the editor, and I decided to write instructions for myself on how to clean all this up. Otherwise they hang in the editor, cause extra cognitive load when switching branches.

```bash
# delete locally
git branch -D branch-name

# delete remotely
git push origin -d branch-name

# if remote_name is not origin, then need to change
```
