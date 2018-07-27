---
layout: page
title: "Hass.io"
description: "Manage your Home Assistant and custom add-ons."
date: 2017-04-30 13:28
sidebar: true
comments: false
sharing: true
footer: true
redirect_from: /components/hassio/
---

Hass.io turns your Raspberry Pi (or another device) into the ultimate home automation hub powered by Home Assistant. With Hass.io you can focus on integrating your devices and writing automations.

[Go to the installation instructions &raquo;][install]

The advantages of using Hass.io:

- Free and open source
- Optimized for embedded devices like Raspberry Pi
- 100% local home automation
- Easy installation and updates (powered by [HassOS] and [Docker])
- Management web interface integrated into Home Assistant
- Create and restore full backups of your whole configuration with ease
- Install many popular add-ons with a single click! For example [Google Assistant], encryption via [Let's Encrypt] and dynamic DNS via [Duck DNS].<br><br>[Browse available add-ons &raquo;][all]<br><br>
- Active community that is helpful and sharing add-ons including AppDaemon, Homebridge and InfluxDB.<br><br>[Browse the forums &raquo;][forums]<br>[Join the Hass.io chat &raquo;][chat]<br>[Browse community add-on repositories &raquo;][comm-add-ons]<br><br>

<div class='videoWrapper'>
<iframe width="560" height="315" src="https://www.youtube.com/embed/XWPluWcYRMI" frameborder="0" allowfullscreen></iframe>
</div>

### {% linkable_title Upgrading %}

Hass.io users can update Home Assistant via the 'Hass.io' page in the UI. However, please note that a Home Assistant updates take time to roll into the Hass.io builds. Therefore there is often a slight delay between the availability of a Home Assistant update and the update being available in Hass.io, so be patient. When a Hass.io update is available, it will be shown as a notification in the ‘Hass.io' page in the web interface.

<p class='img'>
<img src='/images/hassio/screenshots/dashboard.png'>
Hass.io dashboard with upgrade notification (under the hamburger menu -> Hass.io)
</p>

<p class='img'>
<img src='/images/hassio/screenshots/ssh-upgrade.png'>
Hass.io upgrade process from the SSH command line
</p>

[Google Assistant]: /addons/google_assistant/
[Snips.ai]: /addons/snips/
[Let's Encrypt]: /addons/lets_encrypt/
[Duck DNS]: /addons/duckdns/
[forums]: https://community.home-assistant.io/c/hass-io
[comm-add-ons]: https://community.home-assistant.io/tags/hassio-repository
[all]: /addons/
[chat]: https://discord.gg/K3UVxJd
[HassOS]: https://github.com/home-assistant/hassos
[Docker]: https://www.docker.com/
[install]: /hassio/installation/

## {% linkable_title hassio command %}

On the SSH command line, you can use the `hassio` command to retrieve logs, check the details of connected hardware, and more.

Home Assistant:

```bash
$ hassio homeassistant logs
$ hassio homeassistant restart
$ hassio homeassistant stop
$ hassio homeassistant start
$ hassio homeassistant update
$ hassio homeassistant check
```

Host:

```bash
$ hassio host hardware
$ hassio host reboot
$ hassio host shutdown
$ hassio host update
```

Supervisor

```bash
$ hassio supervisor logs
$ hassio supervisor info
$ hassio supervisor reload
$ hassio supervisor update
```

You can get a better description of the CLI capabilities by typing `hassio help`:

```bash
NAME:
   hassio - Commandline tool to allow interaction with hass.io

USAGE:
   hassio [global options] command [command options] [arguments...]

VERSION:
   1.2.1

AUTHOR:
   Home-Assistant <hello@home-assistant.io>

COMMANDS:
     homeassistant, ha  info, logs, check, restart, start, stop, update
     supervisor, su     info, logs, reload, update
     host, ho           hardware, reboot, shutdown, update
     network, ne        info, options
     snapshots, sn      list, info, reload, new, restore, remove
     addons, ad         list, info, logo, changelog, logs, stats,
 reload, start, stop, install, uninstall, update
     help, h  Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --debug, -d    Prints Debug information
   --help, -h     show help
   --version, -v  print the version
```
