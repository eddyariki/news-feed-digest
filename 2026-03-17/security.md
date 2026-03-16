# Security Digest — 2026-03-17

Supply chain attacks targeting Python/ML repositories, active state-sponsored espionage, and a wave of LLM safety research dominate today's security landscape — while a major medical device manufacturer's environment was wiped remotely without any malware.

---

## AI Security Research

**[Prompt Injection as Role Confusion](https://arxiv.org/abs/2603.12277)**
*ArXiv cs.AI / cs.CR*
Researchers identify why prompt injection persists despite safety training: LLMs infer "who is speaking" from writing style rather than message origin, so untrusted text that mimics a privileged role inherits its authority. The paper introduces role probes to measure this effect and tests injection attacks that exploit it.

**[PISmith: Reinforcement Learning-based Red Teaming for Prompt Injection Defenses](https://arxiv.org/abs/2603.13026)**
*ArXiv cs.LG / cs.CR*
An RL-based framework that systematically stress-tests prompt injection defenses by training an adaptive attacker, exposing that many proposed mitigations fail against adaptive adversaries and may provide a false sense of security.

**[Colluding LoRA: A Composite Attack on LLM Safety Alignment](https://arxiv.org/abs/2603.12681)**
*ArXiv cs.LG / cs.CR*
CoLoRA shows that multiple individually-benign LoRA adapters can be composed at inference time to consistently bypass safety alignment — no specific trigger or prompt engineering required, just linear combination of adapters that each appear harmless in isolation.

**[Learnability and Privacy Vulnerability are Entangled in a Few Critical Weights](https://arxiv.org/abs/2603.13186)**
*ArXiv cs.AI / cs.CR*
Privacy vulnerabilities in neural networks concentrate in a small fraction of weights — the same weights critical to model utility — meaning naive membership privacy fixes degrade performance while targeted weight-level interventions can preserve both.

**[Editing Away the Evidence: Diffusion-Based Image Manipulation and the Failure Modes of Robust Watermarking](https://arxiv.org/abs/2603.12949)**
*ArXiv cs.CR*
Diffusion-based image editing can remove robust invisible watermarks used for copyright and content provenance, exposing gaps in current detection frameworks for AI-generated content.

**[GlassWorm Attack Uses Stolen GitHub Tokens to Force-Push Malware Into Python Repos](https://thehackernews.com/2026/03/glassworm-attack-uses-stolen-github.html)**
*The Hacker News*
The GlassWorm campaign is using stolen GitHub tokens to inject obfuscated malware into hundreds of Python repositories — targeting Django apps, ML research code, Streamlit dashboards, and PyPI packages by appending code to `setup.py`, `main.py`, and `app.py`.

**[ClickFix Campaigns Spread MacSync macOS Infostealer via Fake AI Tool Installers](https://thehackernews.com/2026/03/clickfix-campaigns-spread-macsync-macos.html)**
*The Hacker News*
Three distinct ClickFix campaigns deliver the MacSync macOS information stealer by impersonating AI tool installers, relying entirely on user interaction (copy-paste command execution) rather than traditional exploits — making technical defenses insufficient without user awareness.

**[Possible New Result in Quantum Factorization](https://www.schneier.com/blog/archives/2026/03/possible-new-result-in-quantum-factorization.html)**
*Schneier on Security*
A new claimed result suggests a theoretical speedup in factoring large numbers with a quantum computer; Schneier notes skepticism and lack of qualification to review, but flags it as significant if confirmed, with implications for RSA encryption.

---

## Vulnerabilities & Exploits

**[⚡ Weekly Recap: Chrome 0-Days, Router Botnets, AWS Breach, Rogue AI Agents & More](https://thehackernews.com/2026/03/weekly-recap-chrome-0-days-router.html)**
*The Hacker News*
This week's roundup covers active Chrome zero-days, botnet exploitation of consumer routers, an AWS-related breach, and emerging rogue AI agent activity — a dense week with multiple high-severity issues moving from theoretical to actively exploited.

**[Stryker attack wiped tens of thousands of devices, no malware needed](https://www.bleepingcomputer.com/news/security/stryker-attack-wiped-tens-of-thousands-of-devices-no-malware-needed/)**
*BleepingComputer*
Last week's cyberattack on medical technology giant Stryker was confined to its internal Microsoft environment but remotely wiped tens of thousands of employee devices — achieved through native cloud administrative capabilities rather than any malware deployment.

**[DRILLAPP Backdoor Targets Ukraine, Abuses Microsoft Edge Debugging for Stealth Espionage](https://thehackernews.com/2026/03/drillapp-backdoor-targets-ukraine.html)**
*The Hacker News*
A new campaign linked to Russia-aligned threat actor Laundry Bear (UAC-0190) deploys the DRILLAPP backdoor against Ukrainian entities, abusing Microsoft Edge's remote debugging interface for stealthy command-and-control that blends with legitimate browser traffic.

**[CISA flags Wing FTP Server flaw as actively exploited in attacks](https://www.bleepingcomputer.com/news/security/cisa-flags-wing-ftp-server-flaw-as-actively-exploited-in-attacks/)**
*BleepingComputer*
CISA added a Wing FTP Server vulnerability to its Known Exploited Vulnerabilities catalog, warning that it is actively being chained toward remote code execution — U.S. government agencies have until the deadline to patch.

**[UK's Companies House confirms security flaw exposed business data](https://www.bleepingcomputer.com/news/security/uks-companies-house-confirms-security-flaw-exposed-business-data/)**
*BleepingComputer*
The UK government's company registry confirms its WebFiling service had a security flaw that exposed company information since October 2025; the service was taken offline last Friday for remediation and has since been restored.

**[Internet-Scale Measurement of React2Shell Exploitation Using an Active Network Telescope](https://arxiv.org/abs/2603.12300)**
*ArXiv cs.CR*
Researchers conducted an internet-scale study of exploitation of a critical RCE vulnerability (CVE disclosed December 2025) in server-side React frameworks, mapping active exploitation patterns and attacker infrastructure using a network telescope methodology.

**[Attackers Abuse LiveChat to Phish Credit Card, Personal Data](https://www.darkreading.com/threat-intelligence/attackers-livechat-phish-credit-card-personal-data)**
*Dark Reading*
A social engineering campaign impersonates PayPal and Amazon customer support via LiveChat to harvest credit card numbers and personal data, exploiting user trust in real-time chat support channels.

---

## Policy & Compliance

**[Android 17 Blocks Non-Accessibility Apps from Accessibility API to Prevent Malware Abuse](https://thehackernews.com/2026/03/android-17-blocks-non-accessibility.html)**
*The Hacker News*
Google's Android 17 Beta 2 adds a restriction under Advanced Protection Mode that prevents non-accessibility apps from using the accessibility services API — a commonly abused vector for banking malware and stalkerware — building on AAPM introduced in Android 16.

**[Inside Olympic Cybersecurity: Lessons From Paris 2024 to Milan Cortina 2026](https://www.darkreading.com/threat-intelligence/olympic-cybersecurity-paris-2024-milan-2026)**
*Dark Reading*
Former Paris 2024 Olympics CISO Franz Regul details how the Games handled an unprecedented scale of cyber threats, offering operational lessons relevant to any large-scale event security program ahead of the 2026 Winter Olympics.

**[Shadow AI is everywhere. Here's how to find and secure it.](https://www.bleepingcomputer.com/news/security/shadow-ai-is-everywhere-heres-how-to-find-and-secure-it/)**
*BleepingComputer*
As employees adopt AI tools without IT oversight, shadow AI is spreading across SaaS environments; Nudge Security outlines discovery, monitoring, and governance approaches for security teams trying to get visibility and control without blocking legitimate use.
