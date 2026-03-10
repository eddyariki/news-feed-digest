# Security Digest — 2026-03-10

Microsoft's March Patch Tuesday dominates the threat landscape with 79 flaws and 2 actively exploited zero-days, while Russian APT28 resurfaces with new sophisticated implants and AI safety researchers probe the robustness of LLM reward models and alignment mechanisms.

---

## AI Security Research

**[Improving Instruction Hierarchy in Frontier LLMs](https://openai.com/index/instruction-hierarchy-challenge)**
*OpenAI Blog*

OpenAI's IH-Challenge trains models to prioritize trusted instructions over untrusted ones, improving safety steerability and resistance to prompt injection attacks — a key hardening step as agentic AI systems gain wider deployment.

**[Reward Under Attack: Analyzing the Robustness and Hackability of Process Reward Models](https://arxiv.org/abs/2603.06621)**
*arXiv cs.CR*

Researchers demonstrate that state-of-the-art Process Reward Models (PRMs) — now the backbone of LLM reasoning pipelines — are systematically vulnerable to adversarial manipulation, raising concerns about the reliability of RLHF-trained reasoning systems.

**[Safe Transformer: An Explicit Safety Bit For Interpretable And Controllable Alignment](https://arxiv.org/abs/2603.06727)**
*arXiv cs.CR*

This paper proposes encoding safety as an explicit, inspectable bit within transformer architectures rather than embedding it implicitly in weights, enabling auditable and controllable alignment at inference time.

**[FuzzingRL: Reinforcement Fuzz-Testing for Revealing VLM Failures](https://arxiv.org/abs/2603.06600)**
*arXiv cs.CR*

A reinforcement learning-driven fuzzing framework systematically exposes failure modes in Vision Language Models, providing a structured methodology for stress-testing multimodal AI before deployment.

**[Jailbreaking the F-35 Fighter Jet](https://www.schneier.com/blog/archives/2026/03/jailbreaking-the-f-35-fighter-jet.html)**
*Schneier on Security*

Bruce Schneier examines how nations dependent on US-supplied F-35s face software lock-in and the geopolitical implications of "jailbreaking" military hardware — a real-world parallel to AI jailbreak concerns around control and sovereignty.

**[How to Stop AI Data Leaks: A Webinar Guide to Auditing Modern Agentic Workflows](https://thehackernews.com/2026/03/how-to-stop-ai-data-leaks-webinar-guide.html)**
*The Hacker News*

As AI agents take autonomous actions — sending email, moving data, managing software — organizations are advised to audit agentic workflows for data exfiltration risks, with practical guidance on least-privilege and monitoring strategies.

---

## Vulnerabilities & Exploits

**[Microsoft March 2026 Patch Tuesday Fixes 2 Zero-Days, 79 Flaws](https://www.bleepingcomputer.com/news/microsoft/microsoft-march-2026-patch-tuesday-fixes-2-zero-days-79-flaws/)**
*BleepingComputer*

Microsoft's March update addresses 79 CVEs including two publicly disclosed zero-days; companion updates KB5078885 (Windows 10) and KB5079473/KB5078883 (Windows 11) are available immediately for managed and consumer devices.

**[APT28 Uses BEARDSHELL and COVENANT Malware to Spy on Ukrainian Military](https://thehackernews.com/2026/03/apt28-uses-beardshell-and-covenant.html)**
*The Hacker News*

Russia's APT28 (Sednit/Fancy Bear) is deploying a custom variant of the Covenant post-exploitation framework alongside a new BEARDSHELL implant for long-term surveillance of Ukrainian military personnel, signaling a return to sophisticated tooling after years of simpler implants.

**[New 'Zombie ZIP' Technique Lets Malware Slip Past Security Tools](https://www.bleepingcomputer.com/news/security/new-zombie-zip-technique-lets-malware-slip-past-security-tools/)**
*BleepingComputer*

Researchers detail "Zombie ZIP," a method of crafting malformed ZIP archives that bypass antivirus and EDR detection by exploiting inconsistencies in how security tools and OS unpackers parse compressed files.

**[KadNap Malware Infects 14,000+ Edge Devices to Power Stealth Proxy Botnet](https://thehackernews.com/2026/03/kadnap-malware-infects-14000-edge.html)**
*The Hacker News*

A newly discovered malware campaign targeting ASUS routers and edge networking devices has enlisted over 14,000 hosts into a proxy botnet used to launder malicious traffic — with infections first observed earlier this year.

**[New "LeakyLooker" Flaws in Google Looker Studio Could Enable Cross-Tenant SQL Queries](https://thehackernews.com/2026/03/new-leakylooker-flaws-in-google-looker.html)**
*The Hacker News*

Nine cross-tenant vulnerabilities in Google Looker Studio would have allowed attackers to execute arbitrary SQL against victims' databases and exfiltrate sensitive data; Google has since patched the issues.

**[FortiGate Devices Exploited to Breach Networks and Steal Service Account Credentials](https://thehackernews.com/2026/03/fortigate-devices-exploited-to-breach.html)**
*The Hacker News*

Threat actors are actively abusing FortiGate NGFW appliances as entry points to pivot into corporate networks, targeting service account credentials for lateral movement post-compromise.

**[Microsoft Teams Phishing Targets Employees with A0Backdoor Malware](https://www.bleepingcomputer.com/news/security/microsoft-teams-phishing-targets-employees-with-backdoors/)**
*BleepingComputer*

Attackers posing as IT support over Microsoft Teams tricked employees at financial and healthcare organizations into granting remote access via Quick Assist, then deployed a new backdoor called A0Backdoor for persistent access.

---

## Policy & Compliance

**[CISA Flags SolarWinds, Ivanti, and Workspace One Vulnerabilities as Actively Exploited](https://thehackernews.com/2026/03/cisa-flags-solarwinds-ivanti-and.html)**
*The Hacker News*

CISA added three security flaws to its Known Exploited Vulnerabilities catalog — covering SolarWinds, Ivanti, and VMware Workspace One — based on confirmed active exploitation, triggering mandatory federal remediation timelines.

**[CISA: Recently Patched Ivanti EPM Flaw Now Actively Exploited](https://www.bleepingcomputer.com/news/security/cisa-recently-patched-ivanti-epm-flaw-now-actively-exploited/)**
*BleepingComputer*

A high-severity vulnerability in Ivanti Endpoint Manager that was patched only recently has already been weaponized in the wild; CISA has ordered US federal agencies to remediate within three weeks under the KEV directive.
