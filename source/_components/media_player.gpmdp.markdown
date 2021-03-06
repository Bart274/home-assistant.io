---
layout: page
title: "Google Play Music Desktop Player (GPMDP)"
description: "Instructions how to integrate GPMDP into Home Assistant."
date: 2016-05-09 08:00
sidebar: true
comments: false
sharing: true
footer: true
logo: gpmdp.png
ha_category: Media Player
ha_iot_class: "Local Polling"
ha_release: 0.20

---


The `GPMDP` platform allows you to control a [GPMDP](http://www.googleplaymusicdesktopplayer.com/) instance running on a computer from Home Assistant.


You will have first have to check "Enable playback API" in GPMDP's settings and then add an inbound rule to the firewall to allow access to port 5672 on the computer running GPMDP.

Then just add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
media_player:
  platform: gpmdp
  address: IP_ADDRESS
  name: NAME
```

Configuration variables:

- **address** *Required*: IP address of the computer running GPMDP
- **name** *Optional*: Name of the player

