# Security Digest — 2026-04-23

A dense threat landscape today: Anthropic's restricted Mythos cybersecurity model reached unauthorized users, twin supply chain worms hit npm and Docker Hub, Microsoft rushed emergency patches for a CVSS 9.1 ASP.NET flaw, and ArXiv overflowed with research on agentic AI attack surfaces and LLM jailbreak techniques.

---

## AI Security Research

**[Anthropic's Most Dangerous AI Model Just Fell Into the Wrong Hands](https://www.theverge.com/ai-artificial-intelligence/916501/anthropic-mythos-unauthorized-users-access-security)**
*The Verge AI*
Anthropic's Mythos AI model — a powerful cybersecurity tool described as dangerous in the wrong hands — was accessed by a "small group of unauthorized users" including a third-party contractor who shared access to a private online forum. The incident highlights the challenge of restricting dual-use AI security capabilities even in controlled preview programs.

**[Cohere AI Terrarium Sandbox Flaw Enables Root Code Execution, Container Escape](https://thehackernews.com/2026/04/cohere-ai-terrarium-sandbox-flaw.html)**
*The Hacker News*
CVE-2026-5752 (CVSS 9.3) allows sandbox escape and arbitrary code execution with root privileges via JavaScript prototype chain traversal in Cohere's Python-based Terrarium execution environment. The critical severity underscores the difficulty of safely sandboxing LLM code-execution capabilities.

**[Involuntary In-Context Learning: Exploiting Few-Shot Pattern Completion to Bypass Safety Alignment in GPT-5.4](https://arxiv.org/abs/2604.19461)**
*ArXiv cs.CR*
Researchers introduce IICL, an attack class that uses abstract operator framing with few-shot examples to force pattern completion that overrides safety training, probing 10 OpenAI models across 3,479 trials. The findings show that sufficiently strong in-context patterns can reliably compete with and override learned refusal behaviors.

**[Temporal UI State Inconsistency in Desktop GUI Agents: Formalizing and Defending Against TOCTOU Attacks](https://arxiv.org/abs/2604.18860)**
*ArXiv cs.AI*
GUI agents that control desktops via screenshot-and-click loops have a mean 6.51-second observation-to-action gap that creates a TOCTOU window; the paper formalizes three concrete attack primitives — Notification Overlay Hijack, Window Focus Steal, and UI Element Replacement — and proposes defenses. This is among the first formal treatments of timing-based attacks on computer-use agents.

**[Whispers in the Machine: Confidentiality in Agentic Systems](https://arxiv.org/abs/2402.06922)**
*ArXiv cs.LG*
Updated analysis of how prompt injection attacks escalate in severity in agentic settings, where malicious instructions embedded in connected services can misdirect LLM agents with access to email, calendars, and code execution. The paper maps the new attack surface and proposes a confidentiality framework for multi-tool agent architectures.

**[Do Agents Dream of Root Shells? Partial-Credit Evaluation of LLM Agents in Capture The Flag Challenges](https://arxiv.org/abs/2604.19354)**
*ArXiv cs.AI*
DeepRed is an open-source benchmark placing LLM agents in isolated Kali attacker environments against realistic CTF challenges, with partial-credit scoring to measure progress short of full exploitation. Results reveal that current frontier models show meaningful but incomplete offensive capability in realistic isolated environments.

**[Towards Optimal Agentic Architectures for Offensive Security Tasks](https://arxiv.org/abs/2604.18718)**
*ArXiv cs.AI*
A controlled benchmark of 20 interactive targets (web/API and binary) measures when multi-agent topologies outperform single-agent setups for offensive security, finding that topology choice has significant empirical impact on both capability and cost. The study treats agent coordination as an empirical systems question rather than a design assumption.

**[Harmful Intent as a Geometrically Recoverable Feature of LLM Residual Streams](https://arxiv.org/abs/2604.18901)**
*ArXiv cs.AI*
Across 12 models spanning Qwen2.5, Qwen3.5, Llama-3.2, and Gemma-3 in base, instruction-tuned, and abliterated variants, harmful intent is linearly recoverable from residual streams in most layers. This geometric characterization has direct implications for both detection and steering-based safety interventions.

**[Dual-Guard: Dual-Channel Latent Watermarking for Provenance and Tamper Localization in Diffusion Images](https://arxiv.org/abs/2604.19090)**
*ArXiv cs.CR*
Dual-Guard embeds provenance and integrity watermarks in dual latent channels of diffusion models, surviving regeneration attacks and enabling spatial localization of tampered regions. Existing single-domain methods fail under black-box reprompting; Dual-Guard addresses both attribution and tamper detection in a unified framework.

**[An Empirical Study of Multi-Generation Sampling for Jailbreak Detection in Large Language Models](https://arxiv.org/abs/2604.18775)**
*ArXiv cs.LG*
Under realistic conditions using JailbreakBench, generation inconsistency-based detectors outperform lexical TF-IDF approaches for identifying jailbreak behavior, particularly against strongly aligned models where harmful outputs appear only rarely. The study provides empirical baselines for output-based detection that are independent of model internals.

**[An AI Agent Execution Environment to Safeguard User Data](https://arxiv.org/abs/2604.19657)**
*ArXiv cs.AI*
Proposes an isolated execution environment for AI agents that prevents prompt injection from exfiltrating private user data by enforcing data-flow policies between agent actions and external outputs. The architecture separates the agent's reasoning context from privileged user data stores, limiting blast radius when the agent model is compromised.

---

## Vulnerabilities & Exploits

**[Microsoft Patches Critical ASP.NET Core CVE-2026-40372 Privilege Escalation Bug](https://thehackernews.com/2026/04/microsoft-patches-critical-aspnet-core.html)**
*The Hacker News*
An out-of-band emergency patch addresses improper verification of cryptographic signatures in ASP.NET Core, carrying a CVSS score of 9.1 and rated Important severity. Administrators should apply the update immediately as it enables unauthenticated privilege escalation.

**[Malicious KICS Docker Images and VS Code Extensions Hit Checkmarx Supply Chain](https://thehackernews.com/2026/04/malicious-kics-docker-images-and-vs.html)**
*The Hacker News*
Threat actors overwrote existing tags on the official `checkmarx/kics` Docker Hub repository (including v2.1.20 and alpine) and injected a new v2.1.21 tag not corresponding to any official release. The attack illustrates how popular DevSecOps tooling repositories can be leveraged as high-trust supply chain vectors.

**[Self-Propagating Supply Chain Worm Hijacks npm Packages to Steal Developer Tokens](https://thehackernews.com/2026/04/self-propagating-supply-chain-worm.html)**
*The Hacker News*
Tracked as CanisterSprawl by Socket and StepSecurity, a worm spreads through stolen npm tokens and exfiltrates stolen data to an ICP canister, self-propagating by publishing malicious versions from compromised developer accounts. This is a significant escalation: the worm doesn't just compromise one package — it actively reproduces through the npm ecosystem.

**[New Mirai Campaign Exploits RCE Flaw in EoL D-Link Routers](https://www.bleepingcomputer.com/news/security/new-mirai-campaign-exploits-rce-flaw-in-eol-d-link-routers/)**
*BleepingComputer*
CVE-2025-29635, a high-severity command-injection vulnerability in D-Link DIR-823X routers (now end-of-life), is being actively exploited by a new Mirai-based botnet campaign. No patches will be issued for affected devices; the only mitigation is replacement.

**[Kyber Ransomware Gang Toys with Post-Quantum Encryption on Windows](https://www.bleepingcomputer.com/news/security/kyber-ransomware-gang-toys-with-post-quantum-encryption-on-windows/)**
*BleepingComputer*
A new ransomware operation targeting Windows and VMware ESXi is experimenting with Kyber1024 post-quantum encryption in one variant, making key recovery potentially infeasible even if classical decryption keys are obtained. This marks one of the first observed deployments of PQC algorithms in live ransomware operations.

**['The Gentlemen' Rapidly Rises to Ransomware Prominence](https://www.darkreading.com/threat-intelligence/gentlemen-rapidly-rise-ransomware)**
*Dark Reading*
A new ransomware gang has impressed researchers with the speed of its operational scaling and technical sophistication, quickly establishing itself as a notable threat actor. The group's rapid ramp-up suggests either experienced operators or a well-funded new entrant to the ransomware-as-a-service ecosystem.

**[Harvester Deploys Linux GoGra Backdoor in South Asia Using Microsoft Graph API](https://thehackernews.com/2026/04/harvester-deploys-linux-gogra-backdoor.html)**
*The Hacker News*
The Harvester APT group has deployed a Linux variant of its GoGra backdoor that uses legitimate Microsoft Graph API and Outlook mailboxes as a covert C2 channel, bypassing traditional perimeter defenses. Symantec and Carbon Black attribute the campaign to espionage-focused targeting of entities in South Asia.

**[Lotus Wiper Malware Targets Venezuelan Energy Systems in Destructive Attack](https://thehackernews.com/2026/04/lotus-wiper-malware-targets-venezuelan.html)**
*The Hacker News*
Kaspersky discovered Lotus Wiper, a previously undocumented file wiper deployed against Venezuela's energy and utilities sector in late 2025 and early 2026, initiated via batch scripts. The attack represents a destructive ICS-adjacent campaign against critical infrastructure in Latin America.

**[Mustang Panda's New LOTUSLITE Variant Targets India Banks, South Korea Policy Circles](https://thehackernews.com/2026/04/mustang-pandas-new-lotuslite-variant.html)**
*The Hacker News*
A new LOTUSLITE backdoor variant distributed via India banking-themed lures communicates over HTTPS to a dynamic DNS C2 server and supports remote shell, file operations, and session management. The continued espionage capability set indicates Mustang Panda's sustained focus on South and East Asian financial and political targets.

**[French Govt Agency Confirms Breach as Hacker Offers to Sell Data](https://www.bleepingcomputer.com/news/security/french-govt-agency-confirms-breach-as-hacker-offers-to-sell-data/)**
*BleepingComputer*
France Titres — the French government agency responsible for issuing passports, national ID cards, and driver's licenses — has confirmed a data breach after a threat actor claimed the attack and offered stolen citizen data for sale. The breach affects a document-issuance agency, raising identity fraud concerns for potentially large numbers of French citizens.

**[Over 1,300 Microsoft SharePoint Servers Vulnerable to Spoofing Attacks](https://www.bleepingcomputer.com/news/security/over-1-300-microsoft-sharepoint-servers-vulnerable-to-ongoing-attacks/)**
*BleepingComputer*
More than 1,300 SharePoint servers exposed online remain unpatched against a spoofing vulnerability that was first exploited as a zero-day and continues to see active abuse. Organizations running on-premises SharePoint should treat this as a priority patch.

**[DPRK Fake Job Scams Self-Propagate in 'Contagious Interview'](https://www.darkreading.com/cyberattacks-data-breaches/dprk-fake-job-scams-self-propagate-contagious-interview)**
*Dark Reading*
North Korean threat actors have evolved the Contagious Interview campaign so that a compromised developer repository acts as a worm-like vector, spreading RATs and other malware to developers who interact with the poisoned code. The self-propagating nature significantly extends the reach of what was previously a targeted social engineering campaign.

**[Toxic Combinations: When Cross-App Permissions Stack into Risk](https://thehackernews.com/2026/04/toxic-combinations-when-cross-app.html)**
*The Hacker News*
Analysis of the January 2026 Moltbook breach — which exposed 35,000 email addresses, 1.5 million agent API tokens, and plaintext third-party credentials — shows how individually benign cross-app permission grants create compounding risk at scale. The case study illustrates emerging agent-to-agent trust chain vulnerabilities in multi-agent SaaS ecosystems.

---

## Policy & Compliance

**[Anthropic's Mythos Rollout Has Missed America's Cybersecurity Agency](https://www.theverge.com/policy/916758/anthropic-mythos-preview-cisa-left-out)**
*The Verge AI*
While several US federal agencies are piloting Anthropic's Mythos Preview cybersecurity model, CISA — the nation's central cybersecurity coordinator — reportedly does not have access. The omission raises questions about how Anthropic is prioritizing government partnerships for a tool explicitly designed to find infrastructure vulnerabilities.

**[ICE Uses Graphite Spyware](https://www.schneier.com/blog/archives/2026/04/ice-uses-graphite-spyware.html)**
*Schneier on Security*
U.S. Immigration and Customs Enforcement has acknowledged using spyware from Israeli company Graphite. The admission adds ICE to a growing list of U.S. law enforcement agencies deploying commercial spyware, renewing debate over oversight of government surveillance tools.

**["We Are Currently Clean on OPSEC": Why JD Can't Encrypt](https://arxiv.org/abs/2604.19711)**
*ArXiv cs.CR*
A formal analysis of the 2025 Signalgate leak uses applied pi-calculus to prove that the Trump administration's secure communications setup would leak despite end-to-end encryption, because the leak path (journalist access to a message thread) existed outside the encrypted channel. The paper deepens the socio-technical argument that encryption alone cannot substitute for proper operational security practices and access controls.

**[Global Web, Local Privacy? An International Review of Web Tracking](https://arxiv.org/abs/2604.18633)**
*ArXiv cs.CR*
A study evaluating tracker connections on websites across ten countries — comparing global Common Top 525 sites against local equivalents — finds that privacy laws are structurally mismatched with the global nature of the web's advertising and tracking infrastructure. The findings challenge the efficacy of jurisdiction-limited privacy regulation without accompanying cross-border enforcement mechanisms.
