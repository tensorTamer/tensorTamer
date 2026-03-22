<!-- Header -->
<div align="center">

```
╔═══════════════════════════════════════════════════════════════╗
║          ENTERPRISE MSP LAB · BUILT FROM SCRATCH             ║
║          Networking · Security · Cloud · AI                   ║
╚═══════════════════════════════════════════════════════════════╝
```

# Adwaith Jayaraj

**Computer Systems Networking & Telecommunications · Holland College, PEI**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-adwaith--jayaraj-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/adwaith-jayaraj)
[![Email](https://img.shields.io/badge/Email-adwaith.jayaraj03info@gmail.com-D14836?style=flat-square&logo=gmail)](mailto:adwaith.jayaraj03info@gmail.com)
[![Location](https://img.shields.io/badge/Location-Charlottetown%2C%20PEI-green?style=flat-square)](https://maps.app.goo.gl/pei)
[![OCI](https://img.shields.io/badge/OCI-Associate%20Certified-F80000?style=flat-square&logo=oracle)](https://www.oracle.com/cloud/)

</div>

---

## 👋 About Me

I'm a first-year networking student who doesn't wait for classroom assignments to build things.

Over the past months I've designed and deployed a **full enterprise MSP environment from scratch** — the same infrastructure real Managed Service Providers use to run and secure client businesses. Active Directory, pfSense firewall, Wazuh SIEM, and now migrating it all to Oracle Cloud Infrastructure with hybrid identity via Microsoft Entra Connect.

I learn by building. Everything in this GitHub is real, running, and documented.

> *Inspired by the standards of industry leaders: Bulletproof, Bluewave, ProServeIT, and Buchanan Technologies.*

---

## 🏗️ Featured Project — Enterprise MSP Lab

> **A production-grade business network built inside a virtual environment, simulating real MSP infrastructure.**

### Phase 1 — Core Infrastructure ✅

```
┌─────────────────────────────────────────────────────┐
│                    WAN (Internet)                    │
└────────────────────────┬────────────────────────────┘
                         │
              ┌──────────▼──────────┐
              │   pfSense Firewall  │  ← Segmented WAN + Private LAN
              │   Strict routing    │    Stateful packet inspection
              └──────────┬──────────┘
                         │ Private LAN
         ┌───────────────┼───────────────┐
         │               │               │
┌────────▼───┐  ┌────────▼───┐  ┌───────▼────┐
│ Windows    │  │  Windows   │  │   Linux    │
│ Server2022 │  │    10      │  │  (Ubuntu)  │
│ Domain Ctrl│  │  Endpoint  │  │  Endpoint  │
└────────────┘  └────────────┘  └────────────┘
```

| Component | Details |
|---|---|
| **Hypervisor** | Hyper-V on Windows Server 2022 Datacenter |
| **Firewall** | pfSense — segmented WAN/LAN, strict routing rules |
| **Identity** | Active Directory DS — Primary Domain Controller |
| **Endpoints** | Windows 10 + Ubuntu Linux, both domain-joined |
| **Policy** | Group Policy Objects (GPOs) — baseline security hardening |

---

### Phase 2 — Security Monitoring with Wazuh SIEM ✅

```
┌─────────────────────────────────────────────────────┐
│              Wazuh Manager (Linux)                   │
│         alerts.log │ alerts.json │ Dashboard         │
└──────────┬──────────────┬────────────────┬──────────┘
           │              │                │
    ┌──────▼──────┐ ┌─────▼──────┐  ┌─────▼──────┐
    │Wazuh Agent  │ │Wazuh Agent │  │ FIM Engine │
    │Win Server   │ │Windows 10  │  │ CVE Detect │
    │2022         │ │Endpoint    │  │ Vuln Scan  │
    └─────────────┘ └────────────┘  └────────────┘
```

**What I built:**
- Deployed Wazuh manager on Linux with agents across all Windows endpoints
- Ingested raw telemetry from `alerts.log` and `alerts.json` — beyond default configs
- Enabled **File Integrity Monitoring (FIM)** — detects unauthorized file changes in real-time
- Activated **CVE vulnerability engine** — data-driven patch management across all assets
- **Adversary emulation tested** — successfully flagged Nmap scans and unauthorized directory traversal

**Real simulation results:**

```bash
# Wazuh successfully detected and alerted on:
[ALERT] Rule 100002 fired — Nmap scan detected from 192.168.1.x
[ALERT] Rule 550     fired — File integrity changed: /etc/passwd
[ALERT] Rule 510     fired — Unauthorized directory traversal attempt
[ALERT] CVE-2024-xxxx — Critical vulnerability detected on WIN-SERVER-01
```

---

### Phase 3 — OCI Cloud Migration + Hybrid Identity 🔄 In Progress

```
┌──────────────────────────────────────────────────────────────┐
│                  Oracle Cloud Infrastructure                  │
│                                                              │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐               │
│  │   VCN    │    │Site-to-  │    │   NLB    │               │
│  │ Subnets  │◄──►│Site VPN  │◄──►│Load Bal. │               │
│  └──────────┘    └──────────┘    └──────────┘               │
│                        ▲                                     │
└────────────────────────┼─────────────────────────────────────┘
                         │ IPSec Tunnel
┌────────────────────────▼─────────────────────────────────────┐
│                  On-Premises (College Lab)                    │
│                                                              │
│  [pfSense] ◄──► [Windows Server 2022 + AD DS]               │
│                         │                                    │
│                  [Entra Connect]                              │
│                         │                                    │
│                  [Azure Entra ID] ◄─── Hybrid Identity       │
└──────────────────────────────────────────────────────────────┘
```

**Goal:** Unified cloud + on-prem security monitoring with a true hybrid identity model.

---

## 🛠️ Technical Skills

```
NETWORKING          ████████████████████░   TCP/IP · DNS · DHCP · VLANs · VPN · pfSense · CCNA concepts
SYSTEMS ADMIN       ████████████████████░   Windows Server 2022 · Active Directory · GPO · Linux · Hyper-V
CLOUD               ████████████████░░░░░   OCI (VCN · S2S VPN · NLB · FastConnect) · Azure Entra ID
SECURITY & SIEM     ████████████████░░░░░   Wazuh · FIM · CVE Detection · Log Analysis · Threat Emulation
SCRIPTING           ████████████░░░░░░░░░   PowerShell · Python (basic)
IT SUPPORT          ████████████████████░   A+ · Remote Desktop · VPN · Cross-platform (Win/Mac/Linux/iOS/Android)
M365                ████████████████░░░░░   Office 365 Admin · Teams · SharePoint · Outlook
AI & MCP            ██████░░░░░░░░░░░░░░░   Model Context Protocol · Claude API · Learning actively
```

---

## 📜 Certifications

| Certification | Status | Issuer |
|---|---|---|
| Oracle Cloud Infrastructure 2025 Associate | ✅ Issued 2025 | Oracle |
| Oracle Cloud Infrastructure Networking Professional | 🔄 In Progress | Oracle |
| CompTIA Network+ | 🔄 In Progress | CompTIA |
| IT Service Desk: Customer Service Foundations | ✅ Issued 2025 | LinkedIn Learning |
| TCS Young Professional | ✅ Issued Aug 2022 | Tata Consultancy Services |
| Emergency First Aid & CPR/AED Level C | ✅ Valid Jun 2027 | Canadian Red Cross |

---

## 💼 Experience

**Software Engineering Intern** · JPMorgan Chase & Co. *(Jan–Mar 2022, Remote)*
> Applied programming principles to complex engineering and data problems in a remote corporate environment.

**Assistant Brand Manager** · Reliance Retail *(Apr 2022–Nov 2023, India)*
> Managed sales and inventory systems; served as primary technical contact resolving complex issues.

---

## 📊 What's Next

- [ ] **Finish CompTIA Network+** — exam date booked
- [ ] **MCP integration project** — building an MCP server that wraps Wazuh alerts (AI-queryable SIEM)
- [ ] **Complete OCI migration** — full hybrid cloud lab
- [ ] **CompTIA Security+** — after Network+

---

## 📫 Let's Connect

I'm actively looking for **summer IT opportunities** in Charlottetown, PEI — MSP, helpdesk, sysadmin, cloud, or security. If you're hiring or know someone who is, let's talk.

📧 adwaith.jayaraj03info@gmail.com  
📞 902-978-3375  
🔗 [linkedin.com/in/adwaith-jayaraj](https://linkedin.com/in/adwaith-jayaraj)

---

<div align="center">

*"The foundation is set. The monitoring is live. The cloud migration is underway."*

![Visitor Count](https://komarev.com/ghpvc/?username=tensorTamer&color=brightgreen&style=flat-square)

</div>
