# Security Digest — 2026-05-06

A heavy day across the security stack: a critical Apache HTTP/2 RCE, a sprawling Instructure ed-tech breach, fresh supply-chain compromises (DAEMON Tools, Trellix source, ScarCruft on a gaming platform), and a wave of arXiv work probing LLM agent worms, memory-poisoning trojans, and the limits of refusal alignment.

---

## AI Security Research

### [SRTJ: Self-Evolving Rule-Driven Training-Free LLM Jailbreaking](https://arxiv.org/abs/2605.00974)
*ArXiv cs.CR* — A training-free jailbreak framework that systematically learns from both successful and failed attack attempts, evolving its rules to defeat aligned LLMs without gradient access. Targets a long-standing weakness in prior automated red-teaming: the inability to compound experience across attempts.

### [ContextualJailbreak: Evolutionary Red-Teaming via Simulated Conversational Priming](https://arxiv.org/abs/2605.02647)
*ArXiv cs.CR* — Automates multi-turn conversational priming attacks that hand-crafted scaffolds have consistently shown outperform single-turn jailbreaks. Closes the gap between cheap automation and the more powerful but labor-intensive human-authored attack patterns.

### [Logit-Gap Steering: A Forward-Pass Diagnostic for Alignment Robustness](https://arxiv.org/abs/2506.24056)
*ArXiv cs.CR* — Introduces the refusal-affirmation logit gap as a single scalar measuring the per-prompt safety margin RLHF actually buys; alignment widens the gap on 97.5–99.8% of toxic prompts, but the residual margin is small enough that targeted steering can flip refusals.

### [E-MIA: Exam-Style Black-Box Membership Inference Attacks against RAG Systems](https://arxiv.org/abs/2605.00955)
*ArXiv cs.CR* — Shows that an adversary with only black-box query access can reliably determine whether a candidate document was ingested into a RAG knowledge base, turning the retrieval corpus itself into a privacy-leakage surface for proprietary or sensitive documents.

### [Trojan Hippo: Weaponizing Agent Memory for Data Exfiltration](https://arxiv.org/abs/2605.01970)
*ArXiv cs.CR* — Characterizes a persistent memory attack in which a single untrusted tool call (e.g., a crafted email) plants a dormant payload in an LLM agent's long-term memory; the payload activates only on later innocuous-looking triggers, evading existing memory-poisoning defenses.

### [Autonomous LLM Agent Worms: Cross-Platform Propagation and Defense](https://arxiv.org/abs/2605.02812)
*ArXiv cs.CR* — First demonstration of LLM-agent worms that exploit persistent workspaces, scheduled tasks, and messaging integrations to propagate across agent installations. Attacker-influenced content written into agent state re-enters the decision context via autoloading and triggers cross-agent transmission.

### [Beyond Static Sandboxing: Learned Capability Governance for Autonomous AI Agents](https://arxiv.org/abs/2604.11839)
*ArXiv cs.CR* — Documents a 15× capability overprovisioning problem in current agent runtimes (a summarization task gets the same shell, subagent-spawn, and credential access as a deployment task) and proposes learned per-session capability governance as an alternative to static container sandboxes.

### [The Coding Limits of Robust Watermarking for Generative Models](https://arxiv.org/abs/2509.10577)
*ArXiv cs.CR* — Establishes information-theoretic bounds on how reliably a cryptographic watermark for generative output can survive adversarial corruption, via a minimal "zero-bit tamper-detection code" abstraction. Sets formal limits on what any watermark scheme can promise.

---

## Vulnerabilities & Exploits

### [Critical Apache HTTP/2 Flaw (CVE-2026-23918) Enables DoS and Potential RCE](https://thehackernews.com/2026/05/critical-apache-http2-flaw-cve-2026.html)
*The Hacker News* — Apache patched CVE-2026-23918 (CVSS 8.8) in the HTTP Server, a bug that can be driven from denial of service into remote code execution. Given Apache's footprint, expect rapid weaponization once PoCs surface.

### [DarkSword Malware](https://www.schneier.com/blog/archives/2026/05/darksword-malware.html)
*Schneier on Security* — Google TIG identified a sophisticated, likely state-built iOS full-chain exploit chaining multiple zero-days for full device compromise. Toolmarks in recovered payloads suggest a well-resourced government actor.

### [New stealthy Quasar Linux malware targets software developers](https://www.bleepingcomputer.com/news/security/new-stealthy-quasar-linux-malware-targets-software-developers/)
*BleepingComputer* — A previously undocumented Linux implant (QLNX) combining rootkit, backdoor, and credential-stealing capabilities is specifically targeting developer machines — a high-value pivot point into source repos and signing keys.

### [Instructure hacker claims data theft from 8,800 schools, universities](https://www.bleepingcomputer.com/news/security/instructure-hacker-claims-data-theft-from-8-800-schools-universities/)
*BleepingComputer* — A threat actor claims 280 million records exfiltrated from the education-tech giant covering 8,809 schools, districts, and online platforms. If verified, one of the largest education-sector breaches on record.

### [Trellix Source Code Breach Highlights Growing Supply Chain Threats](https://www.darkreading.com/cyberattacks-data-breaches/trellix-source-code-breach-supply-chain-threats)
*Dark Reading* — Source-code exposure at a major security vendor risks revealing where defensive controls live and how detections are built — a force multiplier for any attacker who later targets Trellix-protected environments.

### [DAEMON Tools Supply Chain Attack Compromises Official Installers with Malware](https://thehackernews.com/2026/05/daemon-tools-supply-chain-attack.html)
*The Hacker News* — Kaspersky reports trojanized installers signed with legitimate DAEMON Tools certificates have been served from the official site since April 8, dropping a backdoor on potentially thousands of systems.

### [ScarCruft Hacks Gaming Platform to Deploy BirdCall Malware on Android and Windows](https://thehackernews.com/2026/05/scarcruft-hacks-gaming-platform-to.html)
*The Hacker News* — North Korea–aligned APT37 trojanized components of a video game platform to deliver the BirdCall backdoor, likely targeting ethnic Koreans residing in China — a notable expansion of BirdCall to Android.

### [Weaver E-cology RCE Flaw CVE-2026-22679 Actively Exploited via Debug API](https://thehackernews.com/2026/05/weaver-e-cology-rce-flaw-cve-2026-22679.html)
*The Hacker News* — An unauthenticated RCE (CVSS 9.8) in the widely deployed Chinese enterprise OA platform has been under active exploitation since mid-March, with attackers running discovery commands at scale.

### [Microsoft Edge Stores Passwords in Process Memory, Posing Enterprise Risk](https://www.darkreading.com/cyber-risk/microsoft-edge-passwords-enterprise-risk)
*Dark Reading* — A PoC exploit shows an admin-privileged attacker can pull plaintext passwords from Edge process memory — a credential-harvesting primitive for any post-compromise toolkit.

### [Microsoft Details Phishing Campaign Targeting 35,000 Users Across 26 Countries](https://thehackernews.com/2026/05/microsoft-details-phishing-campaign.html)
*The Hacker News* — A multi-stage credential-theft campaign abused legitimate email services and code-of-conduct lures to steal authentication tokens, demonstrating how attackers continue to bypass reputation-based defenses.

### [We Scanned 1 Million Exposed AI Services. Here's How Bad the Security Actually Is](https://thehackernews.com/2026/05/we-scanned-1-million-exposed-ai.html)
*The Hacker News* — A large-scale internet scan of self-hosted LLM infrastructure finds widespread misconfiguration and weak authentication, suggesting the rush to internalize AI is opening security debt faster than teams can pay it down.

### [Vimeo data breach exposes personal information of 119,000 people](https://www.bleepingcomputer.com/news/security/vimeo-data-breach-exposes-personal-information-of-119-000-people/)
*BleepingComputer* — ShinyHunters claims responsibility for an April compromise affecting 119,000 Vimeo users, with notifications now flowing through Have I Been Pwned.

---

## Policy & Compliance

### [US government now has pre-release access to AI models from five major labs for national security testing](https://the-decoder.com/us-government-now-has-pre-release-access-to-ai-models-from-five-major-labs-for-national-security-testing/)
*The Decoder* — Google DeepMind, Microsoft, and xAI have joined Anthropic and OpenAI in agreements with the Center for AI Standards and Innovation, providing reduced-guardrail models for classified evaluation. A meaningful expansion of pre-deployment government oversight for frontier models.

### [Google now offers up to $1.5 million for some Android exploits](https://www.bleepingcomputer.com/news/security/google-now-offers-up-to-15-million-for-some-android-exploits/)
*BleepingComputer* — Google overhauled its Android and Chrome VRPs, raising top payouts to $1.5M for the hardest exploits while explicitly cutting bounties for classes of bugs that AI-assisted tooling now finds cheaply — an early signal of how AI is reshaping bug-bounty economics.

### [FTC to ban data broker Kochava from selling Americans' location data](https://www.bleepingcomputer.com/news/security/ftc-to-ban-data-broker-kochava-from-selling-americans-location-data/)
*BleepingComputer* — A proposed FTC settlement would bar Kochava and its CDS subsidiary from selling precise geolocation data without explicit consumer consent, resolving charges over data harvested from hundreds of millions of devices.

### [The global cybersecurity gap deepens as AI-powered attacks surge](https://restofworld.org/2026/ai-cybersecurity-anthropic-mythos/)
*Rest of World* — Restricted access to powerful defensive AI tools (e.g., Anthropic's Mythos) is widening the gap between well-resourced defenders and central banks, smaller firms, and nations in the Global South — a pattern that mirrors past asymmetries in cyber-defense capability.

### [Karakurt extortion gang 'cold case' negotiator gets 8.5 years in prison](https://www.bleepingcomputer.com/news/security/karakurt-extortion-gang-negotiator-sentenced-to-85-years-in-prison/)
*BleepingComputer* — A Latvian national extradited to the US received 8.5 years for his negotiator role in the Russia-linked Karakurt ransomware operation, continuing a slow but real trend of successful prosecutions of extortion-gang members.
