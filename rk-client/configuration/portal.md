---
title: Portal
author: Dennis de Houx
published: true
has_toc: true
layout: default
nav_order: 2
permalink: /client/configuration/portal
grand_parent: Linux Client/Daemon
parent: Configuration
has_children: false
---

# Portal Configuration

**The configuration file is a yaml (yml) based file, here is a example file to start with**

## Portal

### Url

The url of the Web Management Portal, if you use a self-hosted portal we recommend that you use ssl and/or only allow your own ip addresses connecting to the portal.

{: .new-title }

> Default value
>
> `url: https://127.0.0.1`

### Api Key

The api key used to connect to the portal, keep this safe and don't publish this key. We recommend creating a special api key only used by this client.

{: .new-title }

> Default value
>
> `api-key: "iNeedToChangeThisAPIkey"`

### Yaml example

```yaml
portal:
  - url: "https://example.com/"
  - api-key: "vxufsdnvdfç!gdjfkhgjkhfdg"
```
