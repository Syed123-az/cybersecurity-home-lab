# 01 — Network Setup

## Objective

Build an isolated cybersecurity lab in VMware Workstation Pro so that penetration-testing exercises can be performed safely against intentionally vulnerable virtual machines.

## Lab Environment

| Machine | Role | IP Address | Network |
|---|---|---|---|
| Windows Host | Host | `192.168.48.1` | VMnet1 |
| Kali Linux | Attacker | `192.168.48.128` | VMnet1 |
| Metasploitable 2 | Target | `192.168.48.129` | VMnet1 |

## Network Configuration

- **Virtual Network:** VMnet1
- **Network Type:** Host-only
- **Subnet:** `192.168.48.0/24`
- **Subnet Mask:** `255.255.255.0`
- **DHCP:** Enabled
- **Host Virtual Adapter:** Enabled

## Network Architecture

```text
                    Windows Host
                   192.168.48.1
                         |
                         |
                    VMware VMnet1
                     Host-Only
                         |
              +----------+----------+
              |                     |
        Kali Linux             Metasploitable 2
       192.168.48.128           192.168.48.129
         ATTACKER                  TARGET




Why Host-Only Networking?

Metasploitable 2 is intentionally vulnerable and should not be exposed to a real network.

VMnet1 provides an isolated virtual network that allows Kali Linux and Metasploitable 2 to communicate while keeping the vulnerable target separated from the physical network.

Verification
Kali IP Address
ip addr
Kali received:192.168.48.128/24
Metasploitable 2 IP Address
ifconfig
Metasploitable 2 received:192.168.48.129
Connectivity Test

From Kali:ping -c 4 192.168.48.129
Result:4 packets transmitted, 4 received, 0% packet loss
This confirmed connectivity between the attacker and target machines.

Security Considerations
Testing is restricted to the isolated virtual laboratory.
Metasploitable 2 is intentionally vulnerable.
The target is not connected directly to the physical/home network.
No unauthorized systems are tested.
Outcome

The isolated VMware cybersecurity laboratory was successfully configured.

Attacker: Kali Linux — 192.168.48.128
Target: Metasploitable 2 — 192.168.48.129

The environment is ready for reconnaissance and vulnerability-assessment exercises.
