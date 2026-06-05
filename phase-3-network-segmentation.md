# Phase 3: Network Segmentation

**Objective:** Isolate the virtual lab environment from the host network while enabling secure communication between virtual machines.

---

## Tools Used

- Oracle VirtualBox
- Windows Firewall
- Host-Only Networking (192.168.56.0/24)

---

## Steps Performed

1. Configured VirtualBox Host-Only networking adapter
2. Isolated lab traffic from the internet
3. Added Metasploitable 2 to the internal network
4. Assigned static IP addresses to all virtual machines
5. Verified communication between systems via ping
6. Configured firewall protections on the host machine

---

## IP Address Configuration

| System | Role | IP Address |
|---|---|---|
| Windows Server 2022 | Domain Controller | 192.168.56.10 |
| Kali Linux | Attacker VM | 192.168.56.20 |
| Windows 11 | Domain Workstation | 192.168.56.30 |
| Metasploitable 2 | Vulnerable Target | 192.168.56.104 |

---

## Network Topology

![Network topology diagram](assets/network-diagram.png)

---

## Firewall Traffic Rules

| Direction | Protocol / Port | Action |
|---|---|---|
| Inbound | SMB — 445 | Allow |
| Inbound | LDAP — 389 | Allow |
| Inbound | Kerberos — 88 | Allow |
| Inbound | DNS — 53 | Allow |
| Inbound | Splunk — 8089 | Allow |
| Inbound | FTP — 21 | Block |
| Inbound | Telnet — 23 | Block |

---

## Security Controls Implemented

- Internal network isolation (no external internet routing)
- Windows Firewall rule enforcement
- Static IP addressing on all VMs
- Host traffic restrictions

---

## Skills Demonstrated

- Network Segmentation
- Virtual Networking
- Firewall Configuration
- IP Address Management
- Secure Lab Design

---

## Lessons Learned

Network segmentation reduces exposure to external threats and safely contains intentionally vulnerable systems such as Metasploitable 2.

This phase also demonstrated the importance of isolating penetration testing environments — a standard practice in enterprise security operations.
