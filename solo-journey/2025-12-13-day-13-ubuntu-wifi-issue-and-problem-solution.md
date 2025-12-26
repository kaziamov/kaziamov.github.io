---
layout: post
title: "Day 13: Ubuntu 20.04/22.04/24.04 "
date: 2025-12-13
category: tools
author: kaziamov
tags: [linux, ubuntu, infrastructure]
---

Today I have reinstalled Ubuntu (24.04 -> 20.04) cause it has issues with WiFi which kinda disturbed.


UPD.
Issue was not in OS, it was a complex issue related temporarily to dns settings and power saving settings. I used preconfigured router parameters for ad filtering, apparently something changed in the provider settings of this service and requests to github over SSH began to be blocked (It looks like nothing happening, just `git pull/push` without responce or error). In addition, the wifi was dropping, which made debugging the problem difficult, because it seemed like an interconnected problem.

Solution
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