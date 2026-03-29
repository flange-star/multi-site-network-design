# VLAN & Subnet Breakdown

ShopSmart Online uses a structured IP addressing scheme across all four sites. Each site is assigned a dedicated /22 block with segmented VLANs for traffic isolation and security.

---

## Fort Myers, FL — Head Office (HQ)

**Network Block:** 192.168.0.0/22 (255.255.252.0)

*HQ has pre-configured services including network hardware, servers, clients, and other infrastructure that require segmented VLANs.*

| VLAN | Subnet | Default Gateway |
|------|--------|-----------------|
| VLAN 10 | 192.168.0.0/25 | 192.168.0.1 |
| VLAN 20 | 192.168.0.128/25 | 192.168.0.129 |
| VLAN 30 | 192.168.1.0/25 | 192.168.1.1 |
| VLAN 40 | 192.168.1.128/25 | 192.168.1.129 |
| VLAN 50 | 192.168.2.0/27 | 192.168.2.1 |
| VLAN 60 | 192.168.2.128/25 | 192.168.2.129 |
| VLAN 70 | 192.168.2.32/27 | 192.168.2.33 |

---

## Dallas, TX — Warm Site

**Network Block:** 192.168.10.0/22 (255.255.252.0)

*This warm site mirrors HQ with the same services, network hardware, and servers, all with segmented VLANs.*

| VLAN | Subnet | Default Gateway |
|------|--------|-----------------|
| VLAN 10 | 192.168.10.0/25 | 192.168.10.1 |
| VLAN 20 | 192.168.10.128/25 | 192.168.10.129 |
| VLAN 30 | 192.168.11.0/25 | 192.168.11.1 |
| VLAN 40 | 192.168.11.128/25 | 192.168.11.129 |
| VLAN 50 | 192.168.12.0/27 | 192.168.12.1 |
| VLAN 60 | 192.168.12.128/25 | 192.168.12.129 |
| VLAN 70 | 192.168.12.32/27 | 192.168.12.33 |

---

## Seattle, WA — Branch Office

**Network Block:** 192.168.20.0/22 (255.255.252.0)

*Branch site connected primarily to HQ and Dallas for redundancy. Uses smaller subnet sizes to match reduced headcount.*

| VLAN | Subnet | Default Gateway |
|------|--------|-----------------|
| VLAN 10 | 192.168.20.0/25 | 192.168.20.1 |
| VLAN 20 | 192.168.20.128/25 | 192.168.20.129 |
| VLAN 30 | 192.168.21.0/25 | 192.168.21.1 |
| VLAN 40 | 192.168.21.128/27 | 192.168.21.129 |
| VLAN 50 | 192.168.21.160/27 | 192.168.21.161 |

---

## Philadelphia, PA — Branch Office

**Network Block:** 192.168.30.0/22 (255.255.252.0)

*Branch site connected primarily to HQ and Dallas for redundancy. Uses smaller subnet sizes to match reduced headcount.*

| VLAN | Subnet | Default Gateway |
|------|--------|-----------------|
| VLAN 10 | 192.168.30.0/25 | 192.168.30.1 |
| VLAN 20 | 192.168.30.128/25 | 192.168.30.129 |
| VLAN 30 | 192.168.31.0/25 | 192.168.31.1 |
| VLAN 40 | 192.168.31.128/27 | 192.168.31.129 |
| VLAN 50 | 192.168.31.160/27 | 192.168.31.161 |
