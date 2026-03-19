# Security Digest — 2026-03-19

Today's threat landscape is dense with high-severity CVEs, active ransomware exploitation, and a wave of AI-specific security findings — from prompt-injection chains targeting Claude users to new research on defending multi-agent systems against steganographic collusion.

---

## AI Security Research

**['Claudy Day' Trio of Flaws Exposes Claude Users to Data Theft](https://www.darkreading.com/vulnerabilities-threats/claudy-day-trio-flaws-claude-users-data-theft)**
*Dark Reading — Elizabeth Montalbano*
A prompt-injection vulnerability chained with two other flaws can turn a Google search into a full attack path capable of exfiltrating data from enterprise Claude deployments. The research underscores how agentic AI workflows expand the attack surface beyond traditional web threats.

**[Meta's AI Glasses and Privacy](https://www.schneier.com/blog/archives/2026/03/metas-ai-glasses-and-privacy.html)**
*Schneier on Security — Bruce Schneier*
Schneier calls Meta's new AI glasses "a privacy disaster," noting there is little the industry can do to stop the technology's spread; an Android app that detects nearby smart glasses has emerged as a grassroots countermeasure.

**[MOSAIC: Composable Safety Alignment with Modular Control Tokens](https://arxiv.org/abs/2603.16210)**
*ArXiv cs.AI*
Researchers propose MOSAIC, a system that encodes context-dependent safety rules as modular control tokens rather than baking them into model weights, enabling fine-grained, per-deployment governance without retraining.

**[Beyond Reward Suppression: Reshaping Steganographic Communication Protocols in MARL via Dynamic Representational Circuit Breaking](https://arxiv.org/abs/2603.15655)**
*ArXiv cs.AI*
The paper introduces DRCB, an architectural defense that targets the optimization substrate itself to prevent multi-agent systems from developing hidden communication channels that evade monitoring — a growing AI safety concern.

**[Steering Frozen LLMs: Adaptive Social Alignment via Online Prompt Routing](https://arxiv.org/abs/2603.15647)**
*ArXiv cs.AI*
This work shows that static post-training alignment degrades against evolving jailbreak techniques, and proposes an inference-time prompt-routing mechanism that adapts safety behavior without modifying model weights.

**[Claude Code Security and Magecart: Getting the Threat Model Right](https://thehackernews.com/2026/03/claude-code-security-and-magecart.html)**
*The Hacker News*
Analysis of where AI-assisted code scanning (e.g., Claude Code) stops and client-side runtime threats begin, using Magecart payloads hidden in EXIF data of dynamically loaded favicons as a case study.

---

## Vulnerabilities & Exploits

**[Interlock Ransomware Exploits Cisco FMC Zero-Day CVE-2026-20131 for Root Access](https://thehackernews.com/2026/03/interlock-ransomware-exploits-cisco-fmc.html)**
*The Hacker News*
The Interlock ransomware gang has been actively exploiting CVE-2026-20131 (CVSS 10.0), an insecure-deserialization flaw in Cisco's Secure Firewall Management Center, since late January — granting unauthenticated remote code execution as root.

**[DarkSword: iPhone Exploit Kit Serves Spies & Thieves Alike](https://www.darkreading.com/threat-intelligence/darksword-iphone-exploit-spies-thieves)**
*Dark Reading — Alexander Culafi*
A sophisticated iOS exploit chain leveraging multiple zero-day vulnerabilities is actively targeting users in Saudi Arabia, Turkey, Malaysia, and Ukraine, enabling both nation-state espionage and data/crypto theft.

**[Critical Unpatched Telnetd Flaw (CVE-2026-32746) Enables Unauthenticated Root RCE](https://thehackernews.com/2026/03/critical-telnetd-flaw-cve-2026-32746.html)**
*The Hacker News*
A CVSS 9.8 out-of-bounds write in the GNU InetUtils telnet daemon allows an unauthenticated remote attacker to execute arbitrary code with root privileges; the flaw remains unpatched at time of disclosure.

**[9 Critical IP KVM Flaws Enable Unauthenticated Root Access Across Four Vendors](https://thehackernews.com/2026/03/9-critical-ip-kvm-flaws-enable.html)**
*The Hacker News*
Eclypsium found nine vulnerabilities in low-cost IP KVM devices from GL-iNet, Angeet/Yeeso, Sipeed, and JetKVM; the most severe allow unauthenticated attackers to gain full control of connected hosts.

**[Ubuntu CVE-2026-3888 Bug Lets Attackers Gain Root via systemd Cleanup Timing Exploit](https://thehackernews.com/2026/03/ubuntu-cve-2026-3888-bug-lets-attackers.html)**
*The Hacker News*
A high-severity (CVSS 7.8) privilege-escalation flaw in Ubuntu Desktop 24.04+ exploits a race condition in systemd's cleanup path, allowing a local unprivileged attacker to achieve full root access.

**[Apple Fixes WebKit Vulnerability Enabling Same-Origin Policy Bypass on iOS and macOS](https://thehackernews.com/2026/03/apple-fixes-webkit-vulnerability.html)**
*The Hacker News*
Apple patched CVE-2026-20643, a cross-origin issue in WebKit's Navigation API that could allow maliciously crafted web content to bypass the same-origin policy on iOS, iPadOS, and macOS.

**[Aura Confirms Data Breach Exposing 900,000 Marketing Contacts](https://www.bleepingcomputer.com/news/security/aura-confirms-data-breach-exposing-900-000-marketing-contacts/)**
*BleepingComputer — Bill Toulas*
Identity protection company Aura disclosed that an unauthorized party accessed nearly 900,000 customer records containing names and email addresses.

**[Marquis: Ransomware Gang Stole Data of 672K People in Cyberattack](https://www.bleepingcomputer.com/news/security/marquis-ransomware-gang-stole-data-of-672-000-people-in-2025-cyberattack/)**
*BleepingComputer — Sergiu Gatlan*
Texas-based financial services provider Marquis revealed that a ransomware attack in August 2025 exfiltrated data from over 670,000 individuals and disrupted operations at 74 US banks.

**[SideWinder Espionage Campaign Expands Across Southeast Asia](https://www.darkreading.com/threat-intelligence/sidewinder-espionage-campaign-expands-across-southeast-asia)**
*Dark Reading — Robert Lemos*
The suspected India-linked SideWinder group is widening its targeting of Southeast Asian governments, telecom operators, and critical infrastructure using spear-phishing and rapidly rotating infrastructure.

**[Researchers: Meta, TikTok Steal Personal & Financial Info When Users Click Ads](https://www.darkreading.com/cyber-risk/meta-tiktok-steal-sensitive-pii)**
*Dark Reading — Nate Nelson*
Tracking pixels embedded in advertiser sites allow Meta and TikTok to collect credit card numbers, geolocations, and other sensitive data even after users navigate away from the social platforms.

---

## Policy & Compliance

**[OFAC Sanctions DPRK IT Worker Network Funding WMD Programs Through Fake Remote Jobs](https://thehackernews.com/2026/03/ofac-sanctions-dprk-it-worker-network.html)**
*The Hacker News*
The US Treasury sanctioned six individuals and two entities tied to North Korea's scheme of placing IT workers in US companies under false pretenses to generate revenue for the DPRK's weapons programs.

**[CISA Orders Feds to Patch Zimbra XSS Flaw Exploited in Attacks](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-zimbra-xss-flaw-exploited-in-attacks/)**
*BleepingComputer — Sergiu Gatlan*
CISA has issued a binding directive requiring US federal agencies to remediate an actively exploited cross-site scripting vulnerability in Zimbra Collaboration Suite.
