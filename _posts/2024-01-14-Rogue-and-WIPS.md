---
layout: post
title: AP Rogue and WIPS
---

In this blog I talk about Rogues APs and WIPS, and how works on my Cisco Lab.

## Topology

In the next topology, you can see my lab. I have a VirtualC9800, and two APs C9120 on Flex Mode associte with it, the SSID that I use is "LAB-WIFI". On the right I have a WLC3504, with only one AP 3702, and configure the same SSID "LAB-WIFI".

![_config.yml]({{ site.baseurl }}/images/RogueLAB.png)

The scenario is the follow:
I have my Corporate SSID “LAB-WIFI” on the Virtual9800 Platform, and I active two Rogue Rules. The first rule classifies to malicious and contain others SSID that have the same name of my managed SSID. The second rule classifies to malicious and contain others SSID that contain the sub-string “LAB”.

