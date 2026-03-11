# Security Digest — 2026-03-11

Today's security landscape is headlined by Microsoft's March Patch Tuesday (84 fixes, two public zero-days) and a cluster of active supply-chain attacks hitting npm and GitHub Actions, while AI agent security emerges as a fast-growing research focus with new prompt-injection defenses from OpenAI and real-world jailbreak demonstrations.

---

## AI Security Research

**[Researchers Trick Perplexity's Comet AI Browser Into Phishing Scam in Under Four Minutes](https://thehackernews.com/2026/03/researchers-trick-perplexitys-comet-ai.html)**
*The Hacker News*
Agentic web browsers powered by AI can be manipulated into participating in phishing and scam traps, researchers demonstrated with Perplexity's Comet in under four minutes. The findings highlight the risks of autonomous, multi-site agents acting on user behalf without robust trust boundaries.

**[Designing AI Agents to Resist Prompt Injection](https://openai.com/index/designing-agents-to-resist-prompt-injection)**
*OpenAI Blog*
OpenAI published guidance on how ChatGPT defends against prompt injection and social engineering in agent workflows, focusing on constraining risky actions and protecting sensitive data from untrusted content in the environment.

**[OpenAI's New Training Dataset Teaches AI Models Which Instructions to Trust](https://the-decoder.com/openais-new-training-dataset-teaches-ai-models-which-instructions-to-trust/)**
*The Decoder*
OpenAI released IH-Challenge, a training dataset designed to help models reliably prioritize trusted instructions over untrusted ones. Early results show measurable improvements in both security posture and resistance to prompt injection attacks.

**[OOD-MMSafe: Advancing MLLM Safety from Harmful Intent to Hidden Consequences](https://arxiv.org/abs/2603.09706)**
*ArXiv cs.AI*
Researchers introduce a benchmark of 455 curated query-image pairs that moves multimodal LLM safety evaluation beyond obvious harmful intent toward subtler, consequence-driven risk scenarios. The work surfaces gaps in current safety filters when harmful outcomes are indirect.

---

## Vulnerabilities & Exploits

**[Microsoft Patches 84 Flaws in March Patch Tuesday, Including Two Public Zero-Days](https://thehackernews.com/2026/03/microsoft-patches-84-flaws-in-march.html)**
*The Hacker News*
Microsoft's March update addresses 84 vulnerabilities across its software stack, including two already publicly disclosed flaws. Organizations should prioritize patching the publicly known issues given their elevated exploitation risk.

**[Critical n8n Flaws Allow Remote Code Execution and Exposure of Stored Credentials](https://thehackernews.com/2026/03/critical-n8n-flaws-allow-remote-code.html)**
*The Hacker News*
Two critical bugs in the n8n workflow automation platform can lead to arbitrary command execution and credential theft; patches are now available. CISA has separately ordered federal agencies to remediate the actively exploited RCE flaw within the mandated timeline.

**[CISA Orders Feds to Patch n8n RCE Flaw Exploited in Attacks](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-n8n-rce-flaw-exploited-in-attacks/)**
*BleepingComputer*
CISA added the n8n remote-code-execution vulnerability to its Known Exploited Vulnerabilities catalog and ordered federal civilian agencies to patch immediately. Active exploitation has already been observed in the wild.

**[Medtech Giant Stryker Offline After Iran-Linked Wiper Malware Attack](https://www.bleepingcomputer.com/news/security/medtech-giant-stryker-offline-after-iran-linked-wiper-malware-attack/)**
*BleepingComputer*
Stryker, a major medical technology company, was taken offline by a wiper malware attack claimed by Handala, an Iranian-linked hacktivist group with a record of destructive operations against Western targets. KrebsOnSecurity [also confirmed](https://krebsonsecurity.com/2026/03/iran-backed-hackers-claim-wiper-attack-on-medtech-firm-stryker/) the group's ties to Iranian intelligence agencies.

**[Xygeni GitHub Action Compromised Via Tag Poison](https://www.darkreading.com/application-security/xygeni-github-action-compromised-via-tag-poison)**
*Dark Reading*
Attackers poisoned a tag in AppSec vendor Xygeni's `xygeni/xygeni-action` GitHub Action and maintained an active C2 implant for up to a week before detection. The incident is the latest in a string of CI/CD supply-chain attacks targeting developer toolchains.

**[New PhantomRaven NPM Attack Wave Steals Dev Data via 88 Packages](https://www.bleepingcomputer.com/news/security/new-phantomraven-npm-attack-wave-steals-dev-data-via-88-packages/)**
*BleepingComputer*
A new wave of the PhantomRaven supply-chain campaign has published 88 malicious npm packages that exfiltrate sensitive data from JavaScript developers. The campaign continues to expand its package count across multiple attack waves.

**[UNC6426 Exploits nx npm Supply-Chain Attack to Gain AWS Admin Access in 72 Hours](https://thehackernews.com/2026/03/unc6426-exploits-nx-npm-supply-chain.html)**
*The Hacker News*
Threat actor UNC6426 used credentials stolen from last year's nx npm compromise to fully breach a victim's AWS environment within 72 hours of initial access. The case illustrates the long tail of damage from supply-chain compromises — stolen keys can be weaponized months later.

**[Five Malicious Rust Crates and AI Bot Exploit CI/CD Pipelines to Steal Developer Secrets](https://thehackernews.com/2026/03/five-malicious-rust-crates-and-ai-bot.html)**
*The Hacker News*
Five malicious Rust crates disguised as time utilities were found exfiltrating `.env` file contents to attacker-controlled servers. An AI bot was also observed automating parts of the CI/CD exploitation chain, a novel development in supply-chain attack tooling.

**[Dozens of Vendors Patch Security Flaws Across Enterprise Software and Network Devices](https://thehackernews.com/2026/03/dozens-of-vendors-patch-security-flaws.html)**
*The Hacker News*
SAP and numerous other vendors released patches for critical flaws enabling arbitrary code execution on enterprise software and network devices. The coordinated disclosure wave underscores the continued concentration of high-severity vulnerabilities in widely deployed business software.

---

## Policy & Compliance

**[Canada Needs Nationalized, Public AI](https://www.schneier.com/blog/archives/2026/03/canada-needs-nationalized-public-ai.html)**
*Schneier on Security*
Bruce Schneier argues Canada faces a critical choice: build sovereign AI compute infrastructure or allow value generated by Canadian data and public investment to flow to American Big Tech. The piece frames the Sovereign AI Compute Strategy as a matter of digital sovereignty, not just economic policy.

**[What Boards Must Demand in the Age of AI-Automated Exploitation](https://thehackernews.com/2026/03/what-boards-must-demand-in-age-of-ai.html)**
*The Hacker News*
As AI accelerates the pace of vulnerability exploitation, boards must move beyond post-incident questioning and demand proactive, measurable vulnerability management practices from security teams. The analysis draws on patterns from recent high-profile breaches to outline board-level expectations.

**[Meta Disables 150K Accounts Linked to Southeast Asia Scam Centers in Global Crackdown](https://thehackernews.com/2026/03/meta-disables-150k-accounts-linked-to.html)**
*The Hacker News*
Meta disabled over 150,000 accounts tied to Southeast Asian cyber-scam compounds as part of a multi-country law enforcement partnership. The action is part of an ongoing crackdown on organized "pig butchering" and romance-scam operations run from facilities in Myanmar, Cambodia, and Laos.
