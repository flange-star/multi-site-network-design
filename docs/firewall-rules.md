# Firewall Rules

ShopSmart Online implements strict firewall rules to provide security while allowing only necessary traffic between branch and HQ resources. All sites follow a default-deny policy — any traffic not explicitly permitted is blocked.

---

## Fort Myers (HQ)

| Rule | Source Address | Source Port | Destination Address | Destination Port | Action | Direction |
|------|----------------|-------------|---------------------|------------------|--------|-----------|
| 1 | 192.168.0.0/25 (HQ VLAN 10) | Any | 192.168.0.131 (HQ DB Server) | 1433 (TCP) | Allow | Outbound |
| 2 | 192.168.0.0/25 (HQ VLAN 10) | Any | 192.168.0.132 (HQ RADIUS Server) | 1812/1813 (UDP) | Allow | Outbound |
| 3 | 192.168.0.0/25 (HQ VLAN 10) | Any | 192.168.0.133 (HQ File Server) | 445 (TCP) | Allow | Outbound |
| 4 | 192.168.0.0/25 (HQ VLAN 10) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 389/636 (TCP), 53 (UDP), 67 (UDP) | Allow | Outbound |
| 5 | 192.168.0.128/25 (HQ VLAN 20) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 6 | 192.168.1.0/25 (HQ VLAN 30) | Any | 192.168.0.130 (HQ VoIP PBX Server) | 5060/5061 (TCP or UDP) | Allow | Outbound |
| 7 | 192.168.1.0/25 (HQ VLAN 30) | Any | 192.168.0.130 (HQ VoIP PBX Server) | 10000-20000 (UDP) | Allow | Outbound |
| 8 | 192.168.1.0/25 (HQ VLAN 30) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 9 | 192.168.1.0/25 (HQ VLAN 30) | Any | Any | Any | Deny | Outbound |
| 10 | 192.168.1.128/25 (HQ VLAN 40) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 11 | 192.168.0.0/25 (HQ VLAN 10) | Any | Any | 80 (TCP), 443 (TCP) | Allow | Outbound |
| 11 | 192.168.1.128/25 (HQ VLAN 40) | Any | Any | 80 (TCP), 443 (TCP) | Allow | Outbound |
| 13 | 192.168.2.0/27 (HQ VLAN 50) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 14 | 192.168.2.0/27 (HQ VLAN 50) | Any | Any | Any | Deny | Outbound |
| 15 | 192.168.2.128/25 (HQ VLAN 60) | Any | 192.168.0.131 (HQ DB Server) | 1433 (TCP) | Allow | Outbound |
| 16 | 192.168.2.128/25 (HQ VLAN 60) | Any | 192.168.0.132 (HQ RADIUS Server) | 1812/1813 (UDP) | Allow | Outbound |
| 17 | 192.168.2.128/25 (HQ VLAN 60) | Any | 192.168.0.133 (HQ File Server) | 445 (TCP) | Allow | Outbound |
| 18 | 192.168.2.128/25 (HQ VLAN 60) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 389/636 (TCP), 53 (UDP), 67 (UDP) | Allow | Outbound |
| 19 | 192.168.2.32/27 (HQ VLAN 70) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 20 | 192.168.2.32/27 (HQ VLAN 70) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud VPN Registry) | 9350-9381 (UDP) | Allow | Outbound |
| 21 | 192.168.2.32/27 (HQ VLAN 70) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Communication) | 80 (TCP), 443 (TCP), 7351 (UDP), 7734 (TCP), 7752 (TCP) | Allow | Outbound |
| 22 | 192.168.2.32/27 (HQ VLAN 70) | Any | Any | Any | Deny | Outbound |
| 23 | 192.0.2.20 (HQ Router/Firewall WAN IP) | Any | Any | 123 (UDP) | Allow | Outbound |
| 24 | 192.0.2.20 (HQ Router/Firewall WAN IP) | Any | *.ods.opinsights.azure.com (Microsoft Azure Log Analytics for SIEM) | 443 (TCP) | Allow | Outbound |
| 25 | 192.0.2.20 (HQ Router/Firewall WAN IP) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud VPN Registry) | 9350-9381 (UDP) | Allow | Outbound |
| 26 | 192.0.2.20 (HQ Router/Firewall WAN IP) | Any | 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Communication) | 80 (TCP), 443 (TCP), 7351 (UDP), 7734 (TCP), 7752 (TCP) | Allow | Outbound |
| 27 | 192.0.2.20 (HQ Router/Firewall WAN IP) | Any | cloud-meraki-asn.amp/cisco.com, cloud-meraki-est.amp.cisco.com (Cisco Meraki Malware Protection) | 443 (TCP) | Allow | Outbound |
| 28 | 192.0.2.20 (HQ Router/Firewall WAN IP) | Any | api.meraki.com (Cisco Meraki API Requests) | 443 (TCP) | Allow | Outbound |
| 29 | 192.0.2.20 (HQ Router/Firewall WAN IP) | Any | 8.8.8.8/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Monitor) | ICMP | Allow | Outbound |
| 30 | Any | Any | Any | Any | Deny | All |

---

## Dallas Office (Warm Site)

| Rule | Source Address | Source Port | Destination Address | Destination Port | Action | Direction |
|------|----------------|-------------|---------------------|------------------|--------|-----------|
| 1 | 192.168.10.0/25 (Dallas VLAN 10) | Any | 192.168.0.131 (HQ DB Server) | 1433 (TCP) | Allow | Outbound |
| 2 | 192.168.10.0/25 (Dallas VLAN 10) | Any | 192.168.0.132 (HQ RADIUS Server) | 1812/1813 (UDP) | Allow | Outbound |
| 3 | 192.168.10.0/25 (Dallas VLAN 10) | Any | 192.168.0.133 (HQ File Server) | 445 (TCP) | Allow | Outbound |
| 4 | 192.168.10.0/25 (Dallas VLAN 10) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 389/636 (TCP), 53 (UDP), 67 (UDP) | Allow | Outbound |
| 5 | 192.168.10.0/25 (Dallas VLAN 10) | Any | Any | 80 (TCP), 443 (TCP) | Allow | Outbound |
| 6 | 192.168.10.128/25 (Dallas VLAN 20) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 7 | 192.168.11.0/25 (Dallas VLAN 30) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 8 | 192.168.11.0/25 (Dallas VLAN 30) | Any | 192.168.10.130 (Dallas VoIP PBX Server) | 5060/5061 (TCP or UDP) | Allow | Outbound |
| 9 | 192.168.11.0/25 (Dallas VLAN 30) | Any | 192.168.10.130 (Dallas VoIP PBX Server) | 10000-20000 (UDP) | Allow | Outbound |
| 10 | 192.168.11.0/25 (Dallas VLAN 30) | Any | Any | Any | Deny | Outbound |
| 11 | 192.168.11.128/25 (Dallas VLAN 40) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 12 | 192.168.11.128/25 (Dallas VLAN 40) | Any | Any | 80 (TCP), 443 (TCP) | Allow | Outbound |
| 13 | 192.168.12.0/27 (Dallas VLAN 50) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 14 | 192.168.12.0/27 (Dallas VLAN 50) | Any | Any | Any | Deny | Outbound |
| 15 | 192.168.12.128/25 (Dallas VLAN 60) | Any | 192.168.0.131 (HQ DB Server) | 1433 (TCP) | Allow | Outbound |
| 16 | 192.168.12.128/25 (Dallas VLAN 60) | Any | 192.168.0.132 (HQ RADIUS Server) | 1812/1813 (UDP) | Allow | Outbound |
| 17 | 192.168.12.128/25 (Dallas VLAN 60) | Any | 192.168.0.133 (HQ File Server) | 445 (TCP) | Allow | Outbound |
| 18 | 192.168.12.128/25 (Dallas VLAN 60) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 389/636 (TCP), 53 (UDP), 67 (UDP) | Allow | Outbound |
| 19 | 192.168.12.32/27 (Dallas VLAN 70) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 20 | 192.168.12.32/27 (Dallas VLAN 70) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud VPN Registry) | 9350-9381 (UDP) | Allow | Outbound |
| 21 | 192.168.12.32/27 (Dallas VLAN 70) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Communication) | 80 (TCP), 443 (TCP), 7351 (UDP), 7734 (TCP), 7752 (TCP) | Allow | Outbound |
| 22 | 192.168.12.32/27 (Dallas VLAN 70) | Any | Any | Any | Deny | Outbound |
| 23 | 198.51.100.40 (Dallas Router/Firewall WAN IP) | Any | Any | 123 (UDP) | Allow | Outbound |
| 24 | 198.51.100.40 (Dallas Router/Firewall WAN IP) | Any | *.ods.opinsights.azure.com (Microsoft Azure Log Analytics for SIEM) | 443 (TCP) | Allow | Outbound |
| 25 | 198.51.100.40 (Dallas Router/Firewall WAN IP) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud VPN Registry) | 9350-9381 (UDP) | Allow | Outbound |
| 26 | 198.51.100.40 (Dallas Router/Firewall WAN IP) | Any | 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Communication) | 80 (TCP), 443 (TCP), 7351 (UDP), 7734 (TCP), 7752 (TCP) | Allow | Outbound |
| 27 | 198.51.100.40 (Dallas Router/Firewall WAN IP) | Any | cloud-meraki-asn.amp/cisco.com, cloud-meraki-est.amp.cisco.com (Cisco Meraki Malware Protection) | 443 (TCP) | Allow | Outbound |
| 28 | 198.51.100.40 (Dallas Router/Firewall WAN IP) | Any | api.meraki.com (Cisco Meraki API Requests) | 443 (TCP) | Allow | Outbound |
| 29 | 198.51.100.40 (Dallas Router/Firewall WAN IP) | Any | 8.8.8.8/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Monitor) | ICMP | Allow | Outbound |
| 30 | Any | Any | Any | Any | Deny | All |

---

## Seattle Office

| Rule | Source Address | Source Port | Destination Address | Destination Port | Action | Direction |
|------|----------------|-------------|---------------------|------------------|--------|-----------|
| 1 | 192.168.20.0/25 (Seattle VLAN 10) | Any | 192.168.0.131 (HQ DB Server) | 1433 (TCP) | Allow | Outbound |
| 2 | 192.168.20.0/25 (Seattle VLAN 10) | Any | 192.168.0.132 (HQ RADIUS Server) | 1812/1813 (UDP) | Allow | Outbound |
| 3 | 192.168.20.0/25 (Seattle VLAN 10) | Any | 192.168.0.133 (HQ File Server) | 445 (TCP) | Allow | Outbound |
| 4 | 192.168.20.0/25 (Seattle VLAN 10) | Any | 192.168.0.134 (HQ AD/DNS Server) | 389/636 (TCP), 53 (UDP), 67 (UDP) | Allow | Outbound |
| 5 | 192.168.20.0/25 (Seattle VLAN 10) | Any | Any | 80 (TCP), 443 (TCP) | Allow | Outbound |
| 6 | 192.168.20.128/25 (Seattle VLAN 20) | Any | 192.168.0.134 (HQ AD/DNS Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 7 | 192.168.20.128/25 (Seattle VLAN 20) | Any | 192.168.0.130 (HQ VoIP PBX Server) | 5060/5061 (TCP or UDP) | Allow | Outbound |
| 8 | 192.168.20.128/25 (Seattle VLAN 20) | Any | 192.168.0.130 (HQ VoIP PBX Server) | 10000-20000 (UDP) | Allow | Outbound |
| 9 | 192.168.20.128/25 (Seattle VLAN 20) | Any | Any | Any | Deny | Outbound |
| 10 | 192.168.21.0/25 (Seattle VLAN 30) | Any | 192.168.0.134 (HQ AD/DNS Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 11 | 192.168.21.0/25 (Seattle VLAN 30) | Any | Any | 80 (TCP), 443 (TCP) | Allow | Outbound |
| 12 | 192.168.21.128/27 (Seattle VLAN 40) | Any | 192.168.0.134 (HQ AD/DNS Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 13 | 192.168.21.128/27 (Seattle VLAN 40) | Any | Any | Any | Deny | Outbound |
| 14 | 192.168.21.160/27 (Seattle VLAN 50) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 15 | 192.168.21.160/27 (Seattle VLAN 50) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud VPN Registry) | 9350-9381 (UDP) | Allow | Outbound |
| 16 | 192.168.21.160/27 (Seattle VLAN 50) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Communication) | 80 (TCP), 443 (TCP), 7351 (UDP), 7734 (TCP), 7752 (TCP) | Allow | Outbound |
| 17 | 192.168.21.160/27 (Seattle VLAN 50) | Any | Any | Any | Deny | Outbound |
| 18 | 203.0.113.50 (Seattle Router/Firewall WAN IP) | Any | Any | 123 (UDP) | Allow | Outbound |
| 19 | 203.0.113.50 (Seattle Router/Firewall WAN IP) | Any | *.ods.opinsights.azure.com (Microsoft Azure Log Analytics for SIEM) | 443 (TCP) | Allow | Outbound |
| 20 | 203.0.113.50 (Seattle Router/Firewall WAN IP) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud VPN Registry) | 9350-9381 (UDP) | Allow | Outbound |
| 21 | 203.0.113.50 (Seattle Router/Firewall WAN IP) | Any | 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Communication) | 80 (TCP), 443 (TCP), 7351 (UDP), 7734 (TCP), 7752 (TCP) | Allow | Outbound |
| 22 | 203.0.113.50 (Seattle Router/Firewall WAN IP) | Any | cloud-meraki-asn.amp/cisco.com, cloud-meraki-est.amp.cisco.com (Cisco Meraki Malware Protection) | 443 (TCP) | Allow | Outbound |
| 23 | 203.0.113.50 (Seattle Router/Firewall WAN IP) | Any | api.meraki.com (Cisco Meraki API Requests) | 443 (TCP) | Allow | Outbound |
| 24 | 203.0.113.50 (Seattle Router/Firewall WAN IP) | Any | 8.8.8.8/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Monitor) | ICMP | Allow | Outbound |
| 25 | Any | Any | Any | Any | Deny | All |

---

## Philadelphia Office

| Rule | Source Address | Source Port | Destination Address | Destination Port | Action | Direction |
|------|----------------|-------------|---------------------|------------------|--------|-----------|
| 1 | 192.168.30.0/25 (Phil. VLAN 10) | Any | 192.168.0.131 (HQ DB Server) | 1433 (TCP) | Allow | Outbound |
| 2 | 192.168.30.0/25 (Phil. VLAN 10) | Any | 192.168.0.132 (HQ RADIUS Server) | 1812/1813 (UDP) | Allow | Outbound |
| 3 | 192.168.30.0/25 (Phil. VLAN 10) | Any | 192.168.0.133 (HQ File Server) | 445 (TCP) | Allow | Outbound |
| 4 | 192.168.30.0/25 (Phil. VLAN 10) | Any | 192.168.0.134 (HQ AD/DNS Server) | 389/636 (TCP), 53 (UDP), 67 (UDP) | Allow | Outbound |
| 5 | 192.168.30.0/25 (Phil. VLAN 10) | Any | Any | 80 (TCP), 443 (TCP) | Allow | Outbound |
| 6 | 192.168.30.128/25 (Phil. VLAN 20) | Any | 192.168.0.134 (HQ AD/DNS Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 7 | 192.168.30.128/25 (Phil. VLAN 20) | Any | 192.168.0.130 (HQ VoIP PBX Server) | 5060/5061 (TCP or UDP) | Allow | Outbound |
| 8 | 192.168.30.128/25 (Phil. VLAN 20) | Any | 192.168.0.130 (HQ VoIP PBX Server) | 10000-20000 (UDP) | Allow | Outbound |
| 9 | 192.168.30.128/25 (Phil. VLAN 20) | Any | Any | Any | Deny | Outbound |
| 10 | 192.168.31.0/25 (Phil. VLAN 30) | Any | 192.168.0.134 (HQ AD/DNS Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 11 | 192.168.31.0/25 (Phil. VLAN 30) | Any | Any | 80 (TCP), 443 (TCP) | Allow | Outbound |
| 12 | 192.168.31.128/27 (Phil. VLAN 40) | Any | 192.168.0.134 (HQ AD/DNS Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 13 | 192.168.31.128/27 (Phil. VLAN 40) | Any | Any | Any | Deny | Outbound |
| 14 | 192.168.31.160/27 (Phil. VLAN 50) | Any | 192.168.0.134 (HQ AD/DNS/DHCP Server) | 53 (UDP), 67 (UDP) | Allow | Outbound |
| 15 | 192.168.31.160/27 (Phil. VLAN 50) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud VPN Registry) | 9350-9381 (UDP) | Allow | Outbound |
| 16 | 192.168.31.160/27 (Phil. VLAN 50) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Communication) | 80 (TCP), 443 (TCP), 7351 (UDP), 7734 (TCP), 7752 (TCP) | Allow | Outbound |
| 17 | 192.168.31.160/27 (Phil. VLAN 50) | Any | Any | Any | Deny | Outbound |
| 18 | 203.0.113.60 (Phil. Router/Firewall WAN IP) | Any | Any | 123 (UDP) | Allow | Outbound |
| 19 | 203.0.113.60 (Phil. Router/Firewall WAN IP) | Any | *.ods.opinsights.azure.com (Microsoft Azure Log Analytics for SIEM) | 443 (TCP) | Allow | Outbound |
| 20 | 203.0.113.60 (Phil. Router/Firewall WAN IP) | Any | 64.62.142.12/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud VPN Registry) | 9350-9381 (UDP) | Allow | Outbound |
| 21 | 203.0.113.60 (Phil. Router/Firewall WAN IP) | Any | 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Communication) | 80 (TCP), 443 (TCP), 7351 (UDP), 7734 (TCP), 7752 (TCP) | Allow | Outbound |
| 22 | 203.0.113.60 (Phil. Router/Firewall WAN IP) | Any | cloud-meraki-asn.amp/cisco.com, cloud-meraki-est.amp.cisco.com (Cisco Meraki Malware Protection) | 443 (TCP) | Allow | Outbound |
| 23 | 203.0.113.60 (Phil. Router/Firewall WAN IP) | Any | api.meraki.com (Cisco Meraki API Requests) | 443 (TCP) | Allow | Outbound |
| 24 | 203.0.113.60 (Phil. Router/Firewall WAN IP) | Any | 8.8.8.8/32, 158.115.128.0/19, 209.206.48.0/20, 216.157.128.0/20 (Cisco Meraki Cloud Monitor) | ICMP | Allow | Outbound |
| 25 | Any | Any | Any | Any | Deny | All |
