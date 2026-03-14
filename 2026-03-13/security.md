# Security Digest — 2026-03-13

Active zero-day exploitation dominated today — Google patched two Chrome bugs already in the wild, while researchers disclosed nine root-escalation flaws in Linux AppArmor and seven critical Veeam RCE vulnerabilities. Law enforcement struck back with Operation Synergia III, sinkholing 45,000 malicious IPs across the globe.

---

## AI Security Research

**[Jailbreak Scaling Laws for Large Language Models: Polynomial-Exponential Crossover](https://arxiv.org/abs/2603.11331)**
*ArXiv cs.AI*
Adversarial prompt-injection attacks shift jailbreak success from slow polynomial growth to exponential growth, raising serious concerns about the scalability of current safety alignment as models and attack effort both increase.

**[Systematic Scaling Analysis of Jailbreak Attacks in Large Language Models](https://arxiv.org/abs/2603.11149)**
*ArXiv cs.LG*
A new scaling-law framework benchmarks how jailbreak success rates grow with attacker effort across model families and harm types, offering the first systematic analysis of the effort-to-success relationship across methods.

**[You Told Me to Do It: Measuring Instructional Text-induced Private Data Leakage in LLM Agents](https://arxiv.org/abs/2603.11862)**
*ArXiv cs.AI*
High-privilege LLM agents with terminal and filesystem access can be induced to leak private data through maliciously crafted project instructions, demonstrating a novel attack surface beyond conventional prompt injection.

**[The Mirror Design Pattern: Strict Data Geometry over Model Scale for Prompt Injection Detection](https://arxiv.org/abs/2603.11875)**
*ArXiv cs.AI*
Proposes a lightweight, geometry-based first-screening layer for prompt injection that runs on every request without the overhead of large neural detectors, prioritizing speed and reliability at the system boundary.

**[Cascade: Composing Software-Hardware Attack Gadgets for Adversarial Threat Amplification in Compound AI Systems](https://arxiv.org/abs/2603.12023)**
*ArXiv cs.AI*
Demonstrates how compound AI pipelines — chaining LLMs, software tools, and databases — inherit and amplify traditional software-hardware attack gadgets, creating a new class of compounding adversarial threat.

**[OpenClaw PRISM: A Zero-Fork, Defense-in-Depth Runtime Security Layer for Tool-Augmented LLM Agents](https://arxiv.org/abs/2603.11853)**
*ArXiv cs.CR*
A drop-in runtime security layer for tool-augmented LLM agents that detects indirect prompt injection via fetched content, unsafe tool calls, and credential leakage — all without requiring changes to the underlying agent codebase.

**[EmbTracker: Traceable Black-box Watermarking for Federated Language Models](https://arxiv.org/abs/2603.12089)**
*ArXiv cs.CR*
Addresses the risk of model leakage in federated LLM training by embedding traceable watermarks that identify which client leaked a model instance, even without white-box model access.

**[Hiding in Plain Sight: A Steganographic Approach to Stealthy LLM Jailbreaks](https://arxiv.org/abs/2505.16765)**
*ArXiv cs.AI*
Introduces steganographically encoded jailbreak prompts that bypass both the safety filters and the detection systems guarding LLMs, prioritizing stealthiness as the primary attack metric alongside effectiveness.

**[Patch Me If You Can: AI Codemods for Secure-by-Default Android Apps](https://engineering.fb.com/2026/03/13/android/ai-codemods-secure-by-default-android-apps-meta-tech-podcast/)**
*Engineering at Meta*
Meta describes using AI-driven automated code modification (codemods) to systematically migrate millions of lines of Android code to security-hardened APIs at scale, turning a manual security-review bottleneck into an automated pipeline.

---

## Vulnerabilities & Exploits

**[Google Fixes Two Chrome Zero-Days Exploited in the Wild Affecting Skia and V8](https://thehackernews.com/2026/03/google-fixes-two-chrome-zero-days.html)**
*The Hacker News*
CVE-2026-3909 (out-of-bounds write in Skia, CVSS 8.8) and a second V8 vulnerability are both confirmed exploited in the wild; users should update Chrome immediately.

**[Veeam Patches 7 Critical Backup & Replication Flaws Allowing Remote Code Execution](https://thehackernews.com/2026/03/veeam-patches-7-critical-backup.html)**
*The Hacker News*
Seven critical CVEs — including CVE-2026-21666 (CVSS 9.9), exploitable by authenticated users — allow full remote code execution against Veeam Backup & Replication; patch urgently given ransomware groups' history of targeting backup infrastructure.

**[Nine CrackArmor Flaws in Linux AppArmor Enable Root Escalation, Bypass Container Isolation](https://thehackernews.com/2026/03/nine-crackarmor-flaws-in-linux-apparmor.html)**
*The Hacker News*
Nine "confused deputy" vulnerabilities in the Linux kernel's AppArmor module let unprivileged users bypass mandatory access controls, escalate to root, and break container isolation guarantees in affected kernel versions.

**[Chinese Hackers Target Southeast Asian Militaries with AppleChris and MemFun Malware](https://thehackernews.com/2026/03/chinese-hackers-target-southeast-asian.html)**
*The Hacker News*
Palo Alto Unit 42 tracks threat cluster CL-STA-1087 — attributed to China — running a state-sponsored espionage campaign against Southeast Asian military organizations dating back to at least 2020, deploying custom malware families AppleChris and MemFun.

**[Storm-2561 Spreads Trojan VPN Clients via SEO Poisoning to Steal Credentials](https://thehackernews.com/2026/03/storm-2561-spreads-trojan-vpn-clients.html)**
*The Hacker News*
Microsoft tracks Storm-2561 using SEO poisoning to redirect searches for Ivanti, Cisco, and Fortinet VPN clients to malicious ZIP archives, harvesting corporate VPN credentials from unsuspecting enterprise users.

**[INTERPOL Dismantles 45,000 Malicious IPs, Arrests 94 in Global Cybercrime Crackdown](https://thehackernews.com/2026/03/interpol-dismantles-45000-malicious-ips.html)**
*The Hacker News*
Operation Synergia III sinkholed 45,000 IP addresses and servers linked to phishing, malware, and ransomware campaigns, resulting in 94 arrests across multiple countries in one of INTERPOL's largest coordinated cyber actions.

**[Authorities Disrupt SocksEscort Proxy Botnet Exploiting 369,000 IPs Across 163 Countries](https://thehackernews.com/2026/03/authorities-disrupt-socksescort-proxy.html)**
*The Hacker News*
A court-authorized takedown dismantled SocksEscort, a criminal proxy service that had enslaved hundreds of thousands of home and small-business routers into a botnet used to commit large-scale fraud.

**[Starbucks Discloses Data Breach Affecting Hundreds of Employees](https://www.bleepingcomputer.com/news/security/starbucks-discloses-data-breach-affecting-hundreds-of-employees/)**
*BleepingComputer*
Threat actors gained unauthorized access to Starbucks Partner Central accounts, exposing personally identifiable information for hundreds of the company's employees.

**[Real-Time Banking Trojan Strikes Brazil's Pix Users](https://www.darkreading.com/application-security/real-time-banking-trojan-strikes-brazils-pix-users)**
*Dark Reading*
A new banking Trojan campaign targeting Brazil's instant-payment Pix system combines automated malware with a real-time human operator who intervenes at the critical moment of a transaction to maximize theft.

**[FBI Seeks Victims of Steam Games Used to Spread Malware](https://www.bleepingcomputer.com/news/security/fbi-seeks-victims-of-steam-games-used-to-spread-malware/)**
*BleepingComputer*
The FBI is soliciting victim reports after eight malicious games were uploaded to Steam and used to distribute malware, as part of an active criminal investigation into the supply chain compromise of the gaming platform.

---

## Policy & Compliance

**[Meta to Shut Down Instagram End-to-End Encrypted Chat Support Starting May 2026](https://thehackernews.com/2026/03/meta-to-shut-down-instagram-end-to-end.html)**
*The Hacker News*
Meta will discontinue its optional end-to-end encrypted chat feature on Instagram after May 8, 2026, prompting privacy advocates to question the rollback of a key user protection.

**[Academia and the "AI Brain Drain"](https://www.schneier.com/blog/archives/2026/03/academia-and-the-ai-brain-drain.html)**
*Schneier on Security*
Bruce Schneier highlights how unprecedented industry AI spending — projected to hit $650B in 2026 — is draining academic AI talent at a rate that undermines independent security research and oversight of the technology.

**[The $32B Acquisition That One VC Is Calling the "Deal of the Decade"](https://techcrunch.com/video/the-32b-acquisition-that-one-vc-is-calling-the-deal-of-the-decade/)**
*TechCrunch AI*
Google's $32 billion acquisition of cybersecurity startup Wiz — the largest venture-backed acquisition in history — signals how central AI, cloud, and security spending have become, with major implications for the enterprise security market.

**[The Data Gap: Why Nonprofit Cyber Incidents Go Underreported](https://www.darkreading.com/threat-intelligence/data-gap-why-nonprofit-cyber-incidents-go-underreported)**
*Dark Reading*
Threat actors increasingly target nonprofits for their sensitive data and weak security postures, yet systemic underreporting leaves policymakers and defenders with an incomplete picture of the true threat landscape in this sector.
