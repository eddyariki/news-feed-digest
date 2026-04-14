# Security Digest — 2026-04-15

April's Patch Tuesday lands with 167 Microsoft fixes and two zero-days, while the debut of Claude Mythos — an AI that autonomously compromised an enterprise network end-to-end — is reshaping how defenders and regulators think about AI-enabled threats.

---

## AI Security Research

**[How Hackers Are Thinking About AI](https://www.schneier.com/blog/archives/2026/04/how-hackers-are-thinking-about-ai.html)**
*Schneier on Security*
A new paper studying hacker forum discourse finds that cybercriminals are still in the early-adoption phase with AI — interested but cautious — with most operational use focused on social engineering and low-skill automation rather than sophisticated exploit development.

**[Claude Mythos can autonomously compromise weakly defended enterprise networks end-to-end](https://the-decoder.com/claude-mythos-can-autonomously-compromise-weakly-defended-enterprise-networks-end-to-end/)**
*The Decoder*
The UK AI Safety Institute's evaluation found that Claude Mythos Preview became the first AI model to complete a full, autonomous attack simulation against a corporate network — a milestone that prompted Anthropic to restrict model access and drew immediate policy attention worldwide.

**[ADAM: A Systematic Data Extraction Attack on Agent Memory via Adaptive Querying](https://arxiv.org/abs/2604.09747)**
*ArXiv cs.AI*
Researchers demonstrate that an adversary can systematically extract private data stored in an LLM agent's memory by adaptively crafting queries, exposing a fundamental confidentiality risk in agentic systems that rely on persistent memory stores.

**[Backdoors in RLVR: Jailbreak Backdoors in LLMs From Verifiable Reward](https://arxiv.org/abs/2604.09748)**
*ArXiv cs.AI*
This paper shows that RLVR fine-tuning — now widely used to boost reasoning — can be poisoned with backdoors that cause a model to comply with harmful instructions on a hidden trigger, with the attack surviving standard safety alignment passes.

**[PlanGuard: Defending Agents against Indirect Prompt Injection via Planning-based Consistency Verification](https://arxiv.org/abs/2604.10134)**
*ArXiv cs.CR*
PlanGuard detects indirect prompt injection by checking whether a tool's returned instructions are consistent with the agent's original plan, offering a lightweight runtime defence that does not require model retraining.

**[RLSpoofer: A Lightweight Evaluator for LLM Watermark Spoofing Resilience](https://arxiv.org/abs/2604.11546)**
*ArXiv cs.CR*
RLSpoofer uses reinforcement learning to evaluate how easily an adversary can spoof existing LLM watermarking schemes under black-box conditions, finding that many current approaches are surprisingly fragile against adaptive spoofing.

**[DuCodeMark: Dual-Purpose Code Dataset Watermarking via Style-Aware Watermark-Poison Design](https://arxiv.org/abs/2604.10611)**
*ArXiv cs.CR*
Proposes a code dataset watermarking scheme that simultaneously deters unauthorized use and enables forensic tracing of stolen training data in code LLMs, without meaningfully degrading model utility.

---

## Vulnerabilities & Exploits

**[Microsoft April 2026 Patch Tuesday fixes 167 flaws, 2 zero-days](https://www.bleepingcomputer.com/news/microsoft/microsoft-april-2026-patch-tuesday-fixes-167-flaws-2-zero-days/)**
*BleepingComputer*
Microsoft's largest Patch Tuesday of 2026 so far addresses 167 vulnerabilities — including two actively exploited zero-days — across Windows, Office, and Azure components; updates for Windows 10 (KB5082200) and Windows 11 (KB5083769 / KB5082052) are available now.

**[CISA Adds 6 Known Exploited Flaws in Fortinet, Microsoft, and Adobe Software](https://thehackernews.com/2026/04/cisa-adds-6-known-exploited-flaws-in.html)**
*The Hacker News*
CISA expanded its KEV catalog with six newly confirmed in-the-wild vulnerabilities spanning Fortinet, Microsoft, and Adobe products, requiring federal agencies to patch within the standard remediation window and signalling active threat-actor interest.

**[108 Malicious Chrome Extensions Steal Google and Telegram Data, Affecting 20,000 Users](https://thehackernews.com/2026/04/108-malicious-chrome-extensions-steal.html)**
*The Hacker News*
Researchers uncovered a coordinated campaign in which 108 Chrome Web Store extensions share C2 infrastructure to harvest Google OAuth2 tokens and Telegram session data; a separate BleepingComputer report tallies over 100 overlapping extensions also deploying backdoors and ad-fraud payloads.

**[ShowDoc RCE Flaw CVE-2025-0520 Actively Exploited on Unpatched Servers](https://thehackernews.com/2026/04/showdoc-rce-flaw-cve-2025-0520-actively.html)**
*The Hacker News*
CVE-2025-0520, a critical remote code execution bug in the ShowDoc documentation platform (CVSS 9.8), is being actively exploited in the wild on unpatched instances, particularly those run by organisations in China.

**[New PHP Composer Flaws Enable Arbitrary Command Execution — Patches Released](https://thehackernews.com/2026/04/new-php-composer-flaws-enable-arbitrary.html)**
*The Hacker News*
Two high-severity command injection vulnerabilities in Composer, the dominant PHP dependency manager, could allow an attacker to execute arbitrary commands on developer machines or CI systems; patches are available and should be applied immediately given Composer's ubiquity in the PHP supply chain.

**[McGraw-Hill confirms data breach following extortion threat](https://www.bleepingcomputer.com/news/security/mcgraw-hill-confirms-data-breach-following-extortion-threat/)**
*BleepingComputer*
Education publisher McGraw-Hill confirmed that attackers exploited a Salesforce misconfiguration to access internal data; the disclosure came only after the threat actors issued an extortion demand, highlighting ongoing risks from cloud platform misconfigurations.

**[Fake Ledger Live app on Apple's App Store stole $9.5M in crypto](https://www.bleepingcomputer.com/news/security/fake-ledger-live-app-on-apples-app-store-stole-95m-in-crypto/)**
*BleepingComputer*
A trojanised Ledger Live app that passed App Store review drained roughly $9.5 million in cryptocurrency from approximately 50 macOS users within days, underscoring persistent gaps in app-store vetting for financial applications.

**[Mirax Android RAT Turns Devices into SOCKS5 Proxies, Reaching 220,000 via Meta Ads](https://thehackernews.com/2026/04/mirax-android-rat-turns-devices-into.html)**
*The Hacker News*
The Mirax remote access trojan is spreading through paid Meta advertisements, converting infected Android devices into SOCKS5 proxies; the campaign has already reached more than 220,000 accounts across Facebook, Instagram, Messenger, and Threads.

---

## Policy & Compliance

**[Claude Mythos is a wake-up call for Europe's AI safety apparatus](https://the-decoder.com/claude-mythos-is-a-wake-up-call-for-europes-ai-safety-apparatus/)**
*The Decoder*
While the UK's AI Safety Institute has direct evaluation access to frontier models, EU regulators have almost no comparable visibility; Mythos's demonstrated cyber-offensive capabilities are accelerating calls for Europe to establish equivalent testing infrastructure before more capable models are released.

**[AI-Driven Pushpaganda Scam Exploits Google Discover to Spread Scareware and Ad Fraud](https://thehackernews.com/2026/04/ai-driven-pushpaganda-scam-exploits.html)**
*The Hacker News*
Researchers uncovered a large-scale operation that uses AI-generated fake news articles optimised for Google Discover to funnel readers into scareware and ad-fraud funnels, illustrating how generative AI is lowering the cost of influence-operation infrastructure.

**[Analysis of 216M Security Findings Shows a 4x Increase In Critical Risk (2026 Report)](https://thehackernews.com/2026/04/analysis-of-216m-security-findings.html)**
*The Hacker News*
OX Security's analysis of 216 million findings across 250 organisations found that while alert volume grew 52% year-over-year, prioritised critical risk surged nearly 400%, driven largely by AI-assisted development introducing new vulnerability classes faster than teams can remediate them.
