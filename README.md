# 🐱 cat3 | Advanced Recon & Vulnerability Framework

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/bash-Professional-green.svg)
![Security](https://img.shields.io/badge/Focus-Anti--Blocking-red.svg)

**cat3** is a high-performance, stealth-oriented reconnaissance and vulnerability scanning framework. It is specifically engineered for bug bounty hunters and security researchers who need to perform deep analysis without triggering WAFs or getting their IP banned.

The tool orchestrates a powerful pipeline of industry-standard tools, wrapped in a custom logic that prioritizes **stealth** and **precision**.

---

## ✨ Key Features

- **🛡️ Anti-Blocking Engine:** Implements advanced rate-limiting, concurrency control, and User-Agent randomization to bypass modern IDS/WAF systems.
- **🎯 Precision Targeting:** Uses a "Filter-First" approach; it only scans hosts verified as "alive" by `httpx`, reducing noise and detection risk.
- **🔍 Automated Pipeline:** 
  `Subdomain Discovery` $\rightarrow$ `Alive Host Filtering` $\rightarrow$ `Stealth Vulnerability Scanning`.
- **⚡ Nuclei Integration:** Leverages the power of Nuclei templates with custom stealth profiles (Critical/High vs. Full Deep Scan).
- **📂 Structured Data:** Automatically organizes all findings into domain-specific directories for easy reporting.

---

## 🛠️ Installation & Requirements

### 1. Dependencies
`cat3` acts as an orchestrator. You must have the following tools installed in your system path:

| Tool | Purpose | Installation |
| :--- | :--- | :--- |
| **Nuclei** | Vulnerability Scanning | `go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest` |
| **Subfinder** | Subdomain Enumeration | `go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest` |
| **httpx** | Alive Host Probing | `go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest` |
| **Assetfinder** | Subdomain Discovery | `go install github.com/tomnomnom/assetfinder@latest` |

### 2. Setup
```bash
# Clone the repository
git clone https://github.com/imostafaa7/cat3.git
cd cat3

# Give execution permission to the script
chmod +x cat3
usag
./cat3 target.com
