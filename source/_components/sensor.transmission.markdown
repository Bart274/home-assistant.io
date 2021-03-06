---
layout: page
title: "Transmission Sensor"
description: "Instructions how to integrate Transmission sensors within Home Assistant."
date: 2015-04-25 9:06
sidebar: true
comments: false
sharing: true
footer: true
logo: transmission.png
ha_category: Sensor
ha_release: pre 0.7
---


The `transmission` platform allows you to monitor your downloads with [Transmission](http://www.transmissionbt.com/) from within Home Assistant and setup automation based on the information.

```yaml
# Example configuration.yaml entry
sensor:
  platform: transmission
  host: IP_ADDRESS
  port: 9091
  name: Transmission
  username: YOUR_USERNAME
  password: YOUR_PASSWORD
  monitored_variables:
    - 'current_status'
    - 'download_speed'
    - 'upload_speed'
```

Configuration variables:

- **host** (*Required*): This is the IP address of your Transmission daemon, eg. 192.168.1.32.
- **port** (*Optional*): The port your Transmission daemon uses, defaults to 9091.
- **name** (*Optional*): The name to use when displaying this Transmission instance.
- **username** (*Optional*): Your Transmission username, if you use authentication.
- **password** (*Optional*): Your Transmission password, if you use authentication.
- **monitored_variables** array: Conditions to display in the frontend.
  - **current_status**: The status of your Transmission daemon.
  - **download_speed**: The current download speed.
  - **upload_speed**: The current upload speed.


To use the monitoring, your transmission client needs to allow remote access. If you are running the graphical transmission client (transmission-gtk) go to **Edit** -> **Preferences** and choose the tab **Remote**. Check **Allow remote access**, enter your username and your password, and uncheck the network restriction as needed.

<p class='img'>
  <img src='{{site_root}}/images/screenshots/transmission_perf.png' />
</p>

If everything is setup correctly, the details will show up in the frontend.

<p class='img'>
  <img src='{{site_root}}/images/screenshots/transmission.png' />
</p>

