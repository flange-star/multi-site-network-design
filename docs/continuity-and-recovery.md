# Continuity & Recovery Documentation
**ShopSmart Online — Network Expansion Project**  
*NeoNet Solutions | IT Project Manager: Angelo Cerdas*

---

## Table of Contents
- [Business Continuity Plan (BCP)](#business-continuity-plan-bcp)
- [Disaster Recovery Plan (DRP)](#disaster-recovery-plan-drp)
- [Incident Response Plan (IRP)](#incident-response-plan-irp)
- [Service Level Agreements (SLA)](#service-level-agreements-sla)
  
---

## Business Continuity Plan (BCP)

The BCP defines how ShopSmart Online maintains operations across all four sites during disruptions. The network design supports continuity through the following pillars:

### Redundancy
- Every office is equipped with **Uninterruptible Power Supplies (UPS)** to protect critical networking equipment from sudden power loss
- Every office maintains contracts with **dual Internet Service Providers (ISPs)** to eliminate single points of failure for internet connectivity

### System Failover
- Critical devices — servers, firewalls, and routers — are configured for **automatic failover** to available backup systems to minimize downtime during hardware failures

### Load Balancing
- Cloud vendor load balancing is enabled across ShopSmart's web-facing services to distribute traffic and prevent overload during peak e-commerce demand

### Remote Access & IT Support
- **Full-mesh IPSec VPN infrastructure** allows all users to securely access resources from any location during business interruptions
- Dedicated IT support teams are stationed at each branch office location

### Backup Strategy (3-2-1 Standard)
All sites follow the 3-2-1 backup standard:

| Copy | Location | Type |
|------|----------|------|
| Production copy | On-premises at each site | Live |
| Backup copy 1 | On-premises NAS | Scheduled backup |
| Backup copy 2 | Cloud storage (offsite) | Scheduled backup |

- Automatic full and **30-minute incremental backups** are configured for all servers and business-critical systems
- Daily full backups are configured for endpoint devices
- HQ backups are mirrored to the **Dallas warm site** continuously

---

## Disaster Recovery Plan (DRP)

The DRP establishes ShopSmart Online's procedures for recovering network infrastructure and business operations following major incidents such as cyberattacks, natural disasters, or critical system failures.

### Recovery Objectives

| Metric | Target | Scope |
|--------|--------|-------|
| **RTO** (Recovery Time Objective) | < 2 hours | VPN gateways, servers, routers |
| **RPO** (Recovery Point Objective) | < 30 minutes | Databases, file servers, critical backups |

### Redundancy Infrastructure

| Component | Implementation |
|-----------|---------------|
| Power | UPS at every office location |
| Internet | Dual ISP contracts at every office |
| Hardware | Redundant servers at HQ and Dallas |
| Site | Dallas, TX serves as the designated **warm site** |

### Warm Site — Dallas, Texas
The Dallas office is ShopSmart's dedicated warm site. In the event HQ (Fort Myers) goes offline, Dallas assumes primary operations with pre-provisioned redundant systems and mirrored backups ready to bring online.

### Risk Assessment Matrix

|  | Low Impact | Medium Impact | High Impact |
|--|-----------|--------------|------------|
| **High Probability** | Network hardware reboots | VoIP call QoS issues | Power outage affecting server availability |
| **Medium Probability** | Slight ISP latency at a regional office | VLAN routing misconfiguration affects office connection | Server failure or corruption at HQ |
| **Low Probability** | Company device malfunction | Network hardware failure (switch or router) | Hurricane or flooding affecting HQ infrastructure |

### Roles & Responsibilities

| Role | Responsibility |
|------|---------------|
| IT Manager | Maintains DRP currency, coordinates communications, relays status to stakeholders |
| IT Team | Supports recovery of systems and network operations, assists users during incidents |
| Security Officer | Ensures BCP/DRP compliance with frameworks, communicates with stakeholders |
| Cybersecurity Engineer & Analyst | Investigates incident impact, eliminates vulnerabilities, secures systems during recovery |
| Network Engineer | Leads recovery of network failures, rebuilds VPN and inter-site connectivity |
| Network Team | Supports physical hardware procurement, VLAN reassignment, and connectivity testing |

### Recovery Steps
1. Initiate DRP and communicate incident status to all affected offices and team members
2. Identify recovery location — if HQ is offline, activate Dallas warm site
3. Identify available resources — teams, hardware, power, and connectivity
4. Allocate IT and network teams to confirm the threat has ended
5. Retrieve mirrored backups stored at Dallas
6. Restore critical servers and internal services (VoIP, file sharing)
7. Perform system tests on all operational and critical services before returning to production

### Testing & Maintenance
- DRP integrity evaluated **twice per year** through simulations and user training
- Lessons learned documented and incorporated after every incident or test

---

## Incident Response Plan (IRP)

The IRP defines ShopSmart Online's procedures for detecting, containing, and recovering from cybersecurity incidents.

### Covered Incident Types

| Incident Type | Description |
|--------------|-------------|
| DDoS | Overwhelms network with traffic causing downtime |
| Unauthorized Access | Access to systems or data without permission |
| User Policy Violation | Internal misuse of computing resources |
| Malware | Malicious software compromising sensitive systems |
| Data Exfiltration | Sensitive data suspected of being stolen or lost |

### Incident Response Team (IRT)

**Primary Members**

| Role | Key Responsibilities |
|------|---------------------|
| IT Manager | Leads IRT, initiates response procedures, coordinates recovery |
| Cybersecurity Engineer | Investigates alerts, manages containment, maintains CIA triad |
| Network Engineer | Assesses configurations, isolates compromised segments, supports failover |
| Security Officer | Ensures IRP compliance, collaborates with legal on major breaches |
| HR Representative | Handles incidents involving internal threat actors |

**Secondary Members**

| Role | Key Responsibilities |
|------|---------------------|
| IT Team | Monitors user activity, provides help desk support, assists recovery |
| Network Team | Supports isolation of compromised systems, monitors suspicious traffic |
| Cybersecurity Analyst | Detects anomalies, isolates compromised systems, documents findings |
| Legal Representatives | Advises on contractual matters, ensures regulatory compliance |

### Escalation Procedure

| Severity | Examples | Resolution Target |
|----------|---------|------------------|
| **Low** | False-positive antivirus flags, password resets, suspicious login attempts | 1 business day |
| **Moderate** | Malware on remote devices, open port discovery, VoIP QoS issues | 4–8 hours |
| **High** | DDoS, data exfiltration, unauthorized access to critical servers | 1–4 hours |

> **Customer Data Rule:** If customer data is compromised, legal representatives must be notified immediately and customers notified within **24 hours** to comply with applicable regulations (GDPR, CCPA).

### Communication Plan
- IT Manager distributes updates across the full IRT
- Secondary members must alert primary members within **10 minutes** of detecting an incident
- Stakeholders and legal notified within **1 hour** of incident identification
- Primary communication channels: email, dashboards, VoIP, and ticketing system

### Incident Response Lifecycle (NIST CSF 2.0)

| Phase | Lead | Actions |
|-------|------|---------|
| Govern | Security Officer, IT Manager | Establish policies, define roles, maintain awareness training |
| Identify | Cybersecurity Engineer, Network Engineer | Risk assessments, vulnerability identification |
| Protect | Network & IT Teams | Deploy firewalls, IDPS, enforce access controls and backups |
| Detect | Cybersecurity Engineer & Analyst | Monitor IDPS alerts, vulnerability scanning |
| Respond | Full IRT | Escalation procedures, threat isolation, resolution |
| Recover | IT Manager, Network & Cybersecurity Teams | Restore systems, confirm functionality, document findings |

---

## Service Level Agreements (SLA)

ShopSmart Online's SLA targets define the minimum acceptable performance standards across all four sites.

### Uptime Targets

| Service | Target Uptime | Maximum Allowable Downtime |
|---------|-------------|--------------------------|
| Core network infrastructure | 99.99% (four nines) | ~52 minutes/year |
| Cloud vendor services (Azure/Cisco) | 99.99% (four nines) | ~52 minutes/year |
| Site-to-site VPN tunnels | 99.9% (three nines) | ~8.7 hours/year |
| ISP failover recovery | < 1 minute | Per incident |
| VPN failover recovery | < 3 minutes | Per incident |

### Latency & Performance Targets

| Metric | Target |
|--------|--------|
| Inter-site latency | < 50 ms |
| VoIP jitter | < 30 ms |
| VoIP packet loss | < 1% |


### Test Cases Summary

| Test | Objective | Pass Criteria |
|------|-----------|--------------|
| VPN Remote User Access | Verify RADIUS authentication for remote users | VPN connects, authorized resources accessible |
| Site-to-Site VPN Failover | Confirm automated rerouting when links fail | Failover completes under 3 minutes |
| ISP Failover | Verify dual ISP automatic failover via Meraki MX | Connectivity restored within 1 minute |
| Site-to-Site Connectivity | Ensure low-latency inter-site connections | Latency < 50 ms on all links |
| VoIP QoS | Validate voice quality under load | Jitter < 30 ms, packet loss < 1% |
| Server Connectivity | Verify user access to HQ and Dallas resources | All services reachable without errors |
| Firewall Rule Enforcement | Confirm ACLs block unauthorized traffic | Only authorized ports open, suspicious traffic blocked |
| Security Alerts | Verify IDPS and SIEM logging and alerting | Real-time alerts generated, all activity logged |
