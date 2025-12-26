---
layout: post
title: "Day 13: Ubuntu 20.04/22.04/24.04 "
date: 2025-12-13
category: tools
author: kaziamov
tags: [linux, ubuntu, infrastructure]
---

Today I reinstalled Ubuntu (24.04 -> 20.04) because it had issues with WiFi which was quite disturbing.


UPD:
The issue was not in the OS - it was a complex issue temporarily related to DNS settings and power saving settings. I used preconfigured router parameters for ad filtering. Apparently something changed in the provider settings of this service and requests to GitHub over SSH began to be blocked (it looks like nothing is happening - just `git pull/push` without response or error). In addition, the WiFi was dropping, which made debugging the problem difficult, because it seemed like an interconnected problem.

Solution:
1. Disable ad filtering settings for my laptop
2. Go to /etc/NetworkManager/conf.d/default-wifi-powersave-on.conf and change wifi.powersave = 2


Before:

```[connection]
wifi.powersave = 3 # wifi was almost immediately turned off if the laptop was running on battery
```

After
```[connection]
wifi.powersave = 2
```