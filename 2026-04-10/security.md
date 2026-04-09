# Security Digest — 2026-04-10

Today's threat landscape features an Adobe Reader zero-day exploited since December, a leaked Windows zero-day PoC, multiple targeted APT campaigns, and growing regulatory scrutiny of AI labs restricting access to powerful cybersecurity models.

---

## AI Security Research

**[SALLIE: Safeguarding Against Latent Language & Image Exploits](https://arxiv.org/abs/2604.06247)**
*ArXiv cs.CR — Azov, Rivlin, Shtar*

Proposes a unified defense against textual jailbreaks, visual jailbreaks, and prompt injection attacks on LLMs and Vision-Language Models. Prior defenses treat these threats in isolation; SALLIE addresses all three modalities without the performance degradation typical of input-transformation approaches.

**[The Defense Trilemma: Why Prompt Injection Defense Wrappers Fail?](https://arxiv.org/abs/2604.06436)**
*ArXiv cs.CR — Bhatt, Munshi, Narajala et al.*

Formally proves that no continuous, utility-preserving wrapper defense can make all outputs safe for an LLM with a connected prompt space — every such wrapper must leave some threshold-level inputs unchanged. The result establishes a fundamental limit on pre-processing defenses for prompt injection.

**[ClawLess: A Security Model of AI Agents](https://arxiv.org/abs/2604.06284)**
*ArXiv cs.CR — Lu, Liu, Wang, Zhang*

Introduces a security framework that enforces formally verified policies on autonomous AI agents, arguing that training- or prompting-based behavioral controls cannot provide fundamental security guarantees when agents retrieve information and execute code.

**[SkillSieve: A Hierarchical Triage Framework for Detecting Malicious AI Agent Skills](https://arxiv.org/abs/2604.06550)**
*ArXiv cs.CR — Hou, Yang*

Audits of the ClawHub agent-skill marketplace found 13–26% of its 13,000+ community-contributed skills contain security vulnerabilities. SkillSieve proposes a three-layer detection system that handles both code payloads and natural-language instruction files where prompt injection hides.

**[Guiding Symbolic Execution with Static Analysis and LLMs for Vulnerability Discovery](https://arxiv.org/abs/2604.06506)**
*ArXiv cs.CR — Shafiuzzaman, Desai, Guo, Bultan*

SAILOR automates the harness-writing bottleneck in symbolic execution by combining static analysis with LLM orchestration, scaling vulnerability discovery to large codebases without requiring expert manual setup.

---

## Vulnerabilities & Exploits

**[Adobe Reader Zero-Day Exploited via Malicious PDFs Since December 2025](https://thehackernews.com/2026/04/adobe-reader-zero-day-exploited-via.html)**
*The Hacker News*

A highly sophisticated zero-day in Adobe Reader has been actively exploited in the wild since at least December 2025, with a crafted invoice PDF first appearing on VirusTotal in November. EXPMON researcher Haifei Li detailed the finding; Adobe has since patched the flaw.

**[EngageLab SDK Flaw Exposed 50M Android Users, Including 30M Crypto Wallets](https://thehackernews.com/2026/04/engagelab-sdk-flaw-exposed-50m-android.html)**
*The Hacker News*

A now-patched vulnerability in the widely used EngageLab Android SDK allowed apps on the same device to bypass the Android security sandbox and access private data across application boundaries — a particular concern for the ~30 million cryptocurrency wallet users in the affected install base.

**['BlueHammer' Windows Zero-Day Exploit Signals Microsoft Bug Disclosure Issues](https://www.darkreading.com/vulnerabilities-threats/bluehammer-windows-exploit-microsoft-bug-disclosure-issues)**
*Dark Reading — Elizabeth Montalbano*

A researcher publishing as "Chaotic Eclipse" released a PoC exploit for an unpatched Windows local-privilege-escalation zero-day, citing frustration with Microsoft's bug-disclosure process. The flaw allows a local user to take over the system; Microsoft has not yet issued a fix.

**[New 'LucidRook' Malware Used in Targeted Attacks on NGOs, Universities](https://www.bleepingcomputer.com/news/security/new-lucidrook-malware-used-in-targeted-attacks-on-ngos-universities/)**
*BleepingComputer — Bill Toulas*

Threat cluster UAT-10362 is deploying a sophisticated Lua-based stager called LucidRook against Taiwanese NGOs and universities via spear-phishing. The malware embeds a Lua interpreter and Rust-compiled libraries inside a DLL to download and execute follow-on payloads.

**[New VENOM Phishing Attacks Steal Senior Executives' Microsoft Logins](https://www.bleepingcomputer.com/news/security/new-venom-phishing-attacks-steal-senior-executives-microsoft-logins/)**
*BleepingComputer — Bill Toulas*

A previously undocumented phishing-as-a-service platform called "VENOM" is targeting C-suite credentials across multiple industries. The platform appears purpose-built for high-value executive accounts, with infrastructure designed to relay stolen sessions in real time.

**[Healthcare IT Solutions Provider ChipSoft Hit by Ransomware Attack](https://www.bleepingcomputer.com/news/security/healthcare-it-solutions-provider-chipsoft-hit-by-ransomware-attack/)**
*BleepingComputer — Bill Toulas*

Dutch healthcare software vendor ChipSoft was forced to take its website and patient-facing digital services offline after a ransomware attack — another entry in the growing list of healthcare-sector incidents.

**[Smart Slider Updates Hijacked to Push Malicious WordPress, Joomla Versions](https://www.bleepingcomputer.com/news/security/smart-slider-updates-hijacked-to-push-malicious-wordpress-joomla-versions/)**
*BleepingComputer — Bill Toulas*

Attackers hijacked the update mechanism for the Smart Slider 3 Pro plugin and pushed a trojaned version containing multiple backdoors to WordPress and Joomla sites — a textbook supply chain compromise targeting the web CMS ecosystem.

**[After Data Breach, $10B-Valued Startup Mercor Is Having a Month](https://techcrunch.com/2026/04/09/after-data-breach-10b-valued-startup-mercor-is-having-a-month/)**
*TechCrunch AI — Julie Bort*

AI hiring startup Mercor is now facing lawsuits and reportedly losing major customers following a breach that exposed user data. The incident underscores the liability exposure faced by AI-era startups that accumulate sensitive personal information.

**[Hackers Steal $3.6 Million from Crypto ATM Giant Bitcoin Depot](https://www.bleepingcomputer.com/news/security/crypto-atm-giant-bitcoin-depot-says-hackers-stole-36-million-from-its-wallets/)**
*BleepingComputer — Sergiu Gatlan*

Bitcoin Depot, operator of one of the largest Bitcoin ATM networks, disclosed that attackers breached its systems last month and drained $3.665 million in Bitcoin from company wallets.

**[Russia's 'Fancy Bear' APT Continues Its Global Onslaught](https://www.darkreading.com/threat-intelligence/russias-fancy-bear-apt-continues-global-onslaught)**
*Dark Reading — Alexander Culafi*

Security experts warn that Fancy Bear (APT28) remains highly active and that defenders don't need to match the group's technical sophistication to be targeted. Patching and some form of zero-trust architecture are now described as non-negotiable baseline defenses.

**[Eurail Says December Data Breach Impacts 300,000 Individuals](https://www.bleepingcomputer.com/news/security/eurail-says-december-data-breach-impacts-300-000-individuals/)**
*BleepingComputer — Sergiu Gatlan*

European rail pass operator Eurail has disclosed that a December 2025 breach resulted in the theft of personal information belonging to over 300,000 customers, a delayed notification now surfacing months after the initial intrusion.

---

## Policy & Compliance

**[Is Anthropic Limiting the Release of Mythos to Protect the Internet — or Anthropic?](https://techcrunch.com/2026/04/09/is-anthropic-limiting-the-release-of-mythos-to-protect-the-internet-or-anthropic/)**
*TechCrunch AI — Tim Fernholz*

Anthropic restricted deployment of its Mythos model, citing its unusual capability to discover exploitable vulnerabilities in widely deployed software. The article questions whether the stated cybersecurity rationale reflects genuine risk management or serves competitive interests at the frontier.

**[OpenAI Reportedly Following Anthropic's Lead in Restricting Access to Powerful Cybersecurity AI](https://the-decoder.com/openai-reportedly-following-anthropics-lead-in-restricting-access-to-powerful-cybersecurity-ai/)**
*The Decoder — Maximilian Schreiner*

OpenAI is reportedly developing an AI model with advanced offensive cybersecurity capabilities that will be made available only to a vetted group of organizations — mirroring Anthropic's approach with Mythos and signaling an emerging industry norm of restricted access tiers for dual-use security models.

**[On Microsoft's Lousy Cloud Security](https://www.schneier.com/blog/archives/2026/04/on-microsofts-lousy-cloud-security.html)**
*Schneier on Security — Bruce Schneier*

Bruce Schneier highlights a ProPublica investigation revealing that federal cybersecurity evaluators found Microsoft's cloud documentation so inadequate that they had "a lack of confidence in assessing the system's overall security posture." The post revives long-running concerns about Microsoft's security culture in government-facing cloud services.
