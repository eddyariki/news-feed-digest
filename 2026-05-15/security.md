# Security Digest — 2026-05-15

A heavy day on the offensive side: a maximum-severity Cisco SD-WAN zero-day and an 18-year-old NGINX flaw landed alongside fresh BitLocker bypasses and another supply-chain hit that pulled OpenAI into the blast radius. On the research side, prompt injection, persistent agent compromise, and reasoning-extraction attacks dominated the new arXiv drops.

---

## AI Security Research

### [How Dangerous Is Anthropic's Mythos AI?](https://www.schneier.com/blog/archives/2026/05/how-dangerous-is-anthropics-mythos-ai.html)
*Schneier on Security* — Schneier examines Anthropic's decision to withhold Claude Mythos Preview from general release because of its vulnerability-discovery capability, arguing the model's offensive utility creates a real policy problem about who gets early access to dual-use capability.

### [How AI Hallucinations Are Creating Real Security Risks](https://thehackernews.com/2026/05/how-ai-hallucinations-are-creating-real.html)
*The Hacker News* — A walkthrough of how confidently wrong LLM outputs are propagating into critical-infrastructure decisions, with no internal mechanism for the model to flag its own uncertainty.

### [Sleeper Channels and Provenance Gates: Persistent Prompt Injection in Always-on Autonomous AI Agents](https://arxiv.org/abs/2605.13471)
*ArXiv cs.CR* — Studies how always-on agents like OpenClaw and Hermes Agent collapse messaging, memory, self-authored skills, scheduling, and shell into one authority boundary, opening "sleeper channel" attacks where injected directives persist across sessions.

### [Evaluation of Prompt Injection Defenses in Large Language Models](https://arxiv.org/abs/2604.23887)
*ArXiv cs.AI* — Builds an adaptive attacker that evolves over hundreds of rounds against nine defense configurations, showing existing prompt-injection mitigations degrade quickly under sustained pressure.

### [Quantifying LLM Safety Degradation Under Repeated Attacks Using Survival Analysis](https://arxiv.org/abs/2605.12869)
*ArXiv cs.AI* — Replaces binary jailbreak success/fail metrics with survival-analysis curves, giving a more realistic picture of how guardrails wear down across repeated adversarial interactions.

### [How to Steal Reasoning Without Reasoning Traces](https://arxiv.org/abs/2603.07267)
*ArXiv cs.CR* — Shows that hiding chain-of-thought traces is not enough to protect reasoning capability: an attacker can recover comparable reasoning behavior using only final answers and brief summaries.

### [BackFlush: Knowledge-Free Backdoor Detection and Elimination with Watermark Preservation in Large Language Models](https://arxiv.org/abs/2605.12529)
*ArXiv cs.CR* — Proposes a backdoor detection-and-removal pipeline for LLMs that does not require knowledge of the trigger and crucially preserves any legitimate watermarks already embedded in the model.

### [Do Skill Descriptions Tell the Truth? Detecting Undisclosed Security Behaviors in Code-Backed LLM Skills](https://arxiv.org/abs/2605.12875)
*ArXiv cs.CR* — Audits programmatic LLM "skills" and finds that natural-language descriptions routinely understate the security-relevant operations the implementation actually performs, creating a trust gap users and host LLMs both rely on.

### [SoK: Exposing the Generation and Detection Gaps in LLM-Generated Phishing](https://arxiv.org/abs/2508.21457)
*ArXiv cs.CR* — Systematization-of-knowledge paper mapping the asymmetry between how easily LLMs now produce convincing phishing content and how poorly current detectors handle it.

### [Tracking Conversations: Measuring Content and Identity Exposure on AI Chatbots](https://arxiv.org/abs/2604.27438)
*ArXiv cs.CR* — First systematic measurement study of advertising and analytics tracking inside AI chatbots, quantifying how much user content and identity is exposed to third parties through these interfaces.

## Vulnerabilities & Exploits

### [Cisco Catalyst SD-WAN Controller Auth Bypass Actively Exploited to Gain Admin Access](https://thehackernews.com/2026/05/cisco-catalyst-sd-wan-controller-auth.html)
*The Hacker News* — CVE-2026-20182, a CVSS 10.0 authentication-bypass flaw in Cisco Catalyst SD-WAN Controller's peering authentication, has been exploited in limited zero-day attacks to gain administrative access; patches are out.

### [OpenAI confirms security breach in TanStack supply chain attack](https://www.bleepingcomputer.com/news/security/openai-confirms-security-breach-in-tanstack-supply-chain-attack/)
*BleepingComputer* — Two OpenAI employee devices were compromised in the TanStack npm/PyPI supply-chain attack that affected hundreds of packages; OpenAI is rotating code-signing certificates as a precaution.

### [Windows 11 and Microsoft Edge hacked at Pwn2Own Berlin 2026](https://www.bleepingcomputer.com/news/security/windows-11-and-microsoft-edge-hacked-on-first-day-of-pwn2own-berlin-2026/)
*BleepingComputer* — Day one of Pwn2Own Berlin 2026 produced 24 unique zero-days and $523,000 in payouts, with successful exploits against Windows 11 and Microsoft Edge.

### [Zero-day exploit completely defeats default Windows 11 BitLocker protections](https://arstechnica.com/security/2026/05/zero-day-exploit-completely-defeats-default-windows-11-bitlocker-protections/)
*Ars Technica* — A still-unexplained exploit fully bypasses Windows 11's default BitLocker disk-encryption configuration; Microsoft says it is investigating but has not detailed the mechanism.

### [Windows Zero-Days Expose BitLocker Bypasses And CTFMON Privilege Escalation](https://thehackernews.com/2026/05/windows-zero-days-expose-bitlocker.html)
*The Hacker News* — The same anonymous researcher behind three earlier Defender bugs has disclosed two more zero-days, codenamed YellowKey: a BitLocker bypass and a privilege escalation in the Windows Collaborative Translation Framework (CTFMON).

### [18-Year-Old NGINX Rewrite Module Flaw Enables Unauthenticated RCE](https://thehackernews.com/2026/05/18-year-old-nginx-rewrite-module-flaw.html)
*The Hacker News* — A heap buffer overflow in `ngx_http_rewrite_module` (CVE-2026-42xxx), undetected for 18 years, enables unauthenticated remote code execution against NGINX Plus and NGINX Open. Disclosed by the depthfirst team.

### [New Fragnesia Linux Kernel LPE Grants Root Access via Page Cache Corruption](https://thehackernews.com/2026/05/new-fragnesia-linux-kernel-lpe-grants.html)
*The Hacker News* — Fragnesia (CVE-2026-46300) is the third Dirty Frag-family kernel LPE in two weeks, abusing page-cache corruption for local root; distros are pushing patches.

### [Stealer Backdoor Found in 3 Node-IPC Versions Targeting Developer Secrets](https://thehackernews.com/2026/05/stealer-backdoor-found-in-3-node-ipc.html)
*The Hacker News* — Socket and StepSecurity flagged malicious code in three published versions of the npm `node-ipc` package (9.1.6, 9.2.3, and one other) designed to exfiltrate developer credentials and secrets.

### [PraisonAI CVE-2026-44338 Auth Bypass Targeted Within Hours of Disclosure](https://thehackernews.com/2026/05/praisonai-cve-2026-44338-auth-bypass.html)
*The Hacker News* — A missing-authentication flaw (CVSS 7.3) in the PraisonAI multi-agent orchestration framework was being actively scanned and exploited within four hours of public disclosure.

### [KongTuke hackers now use Microsoft Teams for corporate breaches](https://www.bleepingcomputer.com/news/security/kongtuke-hackers-now-use-microsoft-teams-for-corporate-breaches/)
*BleepingComputer* — Initial-access broker KongTuke has shifted to Microsoft Teams for social-engineering, with reported time-to-persistent-access on corporate networks as low as five minutes.

### ['FrostyNeighbor' APT Carefully Targets Govt Orgs in Poland, Ukraine](https://www.darkreading.com/cyberattacks-data-breaches/frostyneighbor-apt-govt-orgs-poland-ukraine)
*Dark Reading* — Belarussian nation-state group FrostyNeighbor uniquely fingerprints victims before delivering tailored spear-phishing payloads aimed at espionage against Polish and Ukrainian government organizations.

### [Iranian hackers targeted major South Korean electronics maker](https://www.bleepingcomputer.com/news/security/iranian-hackers-targeted-major-south-korean-electronics-maker/)
*BleepingComputer* — Iran-linked MuddyWater (a.k.a. Seedworm, Static Kitten) ran a broad espionage campaign hitting at least nine high-profile organizations across multiple sectors and countries, including a major South Korean electronics manufacturer.

### [West Pharmaceutical says hackers stole data, encrypted systems](https://www.bleepingcomputer.com/news/security/west-pharmaceutical-says-hackers-stole-data-encrypted-systems/)
*BleepingComputer* — West Pharmaceutical Services disclosed a cyberattack involving both data exfiltration and system encryption, the latest large pharma manufacturer to confirm a ransomware-style intrusion.
