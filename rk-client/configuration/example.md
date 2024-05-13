---
title: Example
author: Dennis de Houx
published: true
has_toc: true
layout: default
nav_order: 99
permalink: /client/configuration/example
grand_parent: Linux Client/Daemon
parent: Configuration
has_children: false
---

# Configuration Example

**The configuration file is a yaml (yml) based file, here is a example file to start with**

## Example file

```yaml
# Example Configuration file for rk-client
---
daemon:
  - enabled: true # Enable the daemon
  - update-time: 1 # Check updates every X hour(s)
  - log-file: syslog

portal:
  - url: "https://example.com/"
  - api-key: "vxufsdnvdfç!gdjfkhgjkhfdg"

monitoring:
  - enabled: true # Enable pushing monitoring information to the portal
  - update-time: 5 # Push information every X minutes (5 is lowest)

bird2:
  - directory: /etc/bird/
  - binary: /usr/sbin/bird
  - socket: /run/bird/bird.ctl
```
