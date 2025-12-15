---
layout: post
title: PyCharm Memory Settings Fix
date: 2023-10-06 06:28
category: tools
author: Ilia Kaziamov
tags: [pycharm, settings, performance]
---

After switching to PyCharm encountered such a problem as freezes. That is, the editor simply freezes solid and doesn't respond to anything. Guys from the work chat said it might be a memory problem. Like you can even enable Memory Indicator at the bottom on the panel. I now shows about 900/2048 when I just launch the project. In general, so as not to check whether it was in it or not (and this is an irritating factor when you're working and writing code, and then you need to suddenly terminate a hung application, restart and restore tabs and train of thought), so I went to settings and changed.

If useful to someone, settings are located in:
```
~/.config/JetBrains/PyCharm2023.2/pycharm64.vmoptions
```

Parameter that needs to be changed:
```
-Xmx4096m
```

I changed to 4096, will see if this continues with the disabled memory indicator, will know if the bottleneck was memory or another reason. Such are the junior's everyday life ))
