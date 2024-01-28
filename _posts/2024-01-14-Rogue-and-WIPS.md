---
layout: post
title: AP Rogue and WIPS
---

In this blog I talk about Rogues APs and WIPS, and how works on my Cisco Lab.

## Topology

In the next topology, you can see my lab. I have a VirtualC9800, and two APs C9120 on Flex Mode associate with it, the SSID that I use is "LAB-WIFI". On the right I have a WLC3504, with only one AP 3702, and configure the same SSID "LAB-WIFI".

![_config.yml]({{ site.baseurl }}/images/RogueLAB2.png)

The scenario is the follow:
I have my Corporate SSID “LAB-WIFI” on the Virtual9800 Platform, and I active two Rogue Rules. The first rule classifies to malicious and contain others SSID that have the same name of my managed SSID. The second rule classifies to malicious and contain others SSID that contain the sub-string “LAB-W”.

These are Rule:

### Rule 1° "Managed SSID"
![_config.yml]({{ site.baseurl }}/images/LABroguerule1.png)

### Rule 2° "Substring SSID"
![_config.yml]({{ site.baseurl }}/images/LABroguerule2.png)


On C9800, I configure WLAN "LAB-WIFI"  with WPA2+802.1X Security and on WLC3504, I configure WLAN "LAB-WIFI" with WPA2+PSK.
![_config.yml]({{ site.baseurl }}/images/wlan-config.png)

## Testing
The objective of this lab are configure and test the Rogue Rules. We have two ways to confirm that contention is apply.
The first way is going to the C9800, in the menu "Monitoring" see the Rogue options, and select "Malicious" Tab. On this Tab we are see, one SSID (of the other platform) with MAC Address "64f6.9dad.de34", and the status is "Contained". With this status we know that rules are working.

![_config.yml]({{ site.baseurl }}/images/Rogue-evidence.png)


The second way to confirm that contention is working, is make a 802.11 Capture. In the next picture We see a 802.11 capture on channel 11. I filter this capture to see only "Deauthentication" frames, and we see this type of frame, and when see the details, We confirm that, these frame have a Source MAC Address "64f6.9dad.de34", and destination are Broadcast.

### Deauth Frames
![_config.yml]({{ site.baseurl }}/images/deauthbroad1.png)

### Deauth Frames Details
![_config.yml]({{ site.baseurl }}/images/deauthbroad2.png)


## Conclusion
The first conclusion is that rule are works xD. All contention works fine on 2.4Ghz band, When We needs make a contention on 5.0Ghz band the things are not easy, because the contention does not work on DFS channels. And the other think is, the contention does not work on SSID that have MFP, because the Mgmt of this type of SSID are protected. When the client see a Deauth frame, not make an actions and keep the connection.

Note: For this moment, I do not have a space for comment. Please if you have a comment, send me an email.


