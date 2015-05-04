---
layout: post
status: publish
published: true
permalink: /2011/02/remote-control-samsung-tv-with-android-phone/
title: SamyGo Remote - Control your Samsung TV with Android
author:
  display_name: Tom
  login: tom
  email: tom@quist.de
  url: ''
author_login: tom
author_email: tom@quist.de
wordpress_id: 125
wordpress_url: http://quist.de/?p=125
date: '2011-02-20 18:52:43 +0100'
date_gmt: '2011-02-20 17:52:43 +0100'
categories:
- Android
- SamyGo-Remote
tags:
- remote lan control
- samsung
- samygo
- tv
- remote
- b-series
- install
- how-to
- instruction
screenshots:
- screenshot3.png
- screenshot5.png
- screenshot4.png
---
![qrcode](http://qrcode.kaywa.com/img.php?s=3&d=https%3a%2f%2fplay.google.com%2fstore%2fapps%2fdetails%3fid%3dde.quist.app.samyGoRemote)

Thanks to the [SamyGo Project](http://samygo.tv/) my TV [Samsung LE37B650](http://www.samsung.com/de/support/model/LE37B650T2PXZG) became a high-tech device. Because it has an ethernet port and runs Linux, it enables you to do many cool [things](http://wiki.samygo.tv/index.php5/Content_Library_applications_list) with it. For example one can run a server application which receives remote signals through your LAN. Therefore you have to install "[Remote Lan Control](http://wiki.samygo.tv/index.php5/Content_Library_applications_list#Remote_LAN_Control)" which can be done using the content library (only necessary on B-Series). For a how-to see below!

Because there only was a [Windows-client](http://wiki.samygo.tv/index.php5/Content_Library_applications_list#Remote_LAN_Control) for B-Series TVs and the android client from Samsung only runs on Samsung devices, I wrote an Android-Client to be able to control the TV using my android phone. The result can be [downloaded from the Android Play Store](https://play.google.com/store/apps/details?id=de.quist.app.samyGoRemote).

{% for screen in page.screenshots %}<img src="{{ screen | prepend: '/assets/' | prepend: site.baseurl | replace: '//', '/' }}" alt="MyMensa" style="display: inline-block; margin: 5px; border: 1px solid black;"/>{% endfor %}

<del>The app only works for B-Series TVs from Samsung, because "Remote Lan Control" only runs on these devices.</del> C-Series, D-Series and E-Series TVs are now also supported without needing to modify the TV. Samsung created a remote-app for C-Series TVs but it only runs on the iPhone or on Android devices produces by Samsung. C-Series devices are able to receive remote signals over the network from scratch (using UPnP) <del>but I've no idea how to access the interface and I'm not able to analyse it, because I don't have such a device.</del>

### How-To for B-Series:

Because sometimes it is hard to find the desired information on the [SamyGo Project pages](http://samygo.tv/), I describe how to run "Remote Lan Control" on your TV. Even if the described approach is not very dangerous because the TV resets to its initial state after a restart, I am not responsible for any damages on your TV. Do it on your own risk!

1.  Download "Remote Lan Control": [here](http://download.samygo.tv/B%20Series/Content%20Library%20Applications/Remote%20LAN%20Control%20%28v0.1%29.zip)
2.  Extract the zip-file and copy the content to a USB-stick (USB-stick should be formatted in FAT32)
3.  Plug the USB-stick into your TV
    *   If your TV is already turned on, a window should pop up after a little while. Select "Content Library"
    *   If your TV was off or no window popped up, press the button "CONTENT" on your remote and select the most right symbol
4.  Now select "USB" and highlight the "Games" entry: Press the ENTER-Button
    *   Some people reported that there was no Games section. In this case you could try to create one. This requires telnet enabled and is explained [here](http://wiki.samygo.tv/index.php5/Enable_GAME_menu_option_at_Plasma_series)
5.  Now you should see a list of applications which are installed on your USB-stick. Highlight "SamyGO Remote" and press the ENTER-Button. Now a menu appears where you can run the application. You can also copy the application to the TVs internal storage so that you don't have to plug in your USB-stick every time you want to run the application.
    *   If you see a message "Not available" you have to downgrade your firmware. The latest firmware update from samsung removed the possibility to load extensions like this. How to downgrade the firmware is explained [here](http://forum.samygo.tv/viewtopic.php?f=5&t=2038)
6.  If you run the application there is NO feedback. Anyway - the server should be running now
7.  Don't forget to change the IP address in the android app to point to your TV. You can try to let SamyGo Remote automatically search for your TV. If it doesn't find it, you are either not connected to wifi, your wifi is not configured properly or your TV is not supported

**Minor flaw:** The server on your TV has to be restarted every time you turn on/off your TV. There is no simple solution yet. The only way to automatically start the server is to modify your firmware and create a start-script which runs the server using gdb (gdbtrick.sh) or injectso. But this should only be done by advanced users. Maybe I will explain it in another post. For the meantime you can look [here](http://wiki.samygo.tv/index.php5/SamyGO_for_DUMMIES#Using_a_SamyGO_app) for more information.

### How-To for C/D/E-Series:

1.  Turn on your TV
2.  To enable your TV to receive remote control signals over the network, go to the System-Settings in the TVs menu. If there is no such menu entry, your TV is not supported.
3.  Connect your phone via wifi with the same network your TV is connected with
4.  Start SamyGo Remote
5.  Go to Menu -> Settings -> Hostname -> Find automatically (Attention: this only works if your TV is within the same broadcast domain as your phone. Some routers don't forward broadcast packages by default, e.g. the Fritz!Box. Make sure to enable communication between wifi devices.)
6.  If your device could be found, your phone should vibrate. In this case, the TV-type is changed accordingly. If you own a C-Series, D-Series or E-Series TV but the type changed to B-Series, your TV is not supported.
7.  If no device could be found, try to determine the ip-address of your TV manually (e.g. look into the webinterface of your router) and type it into the hostname input field.
8.  Now the remote control should work
