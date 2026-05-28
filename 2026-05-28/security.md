# Security Digest — 2026-05-28

Today's security landscape is dominated by AI's double edge: attackers are weaponizing chatbots and AI-targeted supply chains while researchers race to harden LLM agents against prompt injection, jailbreaks, and backdoors. Meanwhile, traditional fronts stay busy with actively exploited CVEs, banking-trojan campaigns, and growing calls for cyber-policy reform.

---

## AI Security Research

[AgentSecBench: Measuring Prompt Injection, Privacy Leakage, and Tool-Use Integrity in LLM Agents](https://arxiv.org/abs/2605.26269)
*ArXiv cs.CR*
A formal security framework and benchmark for LLM agents, which conflate untrusted data with authority when instructions, retrieved records, and tool observations share one generative channel. It measures how easily an untrusted string can hijack secret-bearing responses or action proposals.

[Open-Weight LLM Fine-Tuning Defenses are Susceptible to Simple Attacks](https://arxiv.org/abs/2605.26526)
*ArXiv cs.LG*
The paper challenges the assumption that fine-tuning defenses block adversarial use, showing that safeguarded open-weight models already encode harmful knowledge that can be elicited through simple jailbreaks rather than newly learned. This undercuts a core premise behind current open-weight safety guarantees.

[Furina: Fragmented Uncertainty-Driven Refusal Instability Attack](https://arxiv.org/abs/2605.26158)
*ArXiv cs.AI*
Researchers show that LLM safety alignment is not a binary threshold but has an "instability region" where small perturbations make refusals stochastic, and exploit it with a diagnostic-driven attack. The work reframes refusal behavior as a probabilistic, attackable surface.

[VERA-V: Variational Inference Framework for Jailbreaking Vision-Language Models](https://arxiv.org/abs/2510.17759)
*ArXiv cs.LG*
A variational-inference red-teaming framework that exposes multimodal jailbreak vulnerabilities in vision-language models beyond the brittle, single-attack templates used in prior work. It surfaces a broader range of weaknesses introduced by VLMs' visual reasoning.

[GradSentry: Gradient Spectral Entropy for Backdoor Sample Filtering in LLM Fine-Tuning](https://arxiv.org/abs/2605.26574)
*ArXiv cs.CR*
A defense that filters backdoor/poisoned samples during fine-tuning using the spectral entropy of per-sample gradients, succeeding where clustering-based methods fail at extreme poison ratios. It targets the threat of misbehavior introduced through untrusted training data.

[Assessing Per-Sample Membership Inference Vulnerability without Retraining](https://arxiv.org/abs/2602.15919)
*ArXiv cs.AI*
A privacy method to estimate how exposed individual training points are to membership inference attacks without the cost of training shadow models. It shows per-sample risk depends on more than a point's loss.

[Turning Bias into Bugs: Bandit-Guided Style Manipulation Attacks on LLM Judges](https://arxiv.org/abs/2605.26156)
*ArXiv cs.AI*
Introduces BITE, a black-box adversarial framework that casts stylistic edits as a contextual bandit problem to artificially inflate the scores LLM judges assign. It exposes the stylistic biases of LLM evaluators as a real security vulnerability.

[Sandlock: Confining AI Agent Code with Unprivileged Linux Primitives](https://arxiv.org/abs/2605.26298)
*ArXiv cs.CR*
A lightweight isolation approach for the untrusted code AI agents increasingly run on developer machines—model-generated shell commands, runtime-fetched scripts, and unknown tool plugins—without the overhead of containers or microVMs. It aims for stronger guarantees than ad-hoc wrappers like chroot or ulimit.

[SkillSieve: A Hierarchical Triage Framework for Detecting Malicious AI Agent Skills](https://arxiv.org/abs/2604.06550)
*ArXiv cs.AI*
A triage framework for agent-skill marketplaces, where audits report 13–26% of community-contributed skills contain security vulnerabilities, combining code analysis with reading natural-language instructions that hide prompt injection. It covers both the code and prose modalities that regex scanners and static analyzers each miss.

[Prompt Injection Detection is Regime-Dependent](https://arxiv.org/abs/2605.26999)
*ArXiv cs.CL*
A deployment-aware evaluation comparing lexical, semantic, structural, and transformer-based prompt-injection detectors across multiple models and operating regimes. It finds detector effectiveness is highly dependent on real-world deployment constraints rather than fixed across settings.

---

## Vulnerabilities & Exploits

[Millions of AI agents imperiled by critical vulnerability in open source package](https://arstechnica.com/information-technology/2026/05/millions-of-ai-agents-imperiled-by-critical-vulnerability-in-open-source-package/)
*Ars Technica*
A critical flaw dubbed "BadHost" was found in Starlette, a Python package with 325 million weekly downloads, putting a vast number of AI agents and web services at risk.

[Gitea Vulnerability Exposes Private Container Images without Authentication](https://thehackernews.com/2026/05/gitea-vulnerability-exposes-private.html)
*The Hacker News*
CVE-2026-27771 lets unauthenticated remote attackers pull private container images from self-hosted Gitea deployments without any account or credentials. It affects all versions of Gitea prior to 1.26.2.

[CISA gives feds 4 days to patch actively exploited cPanel plugin flaw](https://www.bleepingcomputer.com/news/security/cisa-gives-feds-4-days-to-patch-actively-exploited-cpanel-plugin-flaw/)
*BleepingComputer*
CISA gave U.S. federal agencies just four days to patch a critical, actively exploited vulnerability in the LiteSpeed cPanel user-end plugin. The unusually short deadline reflects ongoing in-the-wild attacks.

[Malicious npm Package Stole Files From Claude AI User Directory via GitHub](https://thehackernews.com/2026/05/malicious-npm-package-stole-files-from.html)
*The Hacker News*
OX Security found an npm package, "mouse5212-super-formatter," that exfiltrates files from `/mnt/user-data`—the directory Anthropic's Claude uses to handle uploads and outputs—via GitHub. It marks a supply-chain attack tailored specifically to AI tooling.

[GlassWorm Malware Takedown Disrupts Developer Supply Chain Attack Infrastructure](https://thehackernews.com/2026/05/glassworm-malware-takedown-disrupts.html)
*The Hacker News*
CrowdStrike, Google, and the Shadowserver Foundation simultaneously disrupted all C2 channels of GlassWorm, a persistent campaign that targeted software developers through malicious packages and extensions since early 2025. The botnet had relied on resilient Solana blockchain and BitTorrent DHT infrastructure.

[GPU mining malware spreads via SEO poisoning, AI chatbots](https://www.bleepingcomputer.com/news/security/gpu-mining-malware-spreads-via-seo-poisoning-ai-chatbots/)
*BleepingComputer*
An ongoing cryptojacking campaign targets high-performance machines through coordinated SEO poisoning that also manipulates AI chatbot recommendations to surface malicious download sites. The technique extends social engineering beyond conventional search results.

[FBI warns of in-person data theft attacks from extortion gang](https://www.bleepingcomputer.com/news/security/fbi-warns-of-silent-ransom-group-in-person-data-theft-attacks/)
*BleepingComputer*
The FBI warned that the Silent Ransom Group extortion gang is now physically showing up to socially engineer its way into U.S. law firms' servers and databases. The shift to in-person tactics marks an escalation in data-theft operations.

[Grandoreiro Malware and BTMOB RAT Campaigns Target Windows and Android Users](https://thehackernews.com/2026/05/grandoreiro-malware-and-btmob-rat.html)
*The Hacker News*
Per WatchGuard and ESET, two banking-trojan campaigns are infecting Windows and Android devices with Grandoreiro and BTMOB malware. The campaigns single out companies in Spain, Portugal, and Mexico, plus mobile users in Brazil.

[Latin American Cybercriminals Hoover Up Government Data](https://www.darkreading.com/cyberattacks-data-breaches/latin-american-cybercriminals-government-data)
*Dark Reading*
A purported leak of 5.8 million records of Uruguayan citizens is the latest case of cybercriminals targeting government agencies to monetize citizen data. It highlights a regional pattern of attacks on public-sector data stores.

[AI-Assisted Exploit Development Outpaces Scanner Detection](https://www.darkreading.com/threat-intelligence/ai-assisted-exploit-development-scanner-detection)
*Dark Reading*
New research shows attackers are using AI to dramatically compress the time needed to build a working exploit for a CVE. The acceleration is outpacing defenders' scanner-based detection.

---

## Policy & Compliance

[FBI's 2025 Internet Crime Report](https://www.schneier.com/blog/archives/2026/05/fbis-2025-internet-crime-report.html)
*Schneier on Security*
Bruce Schneier flags the FBI's newly published 2025 Internet Crime Report, which is full of statistics on the year's cybercrime landscape.

[State Cyber Leaders Beg Congress for More Funding, Support](https://www.darkreading.com/threat-intelligence/state-leaders-beg-congress-resume-cyber-funding)
*Dark Reading*
A congressional hearing showed states reeling from federal cutbacks to cyber grants and information-sharing initiatives even as critical-infrastructure attacks intensify. State leaders pressed Congress to restore the support.

[Former U.S. cybersecurity chief urges IT reform in Japan](https://www.japantimes.co.jp/business/2026/05/27/tech/cybersecurity-japan-interview/)
*The Japan Times*
Chris Inglis, the first U.S. national cyber director, warns that systems deployed in Japan for 20–30 years carry "many weaknesses" and calls for IT reform.

[On The Effectiveness of the UK NIS Regulations as a Mandatory Cybersecurity Reporting Regime](https://arxiv.org/abs/2603.19084)
*ArXiv cs.CR*
Using UK-wide incident data reported under the NIS Regulations in 2024, the study provides rare empirical evidence on attacks against critical national infrastructure and assesses the reporting regime's effectiveness. It finds 29% of NIS reports already concern significant-impact incidents.

[A Technical Policy Blueprint for Trustworthy Decentralized AI](https://arxiv.org/abs/2512.11878)
*ArXiv cs.CR*
The paper proposes transparent, scalable, and verifiable governance mechanisms for decentralized AI systems such as federated learning, moving beyond today's bespoke, infrastructure-specific policies. It aims to unlock privacy-preserving AI asset marketplaces like healthcare data exchanges.
