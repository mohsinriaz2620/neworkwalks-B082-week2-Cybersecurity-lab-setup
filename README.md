# Week 2 – Footprinting (GHDB) & Network Scanning (Zenmap)

**Cybersecurity & Ethical Hacking Program — NetworkWalks Academy (Batch B082)**
**Author:** Mohsin
**Modules:** W2-PM2 (Footprinting & Reconnaissance with GHDB) · W2-PM5 (Network Scanning with Zenmap)

---

## 📌 Overview

This repository documents two reconnaissance-phase exercises completed during Week 2 of the NetworkWalks Cybersecurity & Ethical Hacking internship:

1. **Footprinting with the Google Hacking Database (GHDB)** — using pre-built Google search operators ("dorks") to passively locate publicly exposed devices and files, without ever directly contacting the target infrastructure during discovery.
2. **Network Scanning with Zenmap** — using the Zenmap GUI (Nmap) to actively discover live hosts on a local subnet, resolve their IP/MAC addresses, and generate a network topology diagram.

Both activities map to **Phase 1 (Reconnaissance)** and **Phase 2 (Scanning)** of a standard penetration testing methodology, and were carried out strictly within the scope defined in the attached Letter of Authorization.

---

## ⚠️ Legal & Ethical Notice

All activities in this repository were performed for **educational purposes only**, under a signed Letter of Authorization (see [`docs/Letter-of-Authorization.pdf`](docs/Letter-of-Authorization.pdf)), against:

- `networkwalks.com` — the client's own public website and DNS records
- The tester's own local area network (LAN)

**No exploitation, unauthorized access, brute-forcing, or intrusive testing was performed.** GHDB findings were located and verified purely through passive, publicly indexed search results. Nothing in this repository should be used to access, disrupt, or interfere with any system you do not own or have explicit written permission to test.

If you are not authorized to test a target, **do not use these techniques against it.** Unauthorized access is illegal in most jurisdictions, even when no data is damaged.

---

## 🗂️ Repository Structure

```
├── README.md
├── report/
│   └── Mohsin_W2_Pentest_Report_GHDB_Zenmap.docx   # Full penetration testing report
├── docs/
│   └── Letter-of-Authorization.pdf                 # Signed scope & permission (Appendix A of report)
└── evidence/
    ├── ghdb/                                        # Screenshots of verified GHDB findings
    └── zenmap/                                      # Zenmap scan output + topology PDF
```

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Google Search Engine | Executes GHDB dorks against publicly indexed content |
| [Google Hacking Database (GHDB)](https://www.exploit-db.com/google-hacking-database) | Curated repository of Google dorks for locating exposed devices/files |
| [Zenmap](https://nmap.org/zenmap/) (Nmap GUI) | Local subnet scanning and live host discovery |
| Windows CMD (`ipconfig`) | Identify local IP address, subnet mask, and MAC address |

---

## 🔍 Module 1 — Footprinting with GHDB

**Objective:** Use GHDB dorks to identify publicly exposed assets through Google alone, with zero direct interaction with the target.

**Task 1 — Live, exposed security cameras**
Searched GHDB for camera-related dorks (e.g. `intitle:"webcamXP" inurl:8080`), ran each dork in Google, and manually verified 10 live, internet-accessible camera interfaces.

**Task 2 — Publicly downloadable mathematics eBooks**
Used directory-listing dorks (e.g. `intitle:index.of "parent directory" mathematics pdf`) to identify 10 open directories containing downloadable PDF files.

Full findings with links and dorks are recorded in the report (Section 4.1) and in `evidence/ghdb/`.

**Key takeaway:** GHDB turns an ordinary search engine into a powerful, fully passive reconnaissance tool — every result comes from Google's own index, so the target is never directly probed, making this technique very hard to detect from the defender's side.

---

## 🔍 Module 2 — Network Scanning with Zenmap

**Objective:** Discover live hosts on a local subnet and map the network topology.

**Steps performed:**
1. Identified local IP address and subnet mask via `ipconfig`
2. Ran a **Ping Scan** (`nmap -sn <subnet>/24`) in Zenmap against the local subnet
3. Recorded the number of live hosts, their IP addresses, and their MAC addresses
4. Generated and exported the **network topology diagram** to PDF via Zenmap's Topology tab

Full results are recorded in the report (Section 4.2) and in `evidence/zenmap/`.

**Key takeaway:** Active scanning complements passive footprinting — where GHDB reveals what's exposed to the internet, Zenmap reveals what's actually alive and reachable on a given network segment.

---

## 📊 Risk Summary

| Finding | Risk Level |
|---|---|
| Live, unauthenticated security cameras indexed by Google | 🔴 Critical |
| Open directory listings exposing downloadable files | 🟠 Medium |
| Fully passive, hard-to-detect device profiling via Google | 🟠 Medium |
| Multiple live hosts visible on local network | 🟠 Medium |
| Host identity exposed via IP/MAC address | 🟡 Low |

Full risk analysis, impact assessment, and recommendations are detailed in the report.

---

## 📄 Full Report

The complete write-up — including methodology, evidence, risk analysis, recommendations, and the signed Letter of Authorization (Appendix A) — is available here:

📥 [`report/Mohsin_W2_Pentest_Report_GHDB_Zenmap.docx`](report/Mohsin_W2_Pentest_Report_GHDB_Zenmap.docx)

---

## 🎓 About This Program

This work was completed as part of the **NetworkWalks Cybersecurity & Ethical Hacking Program (Batch B082)**, under the supervision of **Waqas Karim (CCIE)** at NetworkWalks Academy.

🔗 [networkwalks.com](https://www.networkwalks.com)

---

## 👤 Author

**Muhammad Mohsin**
Cybersecurity & Ethical Hacking Trainee
📍 Pakistan
