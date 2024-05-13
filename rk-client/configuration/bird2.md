---
title: Bird2
author: Dennis de Houx
published: true
has_toc: true
layout: default
nav_order: 4
permalink: /client/configuration/bird2
grand_parent: Linux Client/Daemon
parent: Configuration
has_children: false
---

# Linux Client/Daemon - Bird2 Configuration

**The configuration file is a yaml (yml) based file, here is a example file to start with**

## Bird2

### Yaml example

```yaml
bird2:
  - directory: /etc/bird/
  - binary: /usr/sbin/bird
  - socket: /run/bird/bird.ctl
```
