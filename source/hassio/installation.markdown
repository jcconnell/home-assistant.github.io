---
layout: page
title: "Installing Hass.io"
description: "Instructions on how to install Hass.io."
date: 2017-04-30 13:28
sidebar: true
comments: false
sharing: true
footer: true
---

Hass.io images are available for:

- Download the appropriate image for your IoT:
  - [Raspberry Pi / Zero][pi1]
  - [Raspberry Pi / Zero W][pi0-w]
  - [Raspberry Pi 2][pi2]
  - [Raspberry Pi 3 32bit][pi3-32]
  - [Raspberry Pi 3 64bit][pi3-64]
- As [Virtual Appliance]:
  - [VMDK][vmdk]

<p class='note'>
Please remember to ensure you're using an [appropriate power supply](https://www.raspberrypi.org/help/faqs/#powerReqs) with your Pi. Mobile chargers may not be suitable since some were only designed to provide just enough power to the device it was designed for by the manufacturer.
</p>

- Flash the downloaded image to an SD card using [Etcher].

- Optional - Setup the WiFi or static IP: On the SD-card, create the `network/my-network` file and follow the [HassOS howto][hassos-network].
- Insert SD card to Raspberry Pi and turn it on. On first boot, it downloads the latest version of Home Assistant which takes ~20 minutes (slower/faster depending on the platform).

<img src='/images/hassio/screenshots/first-start.png' style='clear: right; border:none; box-shadow: none; float: right; margin-bottom: 12px;' width='150' />

- You will be able to reach your installation at [http://hassio.local:8123][local].
- Enable either the [Samba add-on][samba] or the [SSH add-on][ssh] to manage your configuration in `/config/` (From the UI choose **Hass.io** which is located in the sidebar).

<p class='note'>
If your router doesn't support mDNS, then you'll have to use the IP address of your Pi instead of `hassio.local`. For example, `http://192.168.0.9:8123`. You should be able to find the IP address of your Pi from the admin interface of your router.
</p>

<p class='note'>
If you copy over your existing Home Assistant configuration, make sure to enable the Hass.io panel by adding either `discovery:` or `hassio:` to your configuration.
</p>

## {% linkable_title Alternative: install on generic Linux server %}

For advanced users, it is also possible to try Hass.io on your [Linux server or inside a virtual machine][linux].

This is the list of packages you need to have available on your system that will run Hass.io if you are using Debian/Ubuntu:

 - apparmor-utils
 - apt-transport-https
 - avahi-daemon
 - ca-certificates
 - curl
 - dbus
 - jq
 - network-manager
 - socat
 - software-properties-common

To perform the Hass.io installation, run the following command as root:

```bash
$ curl -sL https://raw.githubusercontent.com/home-assistant/hassio-build/master/install/hassio_install | bash -s
```

<p class='note'>
When you use this installation method, the core SSH add-on may not function correctly. If that happens, use the community SSH add-on. Some of the documentation might not work for your installation either.
</p>

A detailed guide about running Hass.io as a virtual machine is available in the [blog](/blog/2017/11/29/hassio-virtual-machine/).

[Etcher]: https://etcher.io/
[Virtual Appliance]: https://github.com/home-assistant/hassos/blob/dev/Documentation/boards/ova.md
[hassos-network]: https://github.com/home-assistant/hassos/blob/dev/Documentation/network.md
[pi0-w]: https://github.com/home-assistant/hassos/releases/download/1.7/hassos_rpi0-w-1.7.img.gz
[pi1]: https://github.com/home-assistant/hassos/releases/download/1.7/hassos_rpi-1.7.img.gz
[pi2]: https://github.com/home-assistant/hassos/releases/download/1.7/hassos_rpi2-1.7.img.gz
[pi3-32]: https://github.com/home-assistant/hassos/releases/download/1.7/hassos_rpi3-1.7.img.gz
[pi3-64]: https://github.com/home-assistant/hassos/releases/download/1.7/hassos_rpi3-64-1.7.img.gz
[vmdk]: https://github.com/home-assistant/hassos/releases/download/1.7/hassos_ova-1.7.vmdk
[linux]: https://github.com/home-assistant/hassio-build/tree/master/install#install-hassio
[local]: http://hassio.local:8123
[samba]: /addons/samba/
[ssh]: /addons/ssh/
