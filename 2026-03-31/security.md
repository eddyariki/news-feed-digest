# Security Digest — 2026-03-31

Today's threat landscape is defined by active exploitation of critical enterprise vulnerabilities (Citrix NetScaler, Fortinet BIG-IP) alongside a growing wave of AI-assisted malware and new research pushing ML-based detection into practical deployment.

---

## AI Security Research

**[OpenAI Patches ChatGPT Data Exfiltration Flaw and Codex GitHub Token Vulnerability](https://thehackernews.com/2026/03/openai-patches-chatgpt-data.html)**
*The Hacker News*
Check Point researchers found that a single malicious prompt could silently turn a ChatGPT conversation into a covert exfiltration channel, leaking user messages, uploaded files, and session data. A separate Codex vulnerability exposed GitHub tokens; both have now been patched by OpenAI.

**[Machine Learning Transferability for Malware Detection](https://arxiv.org/abs/2603.26632)**
*arXiv cs.CR*
This study evaluates how well ML-based malware detectors transfer across datasets and distribution shifts, exposing feature-compatibility gaps in public datasets that limit real-world generalization. The findings highlight that obfuscation-based evasion remains a practical threat to static-scanning models.

**[Knowdit: Agentic Smart Contract Vulnerability Detection with Auditing Knowledge Summarization](https://arxiv.org/abs/2603.26270)**
*arXiv cs.CR*
Knowdit uses an agent-driven approach to extract recurring DeFi vulnerability patterns—termed "DeFi semantics"—across diverse smart contract codebases, addressing the business-logic coupling that makes automated auditing difficult. The system targets the billions of dollars at risk in decentralized finance contracts.

**[CANGuard: A Spatio-Temporal CNN-GRU-Attention Hybrid Architecture for Intrusion Detection in In-Vehicle CAN Networks](https://arxiv.org/abs/2603.25763)**
*arXiv cs.CR*
CANGuard proposes a hybrid deep learning architecture that fuses spatial and temporal signals to detect DoS and spoofing attacks on automotive Controller Area Network (CAN) buses. As vehicle connectivity expands, in-vehicle intrusion detection is becoming a critical safety concern.

---

## Vulnerabilities & Exploits

**[Critical Citrix NetScaler Memory Flaw Actively Exploited in Attacks](https://www.bleepingcomputer.com/news/security/critical-citrix-netscaler-memory-flaw-actively-exploited-in-attacks/)**
*Bleeping Computer*
CVE-2026-3055 is a critical memory-corruption bug in Citrix NetScaler ADC and Gateway being actively leveraged to harvest sensitive data from enterprise edge appliances. Organizations running unpatched NetScaler devices should treat this as an emergency patch priority.

**[Fortinet BIG-IP Vulnerability Reclassified as RCE, Under Exploitation](https://www.darkreading.com/application-security/fortinet-big-ip-vulnerability-reclassified-rce-exploitation)**
*Dark Reading*
CVE-2025-53521 was originally rated a high-severity denial-of-service flaw when disclosed in October, but new analysis confirms it enables full remote code execution and is already being exploited in the wild. The reclassification significantly raises the urgency for patching BIG-IP deployments.

**[New RoadK1ll WebSocket Implant Used to Pivot on Breached Networks](https://www.bleepingcomputer.com/news/security/new-roadk1ll-websocket-implant-used-to-pivot-on-breached-networks/)**
*Bleeping Computer*
RoadK1ll is a stealthy post-compromise implant that abuses WebSocket tunnels to enable lateral movement from an initial foothold across segmented networks. Its covert channel design makes it difficult to detect with standard perimeter monitoring.

**[DeepLoad Malware Uses ClickFix and WMI Persistence to Steal Browser Credentials](https://thehackernews.com/2026/03/deepload-malware-uses-clickfix-and-wmi.html)**
*The Hacker News*
DeepLoad is a newly documented loader that uses ClickFix social engineering to trick users into self-executing payloads, then achieves persistence via WMI and immediately begins harvesting browser passwords and session cookies. ReliaQuest researchers note it likely employs AI-assisted obfuscation to evade static scanners.

**[Storm Brews Over Critical, No-Click Telegram Flaw](https://www.darkreading.com/application-security/storm-brews-critical-no-click-telegram-flaw)**
*Dark Reading*
A reported zero-interaction vulnerability in Telegram—allegedly triggered by a malformed sticker—received a 9.8 CVSS score, though Telegram disputes its existence. Security researchers are continuing to investigate while the controversy raises questions about responsible disclosure on high-impact messaging platforms.

**[Three China-Linked Clusters Target Southeast Asian Government in 2025 Cyber Campaign](https://thehackernews.com/2026/03/three-china-linked-clusters-target.html)**
*The Hacker News*
Three distinct China-aligned threat actors coordinated against a single Southeast Asian government entity, deploying an arsenal including HIUPAN (USB-spreading worm), PUBLOAD, and multiple RATs in what researchers call a "complex and well-resourced operation." The campaign underscores sustained state-sponsored interest in regional government intelligence.

---

## Policy & Compliance

**[The State of Secrets Sprawl 2026: 9 Takeaways for CISOs](https://thehackernews.com/2026/03/the-state-of-secrets-sprawl-2026-9.html)**
*The Hacker News*
GitGuardian's annual report found 29 million new hardcoded secrets exposed in public GitHub repositories in 2025—a 34% year-over-year increase and the largest single-year jump ever recorded. The report identifies AI-generated code as an accelerating contributor to secrets sprawl and offers CISO-level guidance on containment strategies.
