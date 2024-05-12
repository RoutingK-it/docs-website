---
title: BGP Communities
author: Dennis de Houx
published: true
layout: default
nav_order: 3
permalink: /wmp/bgp-communties
---
# BGP Communities
{: .fs-9 }
We use large BGP communities for both informational and alterable communities.
{: .fs-6 .fw-300 }

## Informational

These communities are available on both ix/peer and customer/downstream prefixes.

### Location, type, ... information

| Community              | Description                        |
| ---------------------- | ---------------------------------- |
| {{ MY_ASN }}:100:1    | Originated by {{ MY_NETWORK }}    |
| {{ MY_ASN }}:100:2    | Learned from customer/downstream   |
| {{ MY_ASN }}:100:3    | Learned from Direct Peer           |
| {{ MY_ASN }}:100:4    | Learned from IX route servers      |
| {{ MY_ASN }}:100:5    | Learned from transit/upstream      |
| {{ MY_ASN }}:101:{{ SESSION_ASN }} | Learned from {{ SESSION_NAME }} |
| {{ MY_ASN }}:102:{{ IX_ASN }} | Learned from Internet Exchange {{ IX_NAME }} |
| {{ MY_ASN }}:103:{{ ROUTER_COUNTRY_CODE }} | Learned in Country {{ ROUTER_COUNTRY_NAME }} |
| {{ MY_ASN }}:104:{{ ROUTER_LOCATION_ID }} | Learned in Location/Datacenter {{ ROUTER_LOCATION_NAME }} |
| {{ MY_ASN }}:105:{{ ROUTER_ID }} | Learned from {{ ROUTER_NAME }} |

### Validation information

| Community           | Description                                    |
| ------------------- | ---------------------------------------------- |
| {{ MY_ASN }}:510:1 | Validated IPv4 customer/downstream route       |
| {{ MY_ASN }}:510:2 | Validated IPv6 customer/downstream route       |
| {{ MY_ASN }}:520:1 | RPKI validated customer/downstream route with state valid |
| {{ MY_ASN }}:520:2 | RPKI validated customer/downstream route with state not found |
| {{ MY_ASN }}:520:3 | RPKI validated customer/downstream route with state invalid |
| {{ MY_ASN }}:530:1 | prefix too long (smaller < 7 for IPv4 or < 12 for IPv6) |
| {{ MY_ASN }}:530:2 | prefix too small (greater > 24 for IPv4 or > 48 for IPv6) |
| {{ MY_ASN }}:540:1 | Validated Bogon AS filtering                   |
| {{ MY_ASN }}:540:2 | Validated Bogon prefix filtering               |
| {{ MY_ASN }}:550:1 | Validated Long AS path filtering               |


## Alterable / Actions

When these communities are applied to prefixes received by {{ MY_NETWORK }} they alter their routing policy in our autonomous system. They are available only on customer/downstream BGP sessions.

### Blackhole

| Community              | Description                        |
| ---------------------- | ---------------------------------- |
| 65535:666              | Blackhole                          |
| {{ MY_ASN }}:0:666    | Blackhole                          |

Routes tagged with the blackhole community must be either an IPv4 /32 or an IPV6 /128 and have an encompassing IRR route or route6 object from an authenticated source like ARIN, APNIC, AFRINIC, or RIPE.

### Well-known Communities (RFC)

| Community              | Description                                |
| ---------------------- | ------------------------------------------ |
| 65535:0                | Gracefull shutdown, lowers local-pref to 0 |
| 65535:65281            | No Export (RFC1997)                        |
| 65535:65282            | No Advertisement (RFC1997)                 |
| 65535:65284            | No Export (RFC3765)                        |

### Prepends

| Community              | Description                              |
| ---------------------- | ---------------------------------------- |
| {{ MY_ASN }}:600:1    | Prepends the peer AS one time            |
| {{ MY_ASN }}:600:2    | Prepends the peer AS two time            |
| {{ MY_ASN }}:600:3    | Prepends the peer AS three time          |
| {{ MY_ASN }}:601:n    | Prepends the peer AS one time to AS[n]   |
| {{ MY_ASN }}:602:n    | Prepends the peer AS two time to AS[n]   |
| {{ MY_ASN }}:603:n    | Prepends the peer AS three time to AS[n] |

### Local preference

| Community              | Description                              |
| ---------------------- | ---------------------------------------- |
| {{ MY_ASN }}:610:x    | Set local preference to [x]              |

By default, {{ MY_NETWORK }} customers/downstreams are imported to BGP with LocalPref 5000. However, {{ MY_NETWORK }} provides a LocalPref manipulation community that will allow you to control the link over which traffic comes in for active-passive backup purposes. You can set the LocalPref to 4000 by tagging the route with {{ MY_ASN }}:610:4000, which is still higher than non-customer routes.

### Exports

| Community              | Description                                 |
| ---------------------- | ------------------------------------------- |
| {{ MY_ASN }}:660:1    | Do not export to any transit/upstream       |
| {{ MY_ASN }}:660:2    | Do not export to any bilateral peers        |
| {{ MY_ASN }}:660:3    | Do not export to any customer/downstream    |
| {{ MY_ASN }}:660:n    | Do not export to specific AS[n]             |
