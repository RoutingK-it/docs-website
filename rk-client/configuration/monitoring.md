---
title: Monitoring
author: Dennis de Houx
published: true
has_toc: true
layout: default
nav_order: 3
permalink: /client/configuration/monitoring
grand_parent: Linux Client/Daemon
parent: Configuration
has_children: false
---

# Linux Client/Daemon - Monitoring Configuration

**The configuration file is a yaml (yml) based file, here is a example file to start with**

## Monitoring

### Yaml example

```yaml
monitoring:
  - enabled: true # Enable pushing monitoring information to the portal
  - update-time: 5 # Push information every X minutes (5 is lowest)
```
