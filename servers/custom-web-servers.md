---
title:  "Using custom Rack servers"
---

## Overview

By default, applications deployed by Cloud 66 run on [Phusion Passenger](https://www.phusionpassenger.com/) behind [Nginx](https://wiki.nginx.org/Main). You can also choose to use one of several servers:

- [Passenger Enterprise](/docs/build-and-config/passenger-enterprise)
- [Puma](/docs/build-and-config/puma-rack-server)
- [Unicorn](/docs/build-and-config/unicorn-rack-server)
- [Thin](/docs/build-and-config/thin-rack-server)

It's vital to distinguish between these Rack-based **application**  (or "web app") servers and Nginx which acts as the **public web front-end** for Cloud 66 applications. We usually refer to Nginx as our "web server", but it performs a different task to the Rack-based app servers described in this doc.

{% callout type="info" title="Migrating between application servers" %}
You can change freely between supported servers by simply updating your Gems and Procfile.
{% /callout %}

## Configuring a custom Rack server

If you would like to use a different server, there are some points you'd need to consider for it to work with a Cloud 66 application. These conventions will allow Cloud 66 to redirect traffic to your servers and manage them for availability, memory consumption and restart cycles.

### Traffic Socket
For the traffic to be redirected to your web app server, it should use a Unix socket at `/tmp/web_server.sock`

### PID file
For the web app server to be managed and restarted properly by Cloud 66, it needs to have it's PID file at `/tmp/web_server.pid`

## What’s next?

* Learn how to [add a load balancer](/docs/load-balancers/load-balancer) to your application
* Learn how to [set up your DNS records](/docs/networking/configure-dns) to work with Cloud 66
* Learn how to [configure network access](/docs/networking/network-configuration) to your application
* Learn how to [manage processes on your web server](/docs/servers/systemd) directly via your terminal
