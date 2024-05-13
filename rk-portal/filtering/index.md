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
- RPKI (optional, but adviced)
- Bogon ASN (forced)
- Bogon prefix (forced)
- IXP peering LANs (forced)
- Long ASN path (forced)
- Prefix length (forced)
- Known Tier1/Transit Networks (optional)
- BGP Communities (optional)
