---
title: BGP Filtering
author: Dennis de Houx
published: true
has_toc: true
layout: default
nav_order: 3
permalink: /web-management-portal/bgp-filtering
has_children: true
parent: Web Management Portal
---

# BGP Filtering

**Here you can learn more about the global filtering we use, some filtering is required, others are optional.**

## Order of operation

- Global ASN blocklist (optional)
- Global prefix blocklist (optional)
- Blackhole Community (forced eBGP)
- Bogon ASN (forced eBGP)
- Bogon prefix (forced eBGP)
- RPKI (optional, but advised)
- IXP peering LANs (forced eBGP)
- Long AS path (forced eBGP)
- Prefix length (forced eBGP)
- Known Tier1/Transit Networks (optional, but advised)
- BGP Communities (optional)
- Custom filters per session (optional)
