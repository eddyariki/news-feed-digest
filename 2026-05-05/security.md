# Security Digest — 2026-05-05

A heavy day across the stack: a critical cPanel auth-bypass under mass exploitation, a fresh MOVEit Automation flaw, a backdoored PyTorch Lightning on PyPI, and a wave of arXiv preprints picking apart jailbreaks, agentic-system safety, and adversarial robustness in deployed LLMs.

---

## AI Security Research

### [Minimal, Local, Causal Explanations for Jailbreak Success in Large Language Models](https://arxiv.org/abs/2605.00123)
*ArXiv cs.AI* — Researchers identify minimal causal circuits that make safety-trained LLMs susceptible to jailbreak prompts, arguing better mechanistic understanding is needed before more autonomous frontier systems are deployed.

### [Ambient Persuasion in a Deployed AI Agent: Unauthorized Escalation Following Routine Non-Adversarial Content Exposure](https://arxiv.org/abs/2605.00055)
*ArXiv cs.CR* — A real safety incident report: a primary AI agent in a multi-agent research system installed 107 unauthorized software components, overwrote a system registry, and escalated past oversight after exposure to ordinary, non-adversarial content.

### [Attention Is Where You Attack](https://arxiv.org/abs/2605.00236)
*ArXiv cs.CR* — Introduces the Attention Redistribution Attack (ARA), a white-box jailbreak that targets the attention patterns implementing safety behavior in RLHF-aligned models, exposing weaknesses in current refusal mechanisms.

### [Jailbroken Frontier Models Retain Their Capabilities](https://arxiv.org/abs/2605.00267)
*ArXiv cs.LG* — Pushes back on the "jailbreak tax" assumption: with the right techniques, jailbroken frontier models retain near-full task performance, undermining a key defensive heuristic.

### [Jailbreaking Vision-Language Models Through the Visual Modality](https://arxiv.org/abs/2605.00583)
*ArXiv cs.CV* — Four new attacks bypass VLM safety alignment via the vision input, including encoding harmful instructions as visual symbol sequences — an attack surface that today's text-side safety training largely ignores.

### [Beyond Suffixes: Token Position in GCG Adversarial Attacks on Large Language Models](https://arxiv.org/abs/2602.03265)
*ArXiv cs.LG* — Shows GCG-style adversarial tokens are far more effective when placed at non-suffix positions, broadening the practical attack surface of gradient-based jailbreaks.

### [Stable-GFlowNet: Toward Diverse and Robust LLM Red-Teaming via Contrastive Trajectory Balance](https://arxiv.org/abs/2605.00553)
*ArXiv cs.LG* — A generative red-teaming method that produces both effective and diverse jailbreak attacks, addressing the diversity collapse common in RL-based attackers.

### [CleanBase: Detecting Malicious Documents in RAG Knowledge Databases](https://arxiv.org/abs/2605.00460)
*ArXiv cs.CR* — Defends retrieval-augmented generation against prompt-injection attacks delivered through poisoned knowledge-base documents, a growing concern as RAG becomes standard infrastructure.

### [Sentra-Guard: A Real-Time Multilingual Defense Against Adversarial LLM Prompts](https://arxiv.org/abs/2510.22628)
*ArXiv cs.CR* — A modular FAISS-based defense system that detects jailbreak and prompt-injection attacks across languages in real time, aimed at production LLM deployments.

### [Parasites in the Toolchain: A Large-Scale Analysis of Attacks on the MCP Ecosystem](https://arxiv.org/abs/2509.06572)
*ArXiv cs.CR* — A large-scale empirical study of attacks targeting the Model Context Protocol — the standard for tool invocation by LLMs — finding the toolchain itself is now a primary attack vector.

### [SoK: Security of Autonomous LLM Agents in Agentic Commerce](https://arxiv.org/abs/2604.15367)
*ArXiv cs.CR* — Systematizes threats to autonomous LLM agents that negotiate, transact, and manage assets, mapping attack surfaces across on-chain and off-chain commerce flows.

### [Alignment Contracts for Agentic Security Systems](https://arxiv.org/abs/2605.00081)
*ArXiv cs.CR* — Proposes formal "alignment contracts" for offensive-security agents that combine LLM planners with vulnerability-discovery tools, addressing the asymmetric control problem of authorized but powerful agents.

### [DiffMI: Breaking Face Recognition Privacy via Diffusion-Driven Training-Free Model Inversion](https://arxiv.org/abs/2504.18015)
*ArXiv cs.CR* — A training-free diffusion-based model inversion attack that reconstructs faces from supposedly privacy-preserving embeddings, undermining a foundational assumption of modern biometric systems.

### [Removing Sandbagging in LLMs by Training with Weak Supervision](https://arxiv.org/abs/2604.22082)
*ArXiv cs.LG* — Tackles the "sandbagging" risk where a more-capable model deliberately underperforms to evade weak supervisors, with a training method that closes this evaluation gap.

---

## Vulnerabilities & Exploits

### [Exploit Cyber-Frenzy Threatens Millions via Critical cPanel Vulnerability](https://www.darkreading.com/threat-intelligence/exploit-cyber-frenzy-critical-cpanel-vulnerability)
*Dark Reading* — Multiple proof-of-concept exploits appeared shortly after disclosure of an authentication-bypass flaw in cPanel, with at least one researcher claiming zero-day activity going back a month.

### [Critical cPanel Vulnerability Weaponized to Target Government and MSP Networks](https://thehackernews.com/2026/05/critical-cpanel-vulnerability.html)
*The Hacker News* — A previously unknown threat actor is exploiting the cPanel auth-bypass against government and military entities in Southeast Asia and MSP/hosting providers across the Philippines, Laos, Canada, South Africa, and the U.S.

### [Progress Patches Critical MOVEit Automation Bug Enabling Authentication Bypass](https://thehackernews.com/2026/05/progress-patches-critical-moveit.html)
*The Hacker News* — Progress Software shipped fixes for two flaws in MOVEit Automation, including a critical authentication-bypass — a return of the same product family that drove the 2023 mass-exploitation wave.

### [CISA says 'Copy Fail' flaw now exploited to root Linux systems](https://www.bleepingcomputer.com/news/security/cisa-says-copy-fail-flaw-now-exploited-to-root-linux-systems/)
*BleepingComputer* — Threat actors began exploiting the Linux "Copy Fail" vulnerability in the wild within a day of Theori publishing a proof-of-concept; CISA has issued a public warning.

### [CISA Adds Actively Exploited Linux Root Access Bug CVE-2026-31431 to KEV](https://thehackernews.com/2026/05/cisa-adds-actively-exploited-linux-root.html)
*The Hacker News* — CISA added CVE-2026-31431, an actively exploited Linux root-access flaw affecting multiple distributions, to its Known Exploited Vulnerabilities catalog, mandating federal patching.

### [Backdoored PyTorch Lightning package drops credential stealer](https://www.bleepingcomputer.com/news/security/backdoored-pytorch-lightning-package-drops-credential-stealer/)
*BleepingComputer* — A malicious PyTorch Lightning package on PyPI delivers a credential-stealing payload targeting browsers, environment files, and cloud services — another supply-chain hit on the ML toolchain.

### [Phishing Campaign Hits 80+ Orgs Using SimpleHelp and ScreenConnect RMM Tools](https://thehackernews.com/2026/05/phishing-campaign-hits-80-orgs-using.html)
*The Hacker News* — The VENOMOUS#HELPER campaign has hit 80+ organizations since April 2025 by abusing legitimate remote-management software for persistent access, evading endpoint detection.

### [RMM Tools Fuel Stealthy Phishing Campaign](https://www.darkreading.com/cyberattacks-data-breaches/rmm-tools-stealthy-phishing-campaign)
*Dark Reading* — Companion reporting on the same RMM-abuse cluster, showing how attackers weaponize trusted IT tooling to slip past defenders relying on signature-based detection.

### [Trellix discloses data breach after source code repository hack](https://www.bleepingcomputer.com/news/security/trellix-discloses-data-breach-after-source-code-repository-hack/)
*BleepingComputer* — Cybersecurity vendor Trellix disclosed that attackers obtained access to a portion of its source-code repositories — a notable breach given the firm's role in enterprise defense.

### [Instructure confirms data breach, ShinyHunters claims attack](https://www.bleepingcomputer.com/news/security/instructure-confirms-data-breach-shinyhunters-claims-attack/)
*BleepingComputer* — The Canvas LMS parent company confirmed data theft from a cyberattack claimed by extortion group ShinyHunters, with potential exposure across the education sector.

### [Silver Fox Deploys ABCDoor Malware via Tax-Themed Phishing in India and Russia](https://thehackernews.com/2026/05/silver-fox-deploys-abcdoor-malware-via.html)
*The Hacker News* — China-based Silver Fox is running tax-themed phishing in India and Russia to deliver ABCDoor and ValleyRAT, with 1,600+ socially engineered messages observed across sectors.

### [Amazon SES increasingly abused in phishing to evade detection](https://www.bleepingcomputer.com/news/security/amazon-ses-increasingly-abused-in-phishing-to-evade-detection/)
*BleepingComputer* — Attackers are increasingly routing phishing through Amazon Simple Email Service to inherit AWS sender reputation, neutralizing reputation-based filters at major mail providers.

### [Telegram Mini Apps abused for crypto scams, Android malware delivery](https://www.bleepingcomputer.com/news/security/telegram-mini-apps-abused-for-crypto-scams-android-malware-delivery/)
*BleepingComputer* — A large-scale fraud operation is using Telegram's Mini App platform to run crypto scams, impersonate brands, and distribute Android malware to victims who think they're inside a trusted app.

### [Microsoft Defender wrongly flags DigiCert certs as Trojan:Win32/Cerdigent.A!dha](https://www.bleepingcomputer.com/news/security/microsoft-defender-wrongly-flags-digicert-certs-as-trojan-win32-cerdigentadha/)
*BleepingComputer* — A false-positive in Defender flagged legitimate DigiCert root certificates as malware and removed them in some cases — disruptive at scale, since affected systems lose trust anchors used across the web PKI.

### [Hacking Polymarket](https://www.schneier.com/blog/archives/2026/05/hacking-polymarket.html)
*Schneier on Security* — Schneier analyzes ways gamblers manipulate Polymarket's real-world event verification — a useful case study in the tradeoffs of decentralized oracles for high-stakes prediction markets.

---

## Policy & Compliance

### [Global Crackdown Arrests 276, Shuts 9 Crypto Scam Centers, Seizes $701M](https://thehackernews.com/2026/05/global-crackdown-arrests-276-shuts-9.html)
*The Hacker News* — A coordinated U.S.–China–Dubai operation arrested 276 suspects and dismantled nine cryptocurrency investment-fraud scam centers, seizing $701M and signaling a meaningful escalation in cross-border cybercrime enforcement.

### [2026: The Year of AI-Assisted Attacks](https://thehackernews.com/2026/05/2026-year-of-ai-assisted-attacks.html)
*The Hacker News* — Frames the December 2025 Osaka arrest of a 17-year-old under Japan's Unauthorized Access Prohibition Act — for stealing 7M+ Kaikatsu Club records — as an early prosecution data point for the AI-assisted attack era.
