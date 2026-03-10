# Security Digest — 2026-03-10

Active exploitation campaigns are hitting FortiGate firewalls, ASUS routers, and Salesforce cloud misconfigurations, while researchers publish a wave of work exposing new attack surfaces in AI agents, MCP-based systems, and multimodal LLMs.

---

## AI Security Research

**[How to Stop AI Data Leaks: A Webinar Guide to Auditing Modern Agentic Workflows](https://thehackernews.com/2026/03/how-to-stop-ai-data-leaks-webinar-guide.html)**
*The Hacker News*
AI agents that autonomously send emails, move data, and invoke tools open new exfiltration paths that traditional DLP tools weren't built to catch. The piece surveys audit approaches for agentic pipelines as enterprise adoption accelerates.

**[How to Steal Reasoning Without Reasoning Traces](https://arxiv.org/abs/2603.07267)**
*ArXiv cs.CR*
Researchers demonstrate that an adversary can extract a model's latent reasoning capabilities even when full chain-of-thought traces are withheld — only final answers and brief summaries are needed. The finding challenges the assumption that hiding reasoning traces is sufficient protection for proprietary reasoning models.

**[Give Them an Inch and They Will Take a Mile: Understanding and Measuring Caller Identity Confusion in MCP-Based AI Systems](https://arxiv.org/abs/2603.07473)**
*ArXiv cs.CR*
The Model Context Protocol (MCP) is increasingly adopted by AI agents for tool integration, but its trust model is systematically exploitable via caller identity confusion — allowing malicious MCP servers to impersonate legitimate callers. The paper quantifies the attack surface across real-world MCP deployments.

**[Governance Architecture for Autonomous Agent Systems: Threats, Framework, and Engineering Practice](https://arxiv.org/abs/2603.07191)**
*ArXiv cs.CR*
LLM-powered autonomous agents introduce execution-layer vulnerabilities — prompt injection, retrieval poisoning, uncontrolled tool invocation — that existing guardrails address only piecemeal. Authors propose a structured governance architecture with enforcement hooks at the agent runtime layer.

**[PolyJailbreak: Cross-Modal Jailbreaking Attacks on Black-Box Multimodal LLMs](https://arxiv.org/abs/2510.17277)**
*ArXiv cs.CR*
Despite alignment improvements, multimodal LLMs remain vulnerable to jailbreak attacks that exploit cross-modal inconsistencies between image and text processing pathways. PolyJailbreak achieves high success rates against black-box MLLMs without access to model internals.

**[Where Do LLM-based Systems Break? A System-Level Security Framework for Risk Assessment and Treatment](https://arxiv.org/abs/2603.07460)**
*ArXiv cs.CR*
Most LLM security analyses treat models in isolation, missing risks that emerge from system-level interactions with databases, APIs, and user interfaces. This work introduces a goal-driven risk assessment methodology that maps failure modes across the full LLM system stack.

**[Backdoor4Good: Benchmarking Beneficial Uses of Backdoors in LLMs](https://arxiv.org/abs/2603.07452)**
*ArXiv cs.CR*
Backdoor triggers — traditionally viewed as an attack vector — can also serve defensive purposes such as watermarking, ownership verification, and selective capability restriction. The paper presents the first benchmark for evaluating "constructive backdoor" mechanisms in large language models.

---

## Vulnerabilities & Exploits

**[FortiGate Devices Exploited to Breach Networks and Steal Service Account Credentials](https://thehackernews.com/2026/03/fortigate-devices-exploited-to-breach.html)**
*The Hacker News*
Threat actors are actively abusing FortiGate next-generation firewalls as network entry points, leveraging recently disclosed CVEs or weak credentials to pivot inward and harvest service account tokens. ESET researchers published fresh indicators of compromise tied to the campaign.

**[KadNap Malware Infects 14,000+ Edge Devices to Power Stealth Proxy Botnet](https://thehackernews.com/2026/03/kadnap-malware-infects-14000-edge.html)**
*The Hacker News*
KadNap, first spotted in August 2025, has spread to over 14,000 ASUS routers, enrolling them in a stealth residential proxy network used to route malicious traffic. More than 60% of victims are concentrated in a small number of countries, suggesting a targeted distribution strategy.

**[APT28 Uses BEARDSHELL and COVENANT Malware to Spy on Ukrainian Military](https://thehackernews.com/2026/03/apt28-uses-beardshell-and-covenant.html)**
*The Hacker News*
Russia's APT28 (Fancy Bear) has been running a long-term surveillance campaign against Ukrainian military personnel since April 2024 using two custom implants: BEARDSHELL for initial access and COVENANT for persistent C2. ESET's analysis details the command-and-control infrastructure and evasion techniques employed.

**[New "LeakyLooker" Flaws in Google Looker Studio Could Enable Cross-Tenant SQL Queries](https://thehackernews.com/2026/03/new-leakylooker-flaws-in-google-looker.html)**
*The Hacker News*
Nine cross-tenant vulnerabilities in Google Looker Studio would have allowed attackers to run arbitrary SQL against victims' Google Cloud databases and exfiltrate sensitive data. Google has since patched all nine; no evidence of in-the-wild exploitation was disclosed.

**[CISA Flags SolarWinds, Ivanti, and Workspace One Vulnerabilities as Actively Exploited](https://thehackernews.com/2026/03/cisa-flags-solarwinds-ivanti-and.html)**
*The Hacker News*
CISA added three CVEs to its Known Exploited Vulnerabilities catalog, including a server-side request forgery in SolarWinds (CVE-2021-22054, CVSS 7.5) and flaws in Ivanti and VMware Workspace One. Federal agencies face binding deadlines to patch; the flaws have all seen active exploitation in the wild.

**[Threat Actors Mass-Scan Salesforce Experience Cloud via Modified AuraInspector Tool](https://thehackernews.com/2026/03/threat-actors-mass-scan-salesforce.html)**
*The Hacker News*
Attackers are scanning publicly accessible Salesforce Experience Cloud sites at scale using a weaponized fork of the open-source AuraInspector browser extension to probe for overly permissive configurations. Salesforce warned customers to audit guest user access and restrict unauthenticated API exposure.

---

## Policy & Compliance

**[Jailbreaking the F-35 Fighter Jet](https://www.schneier.com/blog/archives/2026/03/jailbreaking-the-f-35-fighter-jet.html)**
*Schneier on Security*
The Dutch Defense Secretary publicly floated the idea of "jailbreaking" US-supplied F-35s to accept third-party software maintenance, exposing the geopolitical risk of critical defense systems locked to a single nation's update infrastructure. Schneier contextualizes this as a DRM and national-security-policy problem with broad implications for allied militaries dependent on US platforms.

**[The UK Cyber Security and Resilience Bill: A Practitioner's Guide to Legislative Reform, Compliance, and Organisational Readiness](https://arxiv.org/abs/2603.07861)**
*ArXiv cs.CR*
The UK's Cyber Security and Resilience Bill — introduced to Parliament in November 2025 and the most significant reform of UK cyber law in nearly a decade — expands NIS2-style obligations to a wider range of sectors and critical suppliers. This practitioner-focused analysis maps the compliance requirements and readiness steps for organizations operating under UK jurisdiction.
