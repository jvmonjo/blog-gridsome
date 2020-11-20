---
title: "Setting up an Ubuntu server [part 1]: Docker"
slug: setting-up-an-ubuntu-server-part-1-docker
date: 2020-10-28
published: true
tags: devops
---

Ok. You've just got a home server or you've hired a vps Ubuntu server. I'm not a devops guy so I need a step by step guide. What do you need to do?

I like to follow the steps in [Digital Ocean website](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04), so I'll just make it a summary here based on that.

First we need to ssh as root:

‌`$ ssh root@your_server_ip`

Then we add a new user

‌ `# adduser josep`

And give it administrative privileges

‌ `# usermod -aG sudo josep`

If we want to access via ssh keys we can copy the root user keys to our account.

‌`# rsync --archive --chown=josep:josep ~/.ssh /home/josep`

### Setting up docker

One of the easiest ways to get up and running with our web apps is to use [Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-es).

Let's first refresh our repos.

‌`$ sudo apt update`

Then we need some https stuff

‌`$ sudo apt install apt-transport-https ca-certificates curl software-properties-common`

Add the Docker GPG repo key.

‌`$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

Add the Docker repo. Here is the command for Ubuntu 20.04.

‌`$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"`

Update the packages list.

‌`$ sudo apt update`

We force the system to install Docker from our new source and not from the internal Ubuntu repo.

`$ apt-cache policy docker-ce`

And finally install Docker.

‌`$ sudo apt install docker-ce`

We will need docker compose too, so we're going to install it now.

```bash
sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
```

In the next article we'll see how to [setup Portainer and Nginx](/2020/10/setting-up-an-ubuntu-server-part-2-portainer-and-nginx) proxy manager to install and manage our apps and sites.
