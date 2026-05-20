# Security Digest — 2026-05-20

Supply-chain and zero-day pressure dominated the day: a fresh Shai-Hulud npm wave hit 600+ packages while a tagged-but-rewritten GitHub Action quietly redirected CI/CD traffic, and Microsoft Exchange picked up an unpatched OWA XSS under active attack. On the research side, several new papers probed how agentic AI dissolves longstanding security assumptions — from clarification-driven prompt injection to monitor-evasion benchmarks.

---

## AI Security Research

[The End of Trust: How Agentic AI Breaks Security Assumptions](https://arxiv.org/abs/2605.16436) — *ArXiv cs.CR*. Argues that the historical attacker tradeoff between deception fidelity and scale collapses once agents can impersonate convincingly at machine speed, forcing a rethink of identity, trust, and authentication primitives.

[SLEIGHT-Bench: A Benchmark of Evasion Attacks Against Agent Monitors](https://arxiv.org/abs/2605.16626) — *ArXiv cs.CR*. Introduces a benchmark for LLM-on-LLM monitoring, measuring how reliably coding agents can slip dangerous actions past supervisory models meant to catch misaligned behavior.

[New Wide-Net-Casting Jailbreak Attacks Risk Large Models](https://arxiv.org/abs/2605.17128) — *ArXiv cs.CR*. Identifies a previously unexplored jailbreak scenario in which an adversary queries a population of frontier models simultaneously, exploiting variance across systems rather than targeting a single one.

[ASPI: Seeking Ambiguity Clarification Amplifies Prompt Injection Vulnerability in LLM Agents](https://arxiv.org/abs/2605.17324) — *ArXiv cs.CR*. Shows that the very "ask-before-acting" behavior treated as a safety property opens a new prompt-injection surface: attackers can hijack clarification turns to coerce agent decisions.

[Asking Back: Interaction-Layer Antidistillation Watermarks](https://arxiv.org/abs/2605.16462) — *ArXiv cs.CR*. Proposes watermark defenses that operate at the interaction layer rather than on output tokens, aimed at catching unauthorized distillation of a deployed LLM API by an attacker with no logit access.

[STRIDE-AI: A Threat Modeling Framework for Generative AI Security Assessment](https://arxiv.org/abs/2605.17163) — *ArXiv cs.CR*. Extends classical STRIDE threat modeling to cover probabilistic AI failure modes — model inversion, data poisoning, prompt injection — that deterministic methodologies miss.

[Ablating Safety: Mechanisms for Removing Alignment in Language Models for Security Applications](https://arxiv.org/abs/2605.17413) — *ArXiv cs.CR*. Investigates which internal mechanisms produce over-refusal on legitimate defensive-security tasks and how to selectively ablate them without broader misuse risk.

## Vulnerabilities & Exploits

[Microsoft Exchange Zero-Day Under Attack, No Patch Available](https://www.darkreading.com/vulnerabilities-threats/microsoft-exchange-zero-day-no-patch) — *Dark Reading*. CVE-2026-42897, a cross-site scripting flaw in Outlook Web Access, is being exploited in the wild with no fix shipped; attackers can compromise OWA mailboxes directly through the bug.

[Windows Zero-Day Barrage Continues After Patch Tuesday](https://www.darkreading.com/cyberattacks-data-breaches/windows-zero-day-barrage-continues-after-patch-tuesday) — *Dark Reading*. A single researcher has now disclosed three more Windows zero-days — YellowKey, GreenPlasma, and MiniPlasma — extending a six-week streak of unpatched vulnerabilities revealed publicly.

[DirtyDecrypt PoC Released for Linux Kernel CVE-2026-31635 LPE Vulnerability](https://thehackernews.com/2026/05/dirtydecrypt-poc-released-for-linux.html) — *The Hacker News*. Working exploit code is now public for a recently patched Linux kernel privilege-escalation bug discovered by Zellic and V12, which turned out to duplicate an earlier reported issue.

[New Shai-Hulud malware wave compromises 600 npm packages](https://www.bleepingcomputer.com/news/security/new-shai-hulud-malware-wave-compromises-600-npm-packages/) — *BleepingComputer*. Threat actors published more than 600 malicious packages to npm in a fresh wave of the self-replicating Shai-Hulud supply-chain campaign, with credential exfiltration as the payload.

[Popular GitHub Action Tags Redirected to Imposter Commit to Steal CI/CD Credentials](https://thehackernews.com/2026/05/github-actions-supply-chain-attack.html) — *The Hacker News*. Every tag on the widely used actions-cool/issues-helper repository was silently moved to point at an imposter commit that harvests CI/CD secrets, a particularly stealthy variant of the tag-pinning attack class.

[Compromised Nx Console 18.95.0 Targeted VS Code Developers with Credential Stealer](https://thehackernews.com/2026/05/compromised-nx-console-18950-targeted.html) — *The Hacker News*. A trojanized release of the 2.2M-install Nx Console extension reached the VS Code Marketplace, shipping a credential stealer to developers across VS Code, Cursor, and JetBrains.

[SEPPMail Secure E-Mail Gateway Vulnerabilities Enable RCE and Mail Traffic Access](https://thehackernews.com/2026/05/seppmail-secure-e-mail-gateway.html) — *The Hacker News*. Critical bugs in the SEPPMail appliance allow remote code execution and unrestricted reading of mail traffic, turning the security gateway itself into an entry vector into internal networks.

['Claw Chain' Vulnerabilities Threaten OpenClaw Deployments](https://www.darkreading.com/application-security/claw-chain-vulnerabilities-threaten-openclaw) — *Dark Reading*. Now-patched flaws in the fast-growing OpenClaw AI agent framework chained together to let attackers steal credentials, escalate privileges, and persist inside agentic deployments.

[Microsoft Self-Service Password Reset abused in Azure data theft attacks](https://www.bleepingcomputer.com/news/security/microsoft-self-service-password-reset-abused-in-azure-data-theft-attacks/) — *BleepingComputer*. A threat actor is chaining legitimate M365 and Azure administration features — including self-service password reset — to exfiltrate data from production tenants without triggering classic IOC patterns.

[7-Eleven confirms data breach claimed by the ShinyHunters gang](https://www.bleepingcomputer.com/news/security/7-eleven-confirms-data-breach-claimed-by-the-shinyhunters-gang/) — *BleepingComputer*. The convenience-store chain has now acknowledged the intrusion that ShinyHunters publicly claimed last month, joining the long list of recent extortion-group disclosures.

[The New Phishing Click: How OAuth Consent Bypasses MFA](https://thehackernews.com/2026/05/the-new-phishing-click-how-oauth.html) — *The Hacker News*. The EvilTokens PhaaS platform compromised 340+ Microsoft 365 organizations in five weeks by tricking users into completing legitimate device-code flows that grant attacker apps full OAuth scope — MFA included.

[Drupal to Release Urgent Core Security Updates on May 20, Sites Told to Prepare](https://thehackernews.com/2026/05/drupal-to-release-urgent-core-security.html) — *The Hacker News*. The Drupal Security Team is shipping an out-of-band core release for every supported branch this evening and warns operators that exploits may appear within hours.

## Policy & Compliance

[Japan to strengthen cyber defense for critical infrastructure](https://www.japantimes.co.jp/news/2026/05/19/japan/cyber-defense-measures/) — *The Japan Times*. Cybersecurity minister Hisashi Matsumoto laid out plans to build the "world's highest" cyber resilience, focusing on critical infrastructure protections amid an escalating regional threat environment.

[Japan's Mythos response 'must involve Big Tech,' says LDP cybersecurity chief](https://www.japantimes.co.jp/business/2026/05/19/tech/japan-mythos-response-interview/) — *The Japan Times*. With Anthropic restricting Mythos access to a small set of vetted partners, Japan's ruling-party cybersecurity lead argues that national defensive use of the model requires coordinated engagement with major platform providers.

[INTERPOL 'Operation Ramz' seizes 53 malware, phishing servers](https://www.bleepingcomputer.com/news/security/interpol-operation-ramz-seizes-53-malware-phishing-servers/) — *BleepingComputer*. A coordinated takedown across the Middle East and North Africa led to more than 200 arrests and 53 malicious server seizures, one of the larger regional cybercrime operations of the year.

[CISA Exposes Secrets, Credentials in 'Private' Repo](https://www.darkreading.com/cybersecurity-operations/cisa-exposes-secrets-credentials-private-repo) — *Dark Reading*. A CISA GitHub repository ironically named "Private-CISA" has been publicly accessible since November 2025, leaking secrets and credentials from the very agency that issues secure-development guidance.

[Is 2026 the Year AI Bills of Materials Get Real?](https://www.darkreading.com/cyber-risk/is-2026-year-ai-bills-of-materials-get-real) — *Dark Reading*. Surveys how AI BOMs are crystallizing as a risk-management primitive — what they should contain, where they fit alongside SBOMs, and which regulators are starting to expect them.

[FBI: Americans lost over $388 million to scams using crypto ATMs in 2025](https://www.bleepingcomputer.com/news/security/fbi-americans-lost-over-388-million-to-scams-using-crypto-atms-in-2025/) — *BleepingComputer*. The FBI's latest tally on Bitcoin-ATM-mediated fraud is fueling renewed calls for kiosk-operator KYC requirements and state-level licensing reforms.

[Discord rolls out end-to-end encryption on voice, video calls](https://www.bleepingcomputer.com/news/security/discord-rolls-out-end-to-end-encryption-on-voice-video-calls/) — *BleepingComputer*. Discord now applies E2EE by default to all voice and video calls, a notable industry move on consumer messaging cryptography that will shape ongoing lawful-access debates.
