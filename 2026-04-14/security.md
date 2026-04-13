# Security Digest — 2026-04-14

AI-powered cyberattack capabilities are the dominant theme today, headlined by Anthropic withholding its Mythos Preview model over autonomous zero-day exploitation; meanwhile, an unusually dense crop of active exploits, supply chain incidents, and nation-state campaigns keeps defenders busy across the rest of the landscape.

---

## AI Security Research

[On Anthropic's Mythos Preview and Project Glasswing](https://www.schneier.com/blog/archives/2026/04/on-anthropics-mythos-preview-and-project-glasswing.html)
*Schneier on Security*
Anthropic is withholding its new Claude Mythos Preview model from public release due to its autonomous cyberattack capabilities and has launched Project Glasswing to proactively scan public and proprietary software for vulnerabilities before the model proliferates. Bruce Schneier examines the precedent this sets for responsible AI deployment.

[Your MTTD Looks Great. Your Post-Alert Gap Doesn't](https://thehackernews.com/2026/04/your-mttd-looks-great-your-post-alert.html)
*The Hacker News*
Anthropic's Mythos Preview autonomously found and exploited zero-days across every major OS and browser before being restricted; Palo Alto's Wendi Whitmore warns similar capabilities are weeks away from broad proliferation. With eCrime breakout time now averaging 29 minutes, the piece argues that detection metrics are masking a critical response gap.

[Re-Mask and Redirect: Exploiting Denoising Irreversibility in Diffusion Language Models](https://arxiv.org/abs/2604.08557)
*arXiv cs.CL / cs.AI*
Safety-aligned diffusion LLMs commit refusal tokens in the first 8–16 of 64 denoising steps and treat those commitments as permanent — a fragile assumption a trivial two-step intervention can shatter, bypassing alignment entirely.

[GRM: Utility-Aware Jailbreak Attacks on Audio LLMs via Gradient-Ratio Masking](https://arxiv.org/abs/2604.09222)
*arXiv cs.SD / cs.AI*
Existing audio jailbreak methods sacrifice transcription quality for attack success; GRM introduces gradient-ratio masking to preserve utility while maintaining attack potency, exposing a more practical threat model for audio LLMs.

[Mosaic: Multimodal Jailbreak against Closed-Source VLMs via Multi-View Ensemble Optimization](https://arxiv.org/abs/2604.09253)
*arXiv cs.CV / cs.AI*
Mosaic transfers adversarial multimodal jailbreaks from open-source surrogates to closed-source vision-language models via a multi-view ensemble, showing that black-box VLMs are more vulnerable to cross-model transfer than previously reported.

[BadSkill: Backdoor Attacks on Agent Skills via Model-in-Skill Poisoning](https://arxiv.org/abs/2604.09378)
*arXiv cs.CR / cs.AI*
Third-party agent skills that bundle learned model artifacts create a supply-chain attack surface where a benign-looking skill can conceal malicious backdoor behavior — a risk not captured by prompt injection or plugin misuse defenses.

[Kill-Chain Canaries: Stage-Level Tracking of Prompt Injection Across Attack Surfaces and Model Safety Tiers](https://arxiv.org/abs/2603.28013)
*arXiv cs.CR / cs.AI / cs.LG*
Rather than a binary succeed/fail metric, this methodology tracks a cryptographic canary through four kill-chain stages (EXPOSED → PERSISTED → EXFILTRATED → EXECUTED) to give multi-agent system architects actionable diagnostic data for hardening pipelines.

[Exploiting Web Search Tools of AI Agents for Data Exfiltration](https://arxiv.org/abs/2510.09093)
*arXiv cs.CR / cs.CL*
Indirect prompt injection through RAG and web-search tool calls can redirect LLM agents to exfiltrate sensitive corporate data; the paper maps the attack surface and evaluates current mitigations.

[Leave My Images Alone: Preventing Multi-Modal LLMs from Analyzing Images via Visual Prompt Injection](https://arxiv.org/abs/2604.09024)
*arXiv cs.CV / cs.CR / cs.AI*
ImageProtector proposes a user-side visual prompt injection technique that proactively prevents open-weight MLLMs from extracting identity, location, or other private details from personal images at scale.

[Large Language Models Generate Harmful Content Using a Distinct, Unified Mechanism](https://arxiv.org/abs/2604.09544)
*arXiv cs.CL / cs.AI / cs.LG*
Targeted weight pruning reveals that LLMs organize harmfulness generation through a coherent internal structure, explaining why jailbreaks and narrow fine-tuning both induce broad emergent misalignment — the safeguards are fragile precisely because they overlay a unified harm-generation pathway.

[RansomTrack: A Hybrid Behavioral Analysis Framework for Ransomware Detection](https://arxiv.org/abs/2604.08739)
*arXiv cs.CR / cs.LG*
RansomTrack combines static and dynamic behavioral analysis to detect ransomware before encryption completes, addressing the seconds-scale window that makes early-stage detection the only viable intervention.

---

## Vulnerabilities & Exploits

[Adobe rolls out emergency fix for Acrobat, Reader zero-day flaw](https://www.bleepingcomputer.com/news/security/adobe-rolls-out-emergency-fix-for-acrobat-reader-zero-day-flaw/)
*BleepingComputer*
Adobe patched CVE-2026-34621 in an out-of-band update after confirming attackers have been delivering maliciously crafted PDFs exploiting the flaw since at least December 2025 — a four-month dwell before a fix arrived.

[OpenAI rotates macOS certs after Axios attack hit code-signing workflow](https://www.bleepingcomputer.com/news/security/openai-rotates-macos-certs-after-axios-attack-hit-code-signing-workflow/)
*BleepingComputer*
A GitHub Actions workflow used to sign OpenAI's macOS apps downloaded a malicious Axios package during a March 31 supply chain attack, prompting OpenAI to rotate all potentially exposed code-signing certificates; no user data was accessed.

[APT41 Delivers 'Zero-Detection' Backdoor to Harvest Cloud Credentials](https://www.darkreading.com/cloud-security/apt41-zero-detection-backdoor-harvest-cloud-credentials)
*Dark Reading*
The China-backed APT41 group is actively targeting AWS, Google Cloud, Azure, and Alibaba environments with a backdoor designed to evade endpoint detection, using typosquatting domains to obscure command-and-control traffic.

[North Korea's APT37 Uses Facebook Social Engineering to Deliver RokRAT Malware](https://thehackernews.com/2026/04/north-koreas-apt37-uses-facebook-social.html)
*The Hacker News*
ScarCruft (APT37) befriended targets on Facebook before pivoting to deliver the RokRAT remote access trojan, marking a notable expansion from spear-phishing to long-term social platform trust-building as an initial access vector.

[FBI and Indonesian Police Dismantle W3LL Phishing Network Behind $20M Fraud Attempts](https://thehackernews.com/2026/04/fbi-and-indonesian-police-dismantle.html)
*The Hacker News*
Joint U.S.–Indonesian enforcement seized the W3LL phishing-kit platform and arrested its alleged developer in the first coordinated takedown between the two countries targeting a phishing kit author, disrupting infrastructure behind over $20 million in attempted fraud.

[Critical flaw in wolfSSL library enables forged certificate use](https://www.bleepingcomputer.com/news/security/critical-flaw-in-wolfssl-library-enables-forged-certificate-use/)
*BleepingComputer*
A critical vulnerability in the widely embedded wolfSSL TLS library allows improper ECDSA signature verification — specifically failing to validate the hash algorithm or its size — potentially letting attackers present forged certificates as legitimate.

[The silent "Storm": New infostealer hijacks sessions, decrypts server-side](https://www.bleepingcomputer.com/news/security/the-silent-storm-new-infostealer-hijacks-sessions-decrypts-server-side/)
*BleepingComputer*
The "Storm" infostealer skips local credential decryption entirely, shipping raw browser data to attacker-controlled servers for server-side decryption — a technique that enables session hijacking while bypassing both passwords and MFA.

[New Booking.com data breach forces reservation PIN resets](https://www.bleepingcomputer.com/news/security/new-bookingcom-data-breach-forces-reservation-pin-resets/)
*BleepingComputer*
Booking.com confirmed unauthorized access to systems exposing sensitive reservation and user data, forcing a platform-wide PIN reset for affected reservations.

[Stolen Rockstar Games analytics data leaked by extortion gang](https://www.bleepingcomputer.com/news/security/stolen-rockstar-games-analytics-data-leaked-by-extortion-gang/)
*BleepingComputer*
The ShinyHunters extortion gang published analytics data stolen from Rockstar Games via a breach at third-party analytics provider Anodot, illustrating ongoing supply-chain exposure through vendor relationships.

[JanelaRAT Malware Targets Latin American Banks with 14,739 Attacks in Brazil in 2025](https://thehackernews.com/2026/04/janelarat-malware-targets-latin.html)
*The Hacker News*
A modified BX RAT variant continues targeting financial and cryptocurrency accounts in Brazil and Mexico, logging keystrokes, capturing screenshots, and stealing financial data from specific banking entities.

---

## Policy & Compliance

[Empty Attestations: OT Lacks the Tools for Cryptographic Readiness](https://www.darkreading.com/ics-ot-security/ot-lacks-tools-cryptographic-readiness)
*Dark Reading*
Regulators are requiring OT asset owners to attest to post-quantum cryptographic readiness, but the tooling to actually assess or achieve that readiness does not exist for most operational technology environments — turning compliance paperwork into security theater.
