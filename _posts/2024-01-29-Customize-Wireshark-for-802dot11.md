---
layout: post
title: "Customize Wireshark for 802.11"
---

Wireshark is a powerful tool to analyze traffic capture and study flow of protocols or exchange between devices into a network. This type of tool, help for us troubleshooting.

By default, Wireshark is not tunnig. The default profile is most useful to analyze 802.3 traffic capture that 802.11. For this reason, in this blog I present some features to change the default profile, to custom for analyze 802.11 frame.

## Add Profile

Is most useful create your own “Profile” to apply all configurations to see 802.11 Frames. To “Add” new profile go to:
Edit> Configuration Profiles, click on “+” bottom and add profile.

![_config.yml]({{ site.baseurl }}/images/2024/B2AddProfile.png)

This profile will be select on the bottom-right side of the screen.

![_config.yml]({{ site.baseurl }}/images/2024/B2SelectProfile.png)


Once we have our own profile, we can do the Tunning 😄 The next feature that I will present are:

* **Columns Preference**
* **Coloring Rules**
* **Display Filters**
* **Filter Butttons**
