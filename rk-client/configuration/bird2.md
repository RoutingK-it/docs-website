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

# Bird2 Configuration

**This is fully optional and you should only use this if your bird2 installation is custom or you have changed the default locations.**

## Bird2

### Directory

The location of your bird2 configuration files.

> **Default value**
>
> `directory: /etc/bird/`

### Binary

The location of your bird2 binary file.

{: .note-title }

> Default value
>
> `binary: /usr/sbin/bird`

### Socket

The location of your bird2 socket file.

{: .important-title }

> Default value
>
> `socket: /run/bird/bird.ctl`

### Yaml example

```yaml
bird2:
  - directory: /etc/bird/
  - binary: /usr/sbin/bird
  - socket: /run/bird/bird.ctl
```
