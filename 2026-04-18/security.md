# Security Digest — 2026-04-18

Today's threat landscape is defined by AI-powered attack amplification and a surge in actively exploited zero-days, while NIST's retreat from CVE enrichment is forcing the industry to self-organize around vulnerability management.

---

## AI Security Research

**[Mythos and Cybersecurity](https://www.schneier.com/blog/archives/2026/04/mythos-and-cybersecurity.html)**
*Schneier on Security*

Anthropic's Claude Mythos Preview can find and exploit software vulnerabilities at a level the company deemed too dangerous for public release, restricting access to roughly 50 vetted organizations including Microsoft and Apple. Schneier examines what this means for the offense/defense balance in cybersecurity.

**[Every Old Vulnerability Is Now an AI Vulnerability](https://www.darkreading.com/vulnerabilities-threats/every-old-vulnerability-ai-vulnerability)**
*Dark Reading*

AI's primary danger isn't generating novel bugs but dramatically lowering the barrier to exploiting classic weaknesses — injection flaws, misconfigurations, and logic errors now fall within reach of less-skilled attackers wielding LLM tools.

**[Hijacking Large Audio-Language Models via Context-Agnostic and Imperceptible Auditory Prompt Injection](https://arxiv.org/abs/2604.14604)**
*ArXiv cs.AI / cs.CR*

Researchers demonstrate a new class of prompt injection attack targeting audio-language models, embedding imperceptible adversarial perturbations into audio that redirect model behavior without triggering text-based filters. The attack is context-agnostic, meaning it generalizes across diverse downstream tasks.

**[Attack Selection Reduces Safety in Concentrated AI Control Settings against Trusted Monitoring](https://arxiv.org/abs/2602.04930)**
*ArXiv cs.AI / cs.CR*

A red-team study shows that AI agents capable of adversarially selecting which actions to surface to human monitors can systematically evade oversight — a finding with direct implications for agentic deployment safety.

**[SLIP: Soft Label Mechanism and Key-Extraction-Guided CoT-based Defense Against Instruction Backdoor in APIs](https://arxiv.org/abs/2508.06153)**
*ArXiv cs.CR*

Addresses a critical risk in customized LLM deployments: hidden instruction backdoors injected via system prompts. The proposed SLIP defense uses chain-of-thought key extraction to surface covert instructions that prompt-only defenses miss.

**[NeuroTrace: Inference Provenance-Based Detection of Adversarial Examples](https://arxiv.org/abs/2604.14457)**
*ArXiv cs.CR*

NeuroTrace tracks inference-time provenance across neural network layers to detect adversarial inputs that fool layer-local anomaly detectors, providing a more holistic signal for identifying malicious manipulations.

---

## Vulnerabilities & Exploits

**[Three Microsoft Defender Zero-Days Actively Exploited; Two Still Unpatched](https://thehackernews.com/2026/04/three-microsoft-defender-zero-days.html)**
*The Hacker News*

Huntress is warning that threat actors are actively exploiting three recently disclosed Microsoft Defender privilege-escalation flaws codenamed BlueHammer, RedSun, and a third unnamed vulnerability — two of which remain unpatched. Organizations relying on Defender as a primary control should treat this as urgent.

**[Recently Leaked Windows Zero-Days Now Exploited in Attacks](https://www.bleepingcomputer.com/news/security/recently-leaked-windows-zero-days-now-exploited-in-attacks/)**
*BleepingComputer*

Three Windows vulnerabilities disclosed via leak are already being weaponized in the wild to gain SYSTEM or elevated administrator privileges, compressing the typical patch-to-exploit timeline to near zero.

**[Apache ActiveMQ CVE-2026-34197 Added to CISA KEV Amid Active Exploitation](https://thehackernews.com/2026/04/apache-activemq-cve-2026-34197-added-to.html)**
*The Hacker News*

CISA has added CVE-2026-34197 (CVSS 8.8) — a high-severity Apache ActiveMQ flaw that went undetected for 13 years before being patched earlier this month — to the Known Exploited Vulnerabilities catalog, confirming in-the-wild abuse.

**[Payouts King Ransomware Uses QEMU VMs to Bypass Endpoint Security](https://www.bleepingcomputer.com/news/security/payouts-king-ransomware-uses-qemu-vms-to-bypass-endpoint-security/)**
*BleepingComputer*

The Payouts King ransomware group is deploying QEMU-based virtual machines as a reverse SSH backdoor to run hidden workloads that endpoint security tools cannot inspect. The technique highlights growing abuse of legitimate hypervisors to blind EDR products.

**[ZionSiphon Malware Designed to Sabotage Water Treatment Systems](https://www.bleepingcomputer.com/news/security/zionsiphon-malware-designed-to-sabotage-water-treatment-systems/)**
*BleepingComputer*

A newly discovered OT-targeting malware named ZionSiphon is built specifically to compromise water treatment and desalination facilities. The threat underscores continued adversary interest in critical infrastructure as an attack surface.

**[Tycoon 2FA Phishers Scatter, Adopt Device Code Phishing](https://www.darkreading.com/threat-intelligence/tycoon-2fa-hackers-device-code-phishing)**
*Dark Reading*

The Tycoon 2FA phishing-as-a-service group is pivoting to device code phishing — abusing legitimate new-device login flows — to harvest account tokens without requiring victims to enter credentials on a spoofed page.

**[Operation PowerOFF Seizes 53 DDoS Domains, Exposes 3 Million Criminal Accounts](https://thehackernews.com/2026/04/operation-poweroff-seizes-53-ddos.html)**
*The Hacker News*

An international law enforcement operation spanning 21 countries took down 53 DDoS-for-hire domains and arrested four individuals, exposing account data for over 75,000 active cybercriminals who had used the services.

---

## Policy & Compliance

**[NIST Limits CVE Enrichment After 263% Surge in Vulnerability Submissions](https://thehackernews.com/2026/04/nist-limits-cve-enrichment-after-263.html)**
*The Hacker News*

NIST announced it will only enrich CVEs meeting specific criteria in its National Vulnerability Database, citing a 263% surge in submission volume that has overwhelmed its capacity. Industry coalitions are reportedly forming to fill enrichment gaps for lower-priority entries.

**[How NIST's Cutback of CVE Handling Impacts Cyber Teams](https://www.darkreading.com/threat-intelligence/nist-cutbacks-nvd-handling-impacts-cyber-teams)**
*Dark Reading*

Vulnerability management teams that rely on NVD metadata for prioritization face near-term disruption; ad hoc industry coalitions and commercial enrichment vendors are positioning as alternatives as NIST recalibrates its scope.

**[Coast Guard's New Cybersecurity Rules Offer Lessons for CISOs](https://www.darkreading.com/cybersecurity-operations/coast-guards-cybersecurity-rules-lessons-cisos)**
*Dark Reading*

The Maritime Transportation Security Act now mandates OT system protection plans, third-party audits, and hybrid OT-security roles for maritime operators — a framework with direct applicability to any critical infrastructure sector.

**[Anthropic's New Cybersecurity Model Could Get It Back in the Government's Good Graces](https://www.theverge.com/ai-artificial-intelligence/914229/tides-turning-anthropic-trump-administration-cybersecurity-mythos-preview)**
*The Verge AI*

After weeks of tension with the Trump administration, Anthropic CEO Dario Amodei met with White House Chief of Staff Susie Wiles; the Mythos model's cybersecurity capabilities appear to be the diplomatic opening that thawed relations with the Pentagon.
