# ShopSmart Online — Multi-Site Enterprise Network Design

Architected a scalable WAN infrastructure for ShopSmart Online's e-commerce expansion, connecting a headquarters and three regional offices across the U.S. with redundant site-to-site VPN connectivity, dual ISP failover, and centralized security monitoring.

---

## Network Diagrams

### Geographic Topology
![Geographic Network Map](diagrams/geographic-map.jpg)

### Logical Network Architecture
![Logical Network Diagram](diagrams/logical-network-diagram.png)

---

## What Was Built

- Full-mesh site-to-site IPSec VPN connecting Fort Myers (HQ), Dallas, Seattle, and Philadelphia
- Dual ISP failover at every site with LTE backup for remote users
- VLAN segmentation across all locations for traffic isolation and security
- Microsoft Sentinel SIEM deployed at each site for centralized threat monitoring
- Cisco Meraki cloud-managed hardware across all four sites
- Centralized DHCP and DNS served from HQ with Dallas warm site as secondary
- Delivered full documentation suite including firewall rules, DHCP scopes, device lists, and VLAN breakdown

---

## Site Overview

| Site | Role | Network Block | VLANs |
|------|------|---------------|-------|
| Fort Myers, FL | Headquarters | 192.168.0.0/22 | 7 |
| Dallas, TX | Warm Site | 192.168.10.0/22 | 7 |
| Seattle, WA | Branch Office | 192.168.20.0/22 | 5 |
| Philadelphia, PA | Branch Office | 192.168.30.0/22 | 5 |

---

## Documentation

| Document | Description |
|----------|-------------|
| [Firewall Rules](docs/firewall-rules.md) | Inbound/outbound firewall rules per site and VLAN |
| [VLAN Breakdown](docs/vlan-breakdown.md) | VLAN IDs, subnets, and default gateways per site |
| [DHCP Scopes](docs/dhcp-scopes.md) | DHCP scope ranges and reservations per site |
| [Device List](docs/device-list.md) | Hardware and server inventory per site |

---

## Technologies Used

- **Routing & Security:** Cisco Meraki MX (Router / Firewall / VPN Gateway / IDPS)
- **Switching:** Cisco Meraki MS
- **Wireless:** Cisco Meraki MR Access Points
- **VPN:** Full-mesh IPSec site-to-site with dual ISP failover
- **Identity & Access:** Microsoft Active Directory, RADIUS Authentication
- **Security Monitoring:** Microsoft Sentinel SIEM
- **Services:** DNS, DHCP, VoIP (SIP/RTP), File Server, Database Server

---

*Senior Capstone — Information Systems Technology | 2025*
