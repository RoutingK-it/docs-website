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

# Monitoring Configuration

**Adjust the monitoring configuration if you want to use this, by default this is disabled to save bandwidth and cpu proccessing**

## Monitoring

### Enabled

Enable or disable the monitoring fuction from collecting data. If the setting is disabled (enabled: false) then the client will not push any session or bird2 information to the Web Management Portal.

{: .new-title }

> Default value
>
> `enabled: false`

### Update time

How fast the client will push collected data to the Web Management Portal via api calls. The lowest available setting is five (5) minutes and the maximum is 1440 minutes (1 day).

{: .new-title }

> Default value
>
> `update-time: 5`

{: .highlight-title }

> Hosted information
>
> Keep in mind that the lowest setting is depending on the type of account you have, it could be as low as 5 minutes for enterprise customers or 60 minutes for home/hobby users.
>
> If you put this more frequent then your account allows you will be rate-limited and this can cause problems for the update checker.
>
> Self-hosted users can set this to 1 minute but this is not recommended, default option is 5 minutes. Setting this lower can cause large database tables and/or trigger the rate-limit on the api.

### Yaml example

```yaml
monitoring:
  - enabled: true # Enable pushing monitoring information to the portal
  - update-time: 5 # Push information every X minutes (5 is lowest)
```
