# Security Digest — 2026-03-13

A heavy patch day dominates today's threat landscape: two Chrome zero-days actively exploited in the wild, nine Linux kernel privilege-escalation flaws, and seven critical Veeam RCE vulnerabilities — while researchers publish new findings on jailbreak scaling laws and LLM agent prompt-injection defenses.

---

## AI Security Research

**[Jailbreak Scaling Laws for Large Language Models: Polynomial-Exponential Crossover](https://arxiv.org/abs/2603.11331)**
*ArXiv cs.LG / cs.AI*
Researchers find adversarial prompt-injection attacks against safety-aligned LLMs exhibit a polynomial-to-exponential scaling crossover as attack budget grows, offering the first systematic characterization of how jailbreak success rates scale with attacker resources.

**[Systematic Scaling Analysis of Jailbreak Attacks in Large Language Models](https://arxiv.org/abs/2603.11149)**
*ArXiv cs.LG / cs.CR*
A complementary scaling study covering how jailbreak success varies with attacker compute, model size, and defense strength — revealing structural vulnerabilities that persist across model families.

**[You Told Me to Do It: Measuring Instructional Text-induced Private Data Leakage in LLM Agents](https://arxiv.org/abs/2603.11862)**
*ArXiv cs.CR / cs.AI*
High-privilege LLM agents that autonomously process external documentation can be manipulated through malicious instructions embedded in those documents, causing them to exfiltrate private user data — a measurement study that quantifies this leakage risk at scale.

**[OpenClaw PRISM: A Zero-Fork, Defense-in-Depth Runtime Security Layer for Tool-Augmented LLM Agents](https://arxiv.org/abs/2603.11853)**
*ArXiv cs.CR*
Proposes a runtime security layer for tool-using LLM agents that intercepts indirect prompt injection through fetched content, enforcing least-privilege tool invocations without modifying the underlying model or requiring access to model weights.

**[Hiding in Plain Sight: A Steganographic Approach to Stealthy LLM Jailbreaks](https://arxiv.org/abs/2505.16765)**
*ArXiv cs.CR / cs.AI*
Introduces a jailbreak method that embeds harmful instructions via steganography, evading both semantic detectors and human reviewers — demonstrating that purely syntactic safety filtering is insufficient.

**[EmbTracker: Traceable Black-box Watermarking for Federated Language Models](https://arxiv.org/abs/2603.12089)**
*ArXiv cs.CR*
Federated LM training exposes every participant's updates to potential IP theft; EmbTracker proposes a black-box watermarking scheme that enables model provenance tracking without requiring white-box access.

**[CLASP: Defending Hybrid Large Language Models Against Hidden State Poisoning Attacks](https://arxiv.org/abs/2603.12206)**
*ArXiv cs.CL*
State space models like Mamba are increasingly used alongside Transformers for efficiency, but their hidden states introduce a new poisoning attack vector; CLASP provides targeted defenses for these hybrid architectures.

**[The Mirror Design Pattern: Strict Data Geometry over Model Scale for Prompt Injection Defense](https://arxiv.org/abs/2603.11875)**
*ArXiv cs.CR / cs.AI*
Challenges the assumption that larger semantic detectors are the right tool for prompt injection defense, instead proposing structural data-geometry constraints that block injection at near-zero compute cost.

---

## Vulnerabilities & Exploits

**[Google Fixes Two Chrome Zero-Days Exploited in the Wild Affecting Skia and V8](https://thehackernews.com/2026/03/google-fixes-two-chrome-zero-days.html)**
*The Hacker News*
Google patched CVE-2026-3909 (CVSS 8.8, out-of-bounds write in the Skia 2D graphics library) and a second high-severity V8 flaw, both confirmed exploited in the wild; users should update Chrome immediately.

**[Nine CrackArmor Flaws in Linux AppArmor Enable Root Escalation, Bypass Container Isolation](https://thehackernews.com/2026/03/nine-crackarmor-flaws-in-linux-apparmor.html)**
*The Hacker News*
Qualys Threat Research disclosed nine "confused deputy" vulnerabilities in the Linux kernel's AppArmor module that allow unprivileged users to escalate to root and break out of container isolation — collectively dubbed CrackArmor.

**[Veeam Patches 7 Critical Backup & Replication Flaws Allowing Remote Code Execution](https://thehackernews.com/2026/03/veeam-patches-7-critical-backup.html)**
*The Hacker News*
Veeam released urgent patches for seven critical RCE flaws including CVE-2026-21666 (CVSS 9.9), which allows any authenticated domain user to execute code on the Backup Server — a high-value target in ransomware intrusions.

**[Supply Chain Attack Using Invisible Unicode Code Hits GitHub and Other Repositories](https://arstechnica.com/security/2026/03/supply-chain-attack-using-invisible-code-hits-github-and-other-repositories/)**
*Ars Technica*
Attackers are hiding malicious logic inside source repositories using invisible Unicode characters, exploiting the gap between what developers see in editors and what the compiler actually processes — a technique now appearing in real supply chain attacks.

**[Storm-2561 Spreads Trojan VPN Clients via SEO Poisoning to Steal Credentials](https://thehackernews.com/2026/03/storm-2561-spreads-trojan-vpn-clients.html)**
*The Hacker News*
Microsoft disclosed a credential-theft campaign in which threat actor Storm-2561 distributes convincing fake VPN installers for Ivanti, Cisco, and Fortinet products via SEO-poisoned search results, targeting enterprise VPN credentials.

**[Chinese Hackers Target Southeast Asian Militaries with AppleChris and MemFun Malware](https://thehackernews.com/2026/03/chinese-hackers-target-southeast-asian.html)**
*The Hacker News*
A suspected Chinese state-sponsored group has conducted cyber-espionage against Southeast Asian military organizations since at least 2020, deploying custom implants including AppleChris and MemFun, per Palo Alto Networks Unit 42.

**[INTERPOL Dismantles 45,000 Malicious IPs, Arrests 94 in Global Cybercrime Crackdown](https://thehackernews.com/2026/03/interpol-dismantles-45000-malicious-ips.html)**
*The Hacker News*
Operation Synergia III sinkholed 45,000 IP addresses and servers tied to phishing, malware, and ransomware campaigns, with 94 arrests across multiple continents — one of INTERPOL's largest coordinated cyber operations to date.

**[Authorities Disrupt SocksEscort Proxy Botnet Exploiting 369,000 IPs Across 163 Countries](https://thehackernews.com/2026/03/authorities-disrupt-socksescort-proxy.html)**
*The Hacker News*
A court-authorized international operation dismantled SocksEscort, a criminal proxy service that conscripted hundreds of thousands of residential routers into a botnet used to anonymize cybercrime traffic globally.

**[Starbucks Discloses Data Breach Affecting Hundreds of Employees](https://www.bleepingcomputer.com/news/security/starbucks-discloses-data-breach-affecting-hundreds-of-employees/)**
*BleepingComputer*
Threat actors gained access to Starbucks Partner Central accounts, exposing employee data; the company has not disclosed how credentials were initially compromised.

**[Canadian Retail Giant Loblaw Notifies Customers of Data Breach](https://www.bleepingcomputer.com/news/security/canadian-retail-giant-loblaw-notifies-customers-of-data-breach/)**
*BleepingComputer*
Loblaw has begun notifying customers of a breach and logged out all affected accounts as a precaution, though full details of the incident scope remain under investigation.

**[FBI Seeks Victims of Steam Games Used to Spread Malware](https://www.bleepingcomputer.com/news/security/fbi-seeks-victims-of-steam-games-used-to-spread-malware/)**
*BleepingComputer*
The FBI is soliciting victims who installed eight malware-laced games distributed through Steam, as part of an active criminal investigation into the campaign operators.

**[Fake PoCs and Misunderstood Risks Cause Cisco SD-WAN Chaos](https://www.darkreading.com/vulnerabilities-threats/fake-pocs-risks-cisco-sd-wan)**
*Dark Reading*
Circulating fake proof-of-concept exploits for recent Cisco SD-WAN vulnerabilities have created confusion about actual exposure, with defenders wasting effort on non-functional PoCs while overlooking real attack paths.

**[Most Google Cloud Attacks Start With Bug Exploitation](https://www.darkreading.com/cloud-security/google-cloud-attacks-bug-exploitation)**
*Dark Reading*
AI-assisted exploit development is outpacing patching cycles, making vulnerability exploitation — not credential theft or misconfiguration — the leading initial access vector for cloud compromises, according to Google Cloud's latest threat report.

**[Real-Time Banking Trojan Strikes Brazil's Pix Users](https://www.darkreading.com/application-security/real-time-banking-trojan-strikes-brazils-pix-users)**
*Dark Reading*
A new banking Trojan campaign targeting Brazil's instant payment platform Pix pairs automated malware with a live human operator who intervenes at the moment of transaction to maximize theft success rates.

---

## Policy & Compliance

**[Meta to Shut Down Instagram End-to-End Encrypted Chat Support Starting May 2026](https://thehackernews.com/2026/03/meta-to-shut-down-instagram-end-to-end.html)**
*The Hacker News*
Meta will discontinue end-to-end encryption support for Instagram DMs after May 8, 2026, affecting users who rely on E2EE for private messaging and raising questions about the long-term trajectory of privacy features across its platforms.

**[Patch Me If You Can: AI Codemods for Secure-by-Default Android Apps](https://engineering.fb.com/2026/03/13/android/ai-codemods-secure-by-default-android-apps-meta-tech-podcast/)**
*Engineering at Meta*
Meta describes using AI-driven codemods to automatically migrate millions of lines of Android code to secure-by-default APIs at scale — a practical model for how large organizations can enforce security standards without manual remediation.
