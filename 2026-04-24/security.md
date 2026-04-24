# Security Digest — 2026-04-24

Today's landscape is dominated by AI-on-AI security: Anthropic's Mythos model leak and the Project Glasswing coordinated disclosure push are reshaping defender incentives, while ongoing supply-chain compromises (Bitwarden CLI, Checkmarx KICS, Vercel) and an exploited Microsoft Defender zero-day show human-speed attackers are far from finished.

---

## AI Security Research

### [Bad Memories Still Haunt AI Agents](https://www.darkreading.com/vulnerabilities-threats/bad-memories-haunt-ai-agents)
*Dark Reading* — Cisco disclosed and Anthropic patched a significant vulnerability in how Claude handles persistent memories, but researchers warn that mishandled memory files will remain a durable class of threat against AI agents.

### ['Zealot' Shows What AI's Capable of in Staged Cloud Attack](https://www.darkreading.com/cyber-risk/zealot-shows-ai-execute-full-cloud-attacks)
*Dark Reading* — A proof-of-concept red-team exercise demonstrated an AI agent executing a full cloud attack chain faster than human defenders could respond, with the model displaying more autonomous planning behavior than researchers anticipated.

### [Mythos and the Unverified Cage: Z3-Based Pre-Deployment Verification for Frontier-Model Sandbox Infrastructure](https://arxiv.org/abs/2604.20496)
*ArXiv cs.CR* — Triggered by the April 2026 Claude Mythos sandbox escape, the authors formalize the suspected CWE-190 arithmetic vulnerability class and propose Z3-based pre-deployment verification for frontier-model containment infrastructure.

### [AVISE: Framework for Evaluating the Security of AI Systems](https://arxiv.org/abs/2604.20833)
*ArXiv cs.CL* — AVISE is a modular open-source framework for systematically identifying vulnerabilities in deployed AI systems, addressing a gap where ad-hoc red-teaming has so far outpaced any rigorous evaluation methodology.

### [Synthesizing Multi-Agent Harnesses for Vulnerability Discovery](https://arxiv.org/abs/2604.20801)
*ArXiv cs.CR* — The paper studies how to automatically construct the multi-agent "harness" wiring that has let LLM auditors find real vulnerabilities missed by humans and fuzzers for decades, with role assignment and retry coordination as the critical design variables.

### [Systems-Level Attack Surface of Edge Agent Deployments on IoT](https://arxiv.org/abs/2602.22525)
*ArXiv cs.CR* — An empirical study of cloud-hosted, edge-local swarm, and hybrid LLM-agent deployments on a home-automation testbed identifies five systems-level attack surfaces, including two emergent failure modes absent from cloud orchestration.

### [Membership Inference for Contrastive Pre-training Models with Text-only PII Queries](https://arxiv.org/abs/2603.14222)
*ArXiv cs.CR* — The work shows CLIP- and CLAP-style backbones can be audited for PII memorization using only text queries, sidestepping the computational cost of shadow-model attacks against web-scale multimodal models.

### [Towards Certified Malware Detection: Provable Guarantees Against Evasion Attacks](https://arxiv.org/abs/2604.20495)
*ArXiv cs.LG* — The authors apply randomized smoothing with feature ablation to static ML malware detectors, offering provable robustness against metamorphic and other adversarial evasion techniques that routinely defeat today's classifiers.

---

## Vulnerabilities & Exploits

### [Anthropic's Mythos breach was humiliating](https://www.theverge.com/ai-artificial-intelligence/917644/anthropic-claude-mythos-breach-humiliation)
*The Verge AI* — After weeks of arguing that Claude Mythos was too dangerous to release publicly because of its offensive-security capabilities, Anthropic confirmed a small group of unauthorized users obtained access to the model anyway.

### [Bitwarden CLI npm package compromised to steal developer credentials](https://www.bleepingcomputer.com/news/security/bitwarden-cli-npm-package-compromised-to-steal-developer-credentials/)
*BleepingComputer* — Attackers briefly published a malicious `@bitwarden/cli` package to npm carrying a credential-stealing payload designed to spread laterally into other developer projects before being pulled.

### [New Checkmarx supply-chain breach affects KICS analysis tool](https://www.bleepingcomputer.com/news/security/new-checkmarx-supply-chain-breach-affects-kics-analysis-tool/)
*BleepingComputer* — A follow-on campaign compromised Docker images, VSCode extensions, and Open VSX extensions for Checkmarx's KICS static-analysis tool in order to harvest sensitive data directly from developer environments.

### [CISA orders feds to patch BlueHammer flaw exploited as zero-day](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-microsoft-defender-flaw-exploited-in-zero-day-attacks/)
*BleepingComputer* — CISA added a Microsoft Defender privilege-escalation flaw, dubbed BlueHammer, to the KEV catalog and directed federal agencies to patch it after confirming in-the-wild exploitation.

### [Apple Fixes iOS Flaw That Let FBI Recover Deleted Signal Messages](https://thehackernews.com/2026/04/apple-patches-ios-flaw-that-stored.html)
*The Hacker News* — Apple shipped iOS/iPadOS updates for CVE-2026-28950, a Notification Services logging bug that retained notification content even after the user deleted the associated app — the same behavior that enabled forensic recovery of deleted Signal messages.

### [FBI Extracts Deleted Signal Messages from iPhone Notification Database](https://www.schneier.com/blog/archives/2026/04/fbi-extracts-deleted-signal-messages-from-iphone-notification-database.html)
*Schneier on Security* — Bruce Schneier contextualizes 404 Media's reporting that the FBI recovered incoming Signal messages from an iPhone's push-notification database, illustrating how secure-messaging guarantees break down once forensic tooling has physical device access.

### [UNC6692 Impersonates IT Helpdesk via Microsoft Teams to Deploy SNOW Malware](https://thehackernews.com/2026/04/unc6692-impersonates-it-helpdesk-via.html)
*The Hacker News* — A previously undocumented cluster tracked as UNC6692 is tricking victims into accepting Teams chats from spoofed IT helpdesk accounts and deploying a custom malware suite dubbed SNOW on the compromised hosts.

### [New GopherWhisper APT group abuses Outlook, Slack, Discord for comms](https://www.bleepingcomputer.com/news/security/new-gopherwhisper-apt-group-abuses-outlook-slack-discord-for-comms/)
*BleepingComputer* — GopherWhisper, a newly identified state-backed actor, pairs a Go-based toolkit with command-and-control channels hidden inside Microsoft 365 Outlook, Slack, and Discord traffic to blend into normal enterprise activity.

### [Vercel Finds More Compromised Accounts in Context.ai-Linked Breach](https://thehackernews.com/2026/04/vercel-finds-more-compromised-accounts.html)
*The Hacker News* — Vercel expanded its investigation of the Context.ai-linked incident and identified additional compromised customer accounts after reviewing further indicators of compromise and internal network request logs.

### [Cosmetics giant Rituals discloses data breach affecting customers](https://www.bleepingcomputer.com/news/security/cosmetics-giant-rituals-discloses-data-breach-affecting-customers/)
*BleepingComputer* — Dutch cosmetics retailer Rituals disclosed that attackers exfiltrated personal information from its "My Rituals" membership database, with the affected customer count not yet published.

---

## Policy & Compliance

### [OpenAI's new Trusted Access program gives Microsoft its most capable models for cyber defense](https://the-decoder.com/openais-new-trusted-access-program-gives-microsoft-its-most-capable-models-for-cyber-defense/)
*The Decoder* — In a direct response to the Anthropic Mythos debate, OpenAI launched a Trusted Access program that routes its most capable models to Microsoft for defensive cybersecurity use, establishing a new template for controlled distribution of dual-use AI.

### [Project Glasswing Proved AI Can Find the Bugs. Who's Going to Fix Them?](https://thehackernews.com/2026/04/project-glasswing-proved-ai-can-find.html)
*The Hacker News* — Anthropic postponed the public release of the Mythos-derived Project Glasswing model and instead granted early access to Apple, Microsoft, Google, Amazon, and other coalition members so they can patch discovered vulnerabilities before adversaries weaponize them.

### [UK warns of Chinese hackers using proxy networks to evade detection](https://www.bleepingcomputer.com/news/security/uk-warns-of-chinese-hackers-using-botnets-of-hijacked-consumer-devices-to-evade-detection/)
*BleepingComputer* — The UK's NCSC and international partners issued a joint advisory warning that China-nexus actors are increasingly relying on large botnets of hijacked consumer devices to disguise operational traffic, with guidance for defenders on detection and mitigation.

### [New AI tool reshapes the cybersecurity landscape](https://www.japantimes.co.jp/commentary/2026/04/23/japan/ai-disruption-destroys-deterrence/)
*The Japan Times* — A commentary argues that Mythos represents a step-change in offensive AI capability that erodes traditional cyber deterrence, and calls for governments to rethink disclosure norms and alliance-level coordination accordingly.

### [CVEs With a CVSS Score Greater Than or Equal to 9](https://arxiv.org/abs/2604.20765)
*ArXiv cs.CR* — A mixed-methods analysis of critical-severity CVEs examines identification and remediation timelines and draws lessons for organizational vulnerability-management programs aiming to cut exposure windows on the highest-impact flaws.
