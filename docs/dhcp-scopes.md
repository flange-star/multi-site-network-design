# DHCP Scopes & Reservations

All sites use a centralized DHCP model with HQ as the primary server and Dallas as the secondary for redundancy. Branch offices (Seattle and Philadelphia) rely on HQ servers for DNS and DHCP services over the VPN.

**Primary DHCP Server:** 192.168.0.134 (HQ AD/DNS/DHCP Server)  
**Secondary DHCP Server:** 192.168.10.134 (Dallas RDOC Server)

**Primary DNS Server:** 192.168.0.134  
**Secondary DNS Server:** 192.168.10.134

---

## Fort Myers, FL — Head Office (HQ)

| VLAN | Purpose | Scope Range | Reservations |
|------|---------|-------------|--------------|
| VLAN 10 | Workstations | 192.168.0.21 – 192.168.0.126 | 192.168.0.1 – 192.168.0.20 (gateway + infrastructure) |
| VLAN 20 | Servers | 192.168.0.141 – 192.168.0.254 | 192.168.0.130 VoIP Server, 192.168.0.131 DB Server, 192.168.0.132 RADIUS Server, 192.168.0.133 File Server, 192.168.0.134 AD/DNS/DHCP Server, 192.168.0.135 – 192.168.0.140 reserved |
| VLAN 30 | VoIP | 192.168.1.31 – 192.168.1.126 | 192.168.1.1 – 192.168.1.30 (gateway + VoIP infrastructure) |
| VLAN 40 | Mobile/Wi-Fi | 192.168.1.130 – 192.168.1.254 | 192.168.1.129 (gateway) |
| VLAN 50 | Printers/Peripherals | 192.168.2.11 – 192.168.2.30 | 192.168.2.1 – 192.168.2.10 (gateway + infrastructure) |
| VLAN 60 | Remote Users | 192.168.2.141 – 192.168.2.254 | 192.168.2.129 – 192.168.2.140 (gateway + infrastructure) |
| VLAN 70 | Access Points | 192.168.2.41 – 192.168.2.62 | 192.168.2.33 Gateway, 192.168.2.34 AP1, 192.168.2.35 AP2, 192.168.2.36 – 192.168.2.40 reserved |

---

## Dallas, TX — Warm Site

| VLAN | Purpose | Scope Range | Reservations |
|------|---------|-------------|--------------|
| VLAN 10 | Workstations | 192.168.10.21 – 192.168.10.126 | 192.168.10.1 – 192.168.10.20 (gateway + infrastructure) |
| VLAN 20 | Servers | 192.168.10.141 – 192.168.10.254 | 192.168.10.130 VoIP Server, 192.168.10.131 DB Server, 192.168.10.132 RADIUS Server, 192.168.10.133 File Server, 192.168.10.134 AD/DNS/DHCP Server, 192.168.10.135 – 192.168.10.140 reserved |
| VLAN 30 | VoIP | 192.168.11.31 – 192.168.11.126 | 192.168.11.1 – 192.168.11.30 (gateway + VoIP infrastructure) |
| VLAN 40 | Mobile/Wi-Fi | 192.168.11.130 – 192.168.11.254 | 192.168.11.129 (gateway) |
| VLAN 50 | Printers/Peripherals | 192.168.12.11 – 192.168.12.30 | 192.168.12.1 – 192.168.12.10 (gateway + infrastructure) |
| VLAN 60 | Remote Users | 192.168.12.141 – 192.168.12.254 | 192.168.12.129 – 192.168.12.140 (gateway + infrastructure) |
| VLAN 70 | Access Points | 192.168.12.41 – 192.168.12.62 | 192.168.12.33 Gateway, 192.168.12.34 AP1, 192.168.12.35 AP2, 192.168.12.36 – 192.168.12.40 reserved |

---

## Seattle, WA — Branch Office

| VLAN | Purpose | Scope Range | Reservations |
|------|---------|-------------|--------------|
| VLAN 10 | Workstations | 192.168.20.21 – 192.168.20.126 | 192.168.20.1 – 192.168.20.20 (gateway + infrastructure) |
| VLAN 20 | VoIP Phones | 192.168.20.141 – 192.168.20.254 | 192.168.20.129 – 192.168.20.140 (gateway + infrastructure) |
| VLAN 30 | Mobile/Wi-Fi | 192.168.21.2 – 192.168.21.126 | 192.168.21.1 (gateway) |
| VLAN 40 | Printers/Peripherals | 192.168.21.141 – 192.168.21.158 | 192.168.21.129 – 192.168.21.140 (gateway + infrastructure) |
| VLAN 50 | Access Points | 192.168.21.171 – 192.168.21.190 | 192.168.21.161 Gateway, 192.168.21.162 AP1, 192.168.21.163 AP2, 192.168.21.164 – 192.168.21.170 reserved |

---

## Philadelphia, PA — Branch Office

| VLAN | Purpose | Scope Range | Reservations |
|------|---------|-------------|--------------|
| VLAN 10 | Workstations | 192.168.30.21 – 192.168.30.126 | 192.168.30.1 – 192.168.30.20 (gateway + infrastructure) |
| VLAN 20 | VoIP Phones | 192.168.30.141 – 192.168.30.254 | 192.168.30.129 – 192.168.30.140 (gateway + infrastructure) |
| VLAN 30 | Mobile/Wi-Fi | 192.168.31.2 – 192.168.31.126 | 192.168.31.1 (gateway) |
| VLAN 40 | Printers/Peripherals | 192.168.31.141 – 192.168.31.158 | 192.168.31.129 – 192.168.31.140 (gateway + infrastructure) |
| VLAN 50 | Access Points | 192.168.31.171 – 192.168.31.190 | 192.168.31.161 Gateway, 192.168.31.162 AP1, 192.168.31.163 AP2, 192.168.31.164 – 192.168.31.170 reserved |
