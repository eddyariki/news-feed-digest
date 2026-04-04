# Security Digest — 2026-04-04

Active nation-state campaigns dominated the day, with DPRK and Chinese threat actors hitting European governments, crypto exchanges, and the npm ecosystem simultaneously — while researchers published a wave of papers targeting LLM jailbreaks, MCP-server abuse, and watermarking for AI-generated content.

---

## AI Security Research

**[SelfGrader: Stable Jailbreak Detection for Large Language Models using Token-Level Logits](https://arxiv.org/abs/2604.01473)**
*ArXiv cs.CR*
Proposes a jailbreak detection method that operates on token-level logit distributions rather than output text, offering more stable and manipulation-resistant guardrails for LLMs.

**[Low-Effort Jailbreak Attacks Against Text-to-Image Safety Filters](https://arxiv.org/abs/2604.01888)**
*ArXiv cs.CV*
Demonstrates that simple, low-cost adversarial prompts can systematically bypass safety filters in widely deployed text-to-image models, raising concerns about the robustness of current content moderation pipelines.

**[From Component Manipulation to System Compromise: Understanding and Detecting Malicious MCP Servers](https://arxiv.org/abs/2604.01905)**
*ArXiv cs.CR*
Analyzes how the Model Context Protocol's open integration model can be exploited by malicious tool servers to compromise LLM-powered applications, and proposes detection strategies.

**[No Attacker Needed: Unintentional Cross-User Contamination in Shared-State LLM Agents](https://arxiv.org/abs/2604.01350)**
*ArXiv cs.CR*
Shows that multi-tenant LLM agents maintaining persistent task state can leak sensitive information between users without any active adversary — a structural privacy risk in production deployments.

**[Safety, Security, and Cognitive Risks in World Models](https://arxiv.org/abs/2604.01346)**
*ArXiv cs.LG*
Surveys the emerging attack surface of learned world models in robotics and autonomous systems, covering adversarial manipulation, distributional exploitation, and misaligned goal-planning risks.

**[An End-to-End Model for Logits-Based Large Language Models Watermarking](https://arxiv.org/abs/2505.02344)**
*ArXiv cs.CR*
Presents an end-to-end watermarking framework for LLM outputs that embeds imperceptible signals in logit distributions, supporting copyright protection and AIGC source tracing.

**[Combating Data Laundering in LLM Training](https://arxiv.org/abs/2604.01904)**
*ArXiv cs.CR*
Introduces methods to detect when rights-holders' data has been laundered into LLM training sets by adversaries attempting to mask unauthorized use, strengthening data-provenance enforcement.

**[Tex3D: Objects as Attack Surfaces via Adversarial 3D Textures for Vision-Language-Action Models](https://arxiv.org/abs/2604.01618)**
*ArXiv cs.CV*
Demonstrates that physically realizable adversarial textures applied to everyday objects can reliably mislead VLA robotic manipulation models, highlighting a new attack vector for embodied AI.

---

## Vulnerabilities & Exploits

**[CERT-EU: European Commission hack exposes data of 30 EU entities](https://www.bleepingcomputer.com/news/security/cert-eu-european-commission-hack-exposes-data-of-30-eu-entities/)**
*BleepingComputer*
CERT-EU attributed a compromise of European Commission cloud infrastructure to the TeamPCP threat group, with the breach resulting in data exposure across at least 29 other EU organizations.

**[UNC1069 Social Engineering of Axios Maintainer Led to npm Supply Chain Attack](https://thehackernews.com/2026/04/unc1069-social-engineering-of-axios.html)**
*The Hacker News*
North Korean threat actor UNC1069 executed a highly targeted social engineering campaign against the maintainer of the widely-used Axios npm package, resulting in a supply chain compromise affecting downstream JavaScript consumers.

**[Drift Loses $285 Million in Durable Nonce Social Engineering Attack Linked to DPRK](https://thehackernews.com/2026/04/drift-loses-285-million-in-durable.html)**
*The Hacker News*
Solana-based DEX Drift confirmed attackers drained approximately $285 million on April 1 via a social engineering attack exploiting durable nonces; the incident has been linked to North Korean threat actors.

**[China-Linked TA416 Targets European Governments with PlugX and OAuth-Based Phishing](https://thehackernews.com/2026/04/china-linked-ta416-targets-european.html)**
*The Hacker News*
A China-aligned APT has resumed targeting European government and diplomatic organizations with PlugX malware delivered via OAuth-based phishing after a two-year lull, signaling renewed geopolitical intelligence-gathering.

**[Blast Radius of TeamPCP Attacks Expands Amid Hacker Infighting](https://www.darkreading.com/threat-intelligence/teampcp-attacks-hacker-infighting)**
*Dark Reading*
As more organizations disclose breaches tied to TeamPCP's supply chain campaign, ShinyHunters and Lapsus$ have inserted themselves into the narrative — complicating attribution and incident response for affected enterprises.

**[Die Linke German political party confirms data stolen by Qilin ransomware](https://www.bleepingcomputer.com/news/security/die-linke-german-political-party-confirms-data-stolen-by-qilin-ransomware/)**
*BleepingComputer*
The Qilin ransomware group attacked Germany's Die Linke party, forcing IT system outages and threatening to leak sensitive political data — a notable escalation of ransomware targeting democratic institutions.

**[New SparkCat Variant in iOS, Android Apps Steals Crypto Wallet Recovery Phrase Images](https://thehackernews.com/2026/04/new-sparkcat-variant-in-ios-android.html)**
*The Hacker News*
An updated version of the SparkCat trojan has been discovered on both the Apple App Store and Google Play, using on-device OCR to steal screenshots containing cryptocurrency wallet recovery phrases.

**[Microsoft Details Cookie-Controlled PHP Web Shells Persisting via Cron on Linux Servers](https://thehackernews.com/2026/04/microsoft-details-cookie-controlled-php.html)**
*The Hacker News*
Microsoft Defender researchers documented a campaign using HTTP cookies as a covert command channel for PHP web shells on Linux, with cron-based persistence mechanisms that survive typical remediation attempts.

**[LinkedIn secretly scans for 6,000+ Chrome extensions, collects data](https://www.bleepingcomputer.com/news/security/linkedin-secretely-scans-for-6-000-plus-chrome-extensions-collects-data/)**
*BleepingComputer*
A report dubbed "BrowserGate" reveals that LinkedIn's website uses hidden JavaScript to enumerate visitors' installed browser extensions and collect device fingerprinting data without disclosure.

**[Hims & Hers warns of data breach after Zendesk support ticket breach](https://www.bleepingcomputer.com/news/security/hims-and-hers-warns-of-data-breach-after-zendesk-support-ticket-breach/)**
*BleepingComputer*
Telehealth company Hims & Hers disclosed a breach of customer support tickets via a compromised third-party Zendesk platform, underscoring persistent risks in SaaS-based customer service chains.

**[Apple Breaks Precedent, Patches DarkSword for iOS 18](https://www.darkreading.com/endpoint-security/apple-patches-darksword-ios-18)**
*Dark Reading*
Apple took the unusual step of backporting a patch for the severe DarkSword mobile exploit to iOS 18, extending protection to users unable or unwilling to upgrade to iOS 26.

**[Claude Source Code Leak Highlights Big Supply Chain Missteps](https://www.darkreading.com/application-security/source-code-leaks-highlight-lack-supply-chain-oversight)**
*Dark Reading*
Analysis of the leaked Anthropic source code uses the incident as a case study for why software supply chains need continuous oversight and hardened guardrails at every layer, not just at deployment boundaries.

---

## Policy & Compliance

**[Architectural Implications of the UK Cyber Security and Resilience Bill](https://arxiv.org/abs/2604.01937)**
*ArXiv cs.CR*
Analyzes how the UK's forthcoming CS&R Bill — the most significant reform of UK cyber law since NIS — will impose new architectural requirements on critical infrastructure operators, with implications for incident reporting timelines and supply chain accountability.

**[Why Third-Party Risk Is the Biggest Gap in Your Clients' Security Posture](https://thehackernews.com/2026/04/why-third-party-risk-is-biggest-gap-in.html)**
*The Hacker News*
Industry guidance piece arguing that the next major enterprise breaches will arrive through trusted vendors and unsanctioned SaaS tools rather than direct attacks, calling for third-party risk programs with continuous monitoring rather than point-in-time assessments.

**[Chainguard Unveils Factory 2.0 to Automate Hardening the Software Supply Chain](https://www.darkreading.com/application-security/chainguard-factory-automate-hardening-software-supply-chain)**
*Dark Reading*
Chainguard's rebuilt platform adds continuous reconciliation of open source artifacts across containers, libraries, agent skills, and GitHub Actions — a response to the wave of supply chain attacks disclosed this week.
