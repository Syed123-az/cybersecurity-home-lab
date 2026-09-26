# 🔐 Cybersecurity Home Lab

A hands-on cybersecurity laboratory built using VMware, Kali Linux, and intentionally vulnerable virtual machines to practice penetration testing, vulnerability assessment, exploitation, detection, and remediation.

> ⚠️ **Disclaimer:** All testing documented in this repository is performed only against intentionally vulnerable systems in my isolated personal lab. No unauthorized systems or networks are targeted.

---

## 🎯 Objectives

The goal of this project is to gain practical experience with the complete cybersecurity workflow:

- Network reconnaissance
- Port and service enumeration
- Vulnerability identification
- Vulnerability validation
- Controlled exploitation
- Privilege escalation
- Log and attack detection
- Security remediation
- Security documentation

---

## 🧪 Lab Environment

| Component | Details |
|---|---|
| Attacker | Kali Linux |
| Target | Metasploitable 2 |
| Virtualization | VMware Workstation Pro |
| Network | VMware VMnet1 Host-Only |
| Kali IP | `192.168.48.128` |
| Target IP | `192.168.48.129` |

### Network Architecture

```text
                 VMware VMnet1
              192.168.48.0/24
                     │
          ┌──────────┴──────────┐
          │                     │
     Kali Linux            Metasploitable 2
   192.168.48.128          192.168.48.129
      ATTACKER                  TARGET
