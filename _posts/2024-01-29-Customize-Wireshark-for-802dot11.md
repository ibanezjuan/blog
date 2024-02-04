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


## Columns Preference
Columns help us access to information on the capture faster, by default WireShark have some columns, but you can add or delete these as your requirements. I use these:

* **SSID** fields “wlan.ssid”
* **SA** by default
* **DA** by default
* **PHY Type** fields “wlan_radio.phy”
* **Channel** fields “wlan_radio.channel”
* **DataRate** fields “wlan_radio.data_rate”
* **SubType** fields “wlan.fc.type_subtype”
* **Type** fields “wlan.fc.type”
* **Retry** fields “wlan.fc.retry.expert”

For access to this configuration, you go to **Edit/Preferences/Appearance/Columns**

![_config.yml]({{ site.baseurl }}/images/2024/B2ColumnsPreference.png)

Other way to adds columns is right click on frame frame field (that you need adds) and select **Apply as Column**

![_config.yml]({{ site.baseurl }}/images/2024/B2applysascolumn.png)



## Coloring Rules
You can coloring frames to make more "readable" and make a difference with other frames. You can apply this feature for coloring "Management", "Control", and "Data" Frames, or apply these rules at Subtype Frames.
For example, if you need coloring "Frame Type" you need three rule, each of these rule have the frame type.

* **wlan.fc.type == 0**
* **wlan.fc.type == 1**
* **wlan.fc.type == 2**

![_config.yml]({{ site.baseurl }}/images/2024/B2coloringrules.png)

When you apply the rules, that view as follows

![_config.yml]({{ site.baseurl }}/images/2024/B2colorinframes.png)

