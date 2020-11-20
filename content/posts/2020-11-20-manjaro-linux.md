---
title: Switching from Ubuntu to Manjaro Linux
date: 2020-11-20
published: true
tags: ['Manjaro', 'Linux']
series: false
cover_image: ./images/photo_2020-11-20_12-31-41.jpg
canonical_url: false
description: Manjaro has just became my main distro
---

I've been an Ubuntu user for long time. During this time of been tempted to change to other distributions but I ended up sticking with Ubuntu due to its simplicity, stability and community support.

But I was pissed by the last Canonical movements to force you to use their snap packages. Mainly because:

* They add unnecessary weight to the apps
* The apps can't access the host api directly
* They last forever to start

But Canonical is pushing it even if you install an app through the command line.

That made me try alternatives. First I tried Fedora. I was a Fedora user long time ago. I have to admit that it was very good, but I felt a little bit limited due to most of the software is Ubuntu/debian packaged.

I was about to try Debian when a trendy distribution hit my face. Manjaro.

## Manjaro linux

Manjaro is a rolling release distribution based on Arch. Si it has the freedom of Arch but the easy approach of a standard distribution. And I have to say that I'm very impressed. For now it has exceeded all my expectations.

I'm used to Gnome. I've tried kde so many times but I always come back to the simplicity of Gnome. And I have to say that the Manjaro Gnome flavor is awesome. The apps and extensions packed by default are perfect. I haven't needed to install a bunch of them by hand as I usually do on each fresh install.

And the official repos combined with the gigantic AUR repo, makes it so easy to find and install any package you can imagin.

I'm definitely sticking to Manjaro as my main distribution for a while.

## Manjaro on Macbook Air

My laptop is a 2017 MacBook Air. Manjaro installed without problems to it. But as usual, I had to install a couple of drivers.

### Wifi drivers

To make the wifi drivers work I just had to update the system and install `broadcom-wl` selecting the one corresponding to my kernel version.

And that was really all.

### Webcam

To make the webcam work I usually have to compile the drivers from source, but this time I could do it automatically from the install process. I just needed to install `bcwc-pcie-git`.

### Import GPG keys

Sometimes when building a package you can recieve a GPG import key error. You need to manually import it with:
`gpg --keyserver pool.sks-keyservers.net --recv-key <YOUR KEY>`
