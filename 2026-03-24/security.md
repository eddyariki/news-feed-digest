# Security Digest — 2026-03-24

A coordinated wiper/supply-chain campaign (TeamPCP/CanisterWorm) dominates the threat landscape, targeting Kubernetes clusters and developer tooling, while new academic work exposes a fundamental safety-capability trade-off in LLM agents and a novel Chrome credential-theft technique surfaces.

---

## AI Security Research

**[We Found Eight Attack Vectors Inside AWS Bedrock](https://thehackernews.com/2026/03/we-found-eight-attack-vectors-inside.html)**
*The Hacker News*
Researchers catalogued eight attack vectors against AWS Bedrock's AI platform, exploiting the model's ability to directly query Salesforce, trigger Lambda functions, and pull from SharePoint. The deep connectivity that makes Bedrock powerful also makes it a high-value target for lateral movement.

**[The Autonomy Tax: Defense Training Breaks LLM Agents](https://arxiv.org/abs/2603.19423)**
*ArXiv cs.CR / cs.AI*
Defense-trained models designed to resist prompt injection attacks introduce a fundamental capability-alignment paradox: the same hardening that blocks malicious instructions also impairs the agent's ability to follow legitimate multi-step tool calls. The paper frames this as an unavoidable "autonomy tax" in current defense architectures.

**[The Verifier Tax: Horizon Dependent Safety Success Tradeoffs in Tool Using LLM Agents](https://arxiv.org/abs/2603.19328)**
*ArXiv cs.CR*
Runtime policy enforcement against unsafe actions reduces end-to-end task completion in tool-using LLM agents, with the performance hit scaling with task horizon length (15–30 turns). Results vary by model family, suggesting no one-size-fits-all safety architecture for agentic systems.

**[LSR: Linguistic Safety Robustness Benchmark for Low-Resource West African Languages](https://arxiv.org/abs/2603.19273)**
*ArXiv cs.CR / cs.AI*
Safety alignment trained predominantly on English-language data frequently fails to activate refusal mechanisms when harmful intent is expressed in Yoruba, Hausa, Igbo, and Igala. The LSR benchmark is the first systematic measure of cross-lingual refusal degradation in low-resource African languages.

**[The Phish, The Spam, and The Valid: Generating Feature-Rich Emails for Benchmarking LLMs](https://arxiv.org/abs/2511.21448)**
*ArXiv cs.CR / cs.AI*
PhishFuzzer seeds real emails into LLMs to produce 23,100 diverse variants across controlled dimensions, enabling rigorous three-class (phishing/spam/valid) benchmarking of detection models. The dataset includes full URL and attachment metadata plus attacker intent annotations, addressing gaps in existing corpora.

---

## Vulnerabilities & Exploits

**['CanisterWorm' Springs Wiper Attack Targeting Iran](https://krebsonsecurity.com/2026/03/canisterworm-springs-wiper-attack-targeting-iran/)**
*Krebs on Security*
A financially motivated group is deploying CanisterWorm, a self-propagating worm that spreads through poorly secured cloud services and wipes all data on systems configured for Iran's time zone or Farsi locale. The campaign exploits Aqua Security's Trivy scanner supply chain, pushing malicious Docker images (versions 0.69.4–0.69.6) and hijacking the company's GitHub organization to tamper with dozens of repositories.

**[Trivy supply-chain attack spreads to Docker, GitHub repos](https://www.bleepingcomputer.com/news/security/trivy-supply-chain-attack-spreads-to-docker-github-repos/)**
*BleepingComputer*
TeamPCP continued to widen the Trivy supply-chain attack blast radius by contaminating Docker Hub images and gaining write access to Aqua Security's GitHub org. The last known clean Trivy release on Docker Hub is 0.69.3; malicious tags have since been removed.

**[North Korean Hackers Abuse VS Code Auto-Run Tasks to Deploy StoatWaffle Malware](https://thehackernews.com/2026/03/north-korean-hackers-abuse-vs-code-auto.html)**
*The Hacker News*
The Contagious Interview / WaterPlum campaign (North Korea) began abusing VS Code `tasks.json` auto-run features in December 2025 to silently deploy the StoatWaffle malware family via malicious project repositories. The technique requires no user interaction beyond opening a project.

**[CISA orders feds to patch DarkSword iOS flaws exploited attacks](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-darksword-ios-flaws-exploited-attacks/)**
*BleepingComputer*
CISA issued an emergency directive mandating federal agencies patch three iOS vulnerabilities being actively exploited via the DarkSword exploit kit, which has been linked to both cryptocurrency theft and nation-state cyberespionage. The directive sets a tight remediation window given active exploitation in the wild.

**[Hackers Exploit CVE-2025-32975 (CVSS 10.0) to Hijack Unpatched Quest KACE SMA Systems](https://thehackernews.com/2026/03/hackers-exploit-cve-2025-32975-cvss-100.html)**
*The Hacker News*
Arctic Wolf observed active exploitation of CVE-2025-32975, a maximum-severity flaw in Quest KACE Systems Management Appliance, beginning the week of March 9 against internet-exposed unpatched devices. The vulnerability allows full system takeover with no authentication.

**[VoidStealer malware steals Chrome master key via debugger trick](https://www.bleepingcomputer.com/news/security/voidstealer-malware-steals-chrome-master-key-via-debugger-trick/)**
*BleepingComputer*
VoidStealer employs a novel debugger-based technique to bypass Chrome's Application-Bound Encryption (ABE) and extract the master key used to decrypt stored credentials and payment data. The approach sidesteps the memory-scraping methods ABE was designed to block.

**[Microsoft Warns IRS Phishing Hits 29,000 Users, Deploys RMM Malware](https://thehackernews.com/2026/03/microsoft-warns-irs-phishing-hits-29000.html)**
*The Hacker News*
Tax-season phishing campaigns are impersonating IRS refund notices and payroll forms to harvest credentials and drop remote monitoring and management (RMM) malware, giving attackers persistent remote access under the guise of legitimate software. Microsoft observed 29,000 users targeted in recent waves.

**[Crunchyroll probes breach after hacker claims to steal 6.8M users' data](https://www.bleepingcomputer.com/news/security/crunchyroll-probes-breach-after-hacker-claims-to-steal-68m-users-data/)**
*BleepingComputer*
Anime streaming platform Crunchyroll is investigating a reported breach after a threat actor claimed to have exfiltrated personal information for approximately 6.8 million users. The company has not confirmed the scope or authenticity of the claim as the investigation continues.

**[FBI warns of Handala hackers using Telegram in malware attacks](https://www.bleepingcomputer.com/news/security/fbi-warns-of-handala-hackers-using-telegram-in-malware-attacks/)**
*BleepingComputer*
The FBI warned that Iranian hackers tied to the Ministry of Intelligence and Security (MOIS), tracked as Handala, are using Telegram as a command-and-control channel to distribute malware. The campaign marks an escalation in Iranian cyber activity during the ongoing regional conflict.
