🐱 cat3 - Advanced Recon & Vulnerability Framework
cat3 is a professional, stealth-oriented reconnaissance and vulnerability scanning framework designed for bug bounty hunters and security researchers. It integrates the power of several industry-standard tools with a specialized focus on anti-blocking techniques and stealth scanning using the Nuclei engine.

🚀 Features
Multi-Stage Reconnaissance:
Automatic subdomain enumeration using subfinder and assetfinder.
Precision alive-host filtering using httpx to reduce noise and avoid WAF triggers.
Intelligent Vulnerability Scanning:
Powered by Nuclei for high-accuracy template-based scanning.
Stealth Mode: Targets only Critical and High severity vulnerabilities.
Deep Analysis Mode: Exhaustive scan using all available templates.
🛡️ Anti-Blocking System:
Rate Limiting (-rl): Strict control over requests per second to bypass Rate-Limiters.
Concurrency Control (-c): Managed threading to avoid server overload and IDS detection.
User-Agent Spoofing: Custom browser-like headers to mask the tool's identity.
Bulk Size Optimization: Minimized batch sizes to mimic human behavior.
Organized Output: Creates dedicated directory structures for every target to keep your research clean and structured.
🛠️ Installation
1. Prerequisites
Ensure you have the following tools installed in your path:

Nuclei
Subfinder
httpx
Assetfinder
2. Setup
# Clone the repository (if applicable) or save the script
chmod +x cat3.sh
📖 Usage
Run the script by passing the target domain as the first argument:

./cat3.sh example.com
Menu Options:
Option	Mode	Description
1	Full Stealth Recon	Full pipeline: Subdomains 
→
→ Alive Check 
→
→ Stealth Nuclei Scan.
2	Quick Scan	Rapidly checks for Critical/High vulnerabilities on known alive hosts.
3	Deep Analysis	Comprehensive scan using all templates (Slow mode for safety).
4	Recon Only	Only gathers subdomains and filters alive hosts.
5	Update	Updates Nuclei templates to the latest version.
⚙️ Stealth Logic (The "Anti-Block" Secret)
Unlike standard scanners that "flood" a server, cat3 implements a tactical approach:

Filter First: It never scans a dead domain. By using httpx first, it ensures every request sent by Nuclei is targeted at a responding service.
Throttling: It uses a low Rate Limit (default 10 rps) and low concurrency, making the traffic look less like a bot and more like a slow user.
Identity Masking: Every request is wrapped in a modern Chrome User-Agent header to bypass basic WAF filters.
📂 Project Structure
cat3_domain/
├── recon/
│   ├── subs.txt      # All discovered subdomains
│   └── alive.txt     # Only hosts responding to HTTP/HTTPS
└── nuclei/
    └── results.txt   # Validated vulnerabilities found
⚠️ Disclaimer
cat3 is intended for educational purposes and authorized security testing only. Scanning targets without explicit permission is illegal. The author is not responsible for any misuse of this tool.

Developed with ❤️
