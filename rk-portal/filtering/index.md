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
- Bogon ASN (forced)
- Bogon prefix (forced)
- RPKI (optional, but adviced)
- IXP peering LANs (forced)
- Long AS path (forced)
- Prefix length (forced)
- Known Tier1/Transit Networks (optional, but adviced)
- BGP Communities (optional)
- Custom filters per session (optional)
