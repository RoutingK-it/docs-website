---
title: Daemon
author: Dennis de Houx
published: true
has_toc: true
layout: default
nav_order: 1
permalink: /client/configuration/daemon
grand_parent: Linux Client/Daemon
parent: Configuration
has_children: false
---

# Daemon Configuration

**The configuration file is a yaml (yml) based file, here is a example file to start with**

## Daemon

### Enabled

Enable or disable the daemon from running in the background. If the setting is disabled (enabled: false) then the client will only run once.
{: .note-title }

> Default value
> `enabled: true`

### Update time

How fast the client will check for updates on the Web Management Portal via api calls. The lowest available setting is one (1) hour and the maximum is 720 hours (1 month).
{: .note-title }

> Default value
> `update-time: 4`

### Log file

Location where the log files will be saved, the default is the syslog location.
{: .note-title }

> Default value
> `log-file: syslog`

### Yaml example

```yaml
daemon:
  - enabled: true # Enable the daemon
  - update-time: 1 # Check updates every X hour(s)
  - log-file: syslog
```
