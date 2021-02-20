---
title: Fixing 2 minutes shutdown issue
slug: fixing-2-minutes-shutdown-issue
date: 2020-31-12
tags: [Manjaro,Linux]
cover_image: ./images/photo_2020-11-20_12-31-41.jpg
published: true
---

I've recently updated my Manjaro system and I've noticed an unusually slow shutdown process, around 2 minutes.

I've found out that it is an issue of systemd update. To workaround it just add this:

`Slice=-.slice`

To the end of this file:

`sudo nano /usr/lib/systemd/user/gnome-session-restart-dbus.service`

Credit: <https://forum.manjaro.org/t/pretty-slow-shutdown/41785/2>
