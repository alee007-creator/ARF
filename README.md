```markdown
🛡️ ALI RAZA Recon Framework (ARF) v1.0 🛡️
"Automate. Discover. Dominate." — The Hacker Edition

      █████╗ ██╗     ██╗    ██████╗  █████╗ ███████╗ █████╗ 
     ██╔══██╗██║     ██║    ██╔══██╗██╔══██╗╚══███╔╝██╔══██╗
     ███████║██║     ██║    ██████╔╝███████║  ███╔╝ ███████║
     ██╔══██║██║     ██║    ██╔══██╗██╔══██║ ███╔╝  ██╔══██║
     ██║  ██║███████╗██║    ██║  ██║██║  ██║███████╗██║  ██║
     ╚═╝  ╚═╝╚══════╝╚═╝    ╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝

ARF is a professional-grade, multi-threaded offensive security workstation designed for high-concurrency infrastructure auditing, AI-driven tactical strategy, and visual threat intelligence. 

---

## 🏗️ Core Architecture & The Global Workspace

ARF v1.0 employs a Global Workspace Redirect architecture. Regardless of where the framework is installed on your system, all databases (`arf_vault.db`), exported PDFs, screenshots, and tool outputs are safely sandboxed inside `~/ARF_Workspace/`. This ensures persistent data retention, safe package upgrades, and zero clutter on your host OS.

---

## ⚡ Execution Engines: Understanding the 3 Pipelines

ARF features three distinct scanning engines, tailored for different operational needs:

1. [📡] Live Reconnaissance Pipeline (The Flagship Engine)
   * Execution: Python-native, deeply integrated `asyncio` engine.
   * Behavior: Performs comprehensive subdomain enumeration, active port/banner grabbing, WAF detection, Geo-OSINT plotting, extracts JS secrets, and captures resilient headless screenshots (bypassing invalid SSLs and awaiting JavaScript rendering).
   * Output: Instantly draws the Interactive PyVis Node Graph, maps coordinates to the Global Threat Map, calculates the Real-Time Risk Score, generates AI Tactical Briefings, and writes structured data directly to the SQLite Vault.
   * Best For: Deep, interactive GUI analysis and Enterprise PDF reporting.

2. [🌐] Auto Scan: Domain (Detached Kill-Chain)
   * Execution: Pure Bash-driven orchestration script (`recon_runner.sh`).
   * Behavior: Spawns a detached native OS terminal and runs 19 external tools (Subfinder, Nuclei, Katana, etc.) in parallel. 
   * Output: Aggressively dumps raw terminal outputs into a targeted directory and compiles a raw `MASTER_REPORT.html` file, syncing the final flat files back to the Vault.
   * Best For: Raw, noisy, aggressive data dumping across a wide attack surface.

3. [🎯] Auto Scan: IP (Detached Kill-Chain)
   * Execution: Specialized 12-tool Bash pipeline.
   * Behavior: Bypasses DNS/Subdomain enumeration tools (like Subfinder/Assetfinder) to focus purely on direct IP scanning (Nmap, Naabu, Wfuzz).
   * Best For: Direct infrastructure probing and single-server assessments.

---

## 🗂️ The ARF Module Hub (Command Categories)

The framework is divided into 4 primary tactical categories:

### 1. 🔍 Recon & Data
* Live Scanner Log: Real-time, color-coded telemetry stream of your active pipeline.
* Data & Viz: Contains the searchable Data Grid, the PyVis Interactive Topology Graph, and the CartoDB Global Threat Map.
* Attack Surface Diff: Visually compare two scans of the same target to instantly spot new subdomains, newly opened ports, or patched vulnerabilities over time.
* AI Assistant (Hybrid Neural Engine): Toggle between Local Intelligence (Qwen2.5-Coder for offline, free analysis) and Cloud Intelligence (AWS Bedrock Claude 3.5 Sonnet/Opus for heavy-compute architectural auditing).
* Export & Reports: Generate Executive PDFs, launch Maltego CE graphs, or restore historical scans back into the live dashboard.
* Wireless Signals (If Enabled): 802.11 monitor mode management and detached execution for `airodump-ng`, `wifite`, and `wash`.

### 2. 🛠️ System Diagnostics
* System Basics: Rapid-fire 1-click audit commands (`WhoAmI`, `Sudo Privs`, `Active Services`, `Cron Jobs`, `SUID Files`) without leaving the GUI.
* System Monitor: Live hardware telemetry tracking CPU load, RAM usage, Network I/O, and the single heaviest process on the machine to prevent lockups.

### 3. 🚀 Automation & Config
* Auto Scan (Domain/IP): Access to the Detached Kill-Chain pipelines.
* Auto Installer: 1-Click Master OS Bootstrapper for Kali/Debian/Arch to install Go, Python deps, and compile the entire toolset.
* Workspace Config: Create, load, and manage isolated project environments with dedicated API keys and settings.

### 4. 🛡️ ARF Tool Arsenal
* 25+ Direct Tool Interfaces: Dedicated GUI tabs for tools like `Nmap`, `Nuclei`, `Ffuf`, `Katana`, `GitDorker`, and more.
* Custom Presets: Save custom command arguments for 1-click execution.
* Detached Toggle: Choose between streaming the tool output to the GUI or spawning it in a dedicated native OS terminal.

---

## ⚙️ Core Configuration & Telemetry

Fine-tune the engine's behavior via the main configuration panel:

### Targeting & Scope
* Target(s): Input domains/IPs manually or upload a `.txt` list.
* Out of Scope: Enforce strict Regex rules (e.g., `.*\.dev\.example\.com`) to guarantee the engine skips restricted infrastructure.
* Wordlist & Spidering: Select a custom wordlist, or use the [🕷️ Spider Target] button to scrape the target website and automatically generate a highly targeted, context-aware dictionary for fuzzing.

### Global Threat Intelligence APIs
Link your API keys to automatically flag malicious background scanners, CVEs, and leverage cloud AI:
* AWS Bedrock Bearer Token: Unlock enterprise-grade Cloud AI (Claude) using AWS's long-term unified token.
* VirusTotal: Community reputation and vendor flags.
* GreyNoise: Identifies "Internet Background Noise" and benign scanners.
* Pulsedive: Risk scoring and indicator tracking.
* Censys PAT: Deep platform profiling and service discovery.

### Monitoring & Output
* Discord/Slack Webhook: Automatically sends critical alerts (e.g., newly discovered subdomains during a Diff scan) to your team's chat.
* Continuous Monitoring: Enable this to loop the pipeline indefinitely at a specified interval (e.g., every 60 minutes) for continuous Attack Surface Management (ASM).
* Thread Controller: Throttle or maximize concurrent async workers depending on your VPS/hardware capabilities.

---

## 🕹️ System Hotkeys & Advanced Operations

### Pipeline Controls
* Terminate Pipeline: Gracefully sends a stop signal to active workers, finishing current tasks and saving recovered data before halting.
* [Ctrl+Shift+K] Emergency Purge: The "Panic Button." Instantly force-kills all active child threads, orphans detached terminals, and aggressively deletes the current working directory to wipe session artifacts.

### Visual & Environmental Toggles (Menu Bar)
* Toggle Instructor/Presentation Mode: Instantly scales up all application fonts—perfect for screen-sharing, teaching, or capturing readable screenshots for reports.
* Toggle Fullscreen (F11): Maximize the Command Center.
* Enable Wireless Recon Mode: Unlocks the hidden `[📶] Wireless Signals` tab in the Recon category to interact with external Wi-Fi adapters.
* Clear Temporary Data: Flushes local DNS caches and temporary system artifacts.
* Run Pre-Flight Health Check: Audits your OS `$PATH` to verify all required binaries are installed.

---

## 💻 Command Line Interface (CLI) & Headless Mode

ARF v1.0 features a completely decoupled architecture. You can run the entire framework purely from the terminal without a Desktop Environment or X11 forwarding. All CLI operations automatically log the `exec_mode` as "CLI" directly into the SQLite Vault for professional auditing.

### Option 1: The Interactive Console (Metasploit-Style)
For a guided, prompt-driven terminal experience, launch the interactive menu:

```bash
arf -i

```

### Option 2: Headless Automation (Cron / Scripts)

For zero-touch automation on remote VPS environments, use the `-e` flag to dictate the engine.

**CLI Execution Examples:**

**1. Run the Live Python Recon Engine:**

```bash
arf -e live -d example.com -p "Client_Alpha" -t 100 --scope "dev.example.com"

```

**2. Run the Domain Bash Kill-Chain (19 Tools):**

```bash
arf -e domain -d example.com -w my_custom_list.txt -p "Client_Bravo"

```

**3. Execute a Single Arsenal Tool & Save to Vault:**

```bash
arf -e tool -d example.com --toolname "nuclei" --toolargs "-tags cve,critical -u {t}" -p "Client_Alpha"

```

---

## 🚀 Installation & System Build

ARF is deployed as a professional system-wide Debian package (`.deb`). This completely eliminates virtual environment headaches and ensures the framework runs natively from your application menu or terminal anywhere on the system.


### Step 1: System Installation

```bash
# Install the framework and automatically resolve dependencies
sudo dpkg -i ./arf-framework_1.0_amd64.deb

```

*Note: The installer will automatically build a secure, self-contained Python virtual environment at `/opt/arf` and download the necessary headless Chromium browsers for the screenshot engine.*

### Step 2: Launch

You can now launch the framework by either:

1. Searching for **ARF Recon Framework** in your Kali/Linux application menu.
2. Typing `arf` directly into any terminal window.

### Optional: Local AI Setup (Ollama)

If you wish to use the Offline Neural Engine instead of AWS Bedrock:

1. Install Ollama: `curl -fsSL https://ollama.com/install.sh | sh`
2. Download the model: `ollama run qwen2.5-coder:3b`
3. Manage background RAM usage via the "Wake / Sleep" buttons in the ARF AI Assistant tab.

---

## ⚠️ Legal Disclaimer

**For Authorized Security Auditing Only.**
The use of the ALI RAZA Recon Framework for scanning, attacking, or interacting with targets without prior, mutual, and explicit written consent is illegal. It is the end user's absolute responsibility to obey all applicable local, state, and federal laws. The developers assume no liability and are not responsible for any misuse, damage, or data loss caused by this software.

---

**Developed by Ali Raza** *Cybersecurity Professional | Ethical Hacker | Instructor*

```

```
