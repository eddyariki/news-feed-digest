# Security Digest — 2026-04-21

Third-party AI tool compromise drove the week's biggest breach story as Vercel's systems were accessed via a compromised Context.ai employee OAuth token, illustrating how AI tooling is rapidly becoming a high-value lateral-movement vector. Simultaneously, researchers disclosed critical RCE vulnerabilities in AI inference infrastructure and novel jailbreak techniques targeting large reasoning models.

---

## AI Security Research

**[SGLang CVE-2026-5760 (CVSS 9.8) Enables RCE via Malicious GGUF Model Files](https://thehackernews.com/2026/04/sglang-cve-2026-5760-cvss-98-enables.html)**
*The Hacker News*
A critical command-injection vulnerability in the SGLang LLM serving framework allows remote code execution through maliciously crafted GGUF model files. The near-perfect CVSS score reflects unauthenticated exploitability against any system serving models with SGLang.

**[Anthropic MCP Design Vulnerability Enables RCE, Threatening AI Supply Chain](https://thehackernews.com/2026/04/anthropic-mcp-design-vulnerability.html)**
*The Hacker News*
Researchers identified a "by design" weakness in the Model Context Protocol architecture that can cascade into arbitrary command execution across any vulnerable MCP implementation. The flaw raises supply chain concerns as MCP adoption grows across AI tooling ecosystems.

**[LogJack: Indirect Prompt Injection Through Cloud Logs Against LLM Debugging Agents](https://arxiv.org/abs/2604.15368)**
*ArXiv cs.CR*
This benchmark of 42 payloads demonstrates that LLM debugging agents consuming cloud logs can be hijacked via injected log content, with verbatim command execution rates varying widely across eight foundation models tested. The attack surface is a natural consequence of agents with both read-log and execute-remediation permissions.

**[Too Private to Tell: Practical Token Theft Attacks on Apple Intelligence](https://arxiv.org/abs/2604.15637)**
*ArXiv cs.CR*
Researchers probed Apple Intelligence's two-stage anonymous access token mechanism and found practical weaknesses that allow token theft, undermining Apple's privacy-first security claims. The paper provides a detailed analysis of the issuance flow and exploitation conditions.

**[Reasoning-targeted Jailbreak Attacks on Large Reasoning Models via Semantic Triggers and Psychological Framing](https://arxiv.org/abs/2604.15725)**
*ArXiv cs.AI*
Novel jailbreaks exploit the reasoning chain itself rather than final outputs in large reasoning models, injecting harmful content into intermediate thinking steps. Prior safety evaluations that only checked final answers left this attack surface entirely unmeasured.

**[Jailbreak Scaling Laws for Large Language Models: Polynomial-Exponential Crossover](https://arxiv.org/abs/2603.11331)**
*ArXiv cs.AI*
Adversarial prompt-injection attacks amplify jailbreak success rates from slow polynomial growth to exponential growth with inference-time sampling, revealing a dangerous scaling dynamic for models deployed with repeated sampling. The analysis identifies a minimal statistical mechanism explaining both regimes.

**[SoK: Security of Autonomous LLM Agents in Agentic Commerce](https://arxiv.org/abs/2604.15367)**
*ArXiv cs.CR*
A systematization-of-knowledge paper mapping the security landscape for autonomous LLM agents operating in commerce — including on-chain/off-chain transactions, digital asset management, and emerging agent payment protocols like ERC-8004 and AP2. Covers attack surfaces unique to machine-actor economics that existing threat models do not address.

**[HarmfulSkillBench: How Do Harmful Skills Weaponize Your Agents?](https://arxiv.org/abs/2604.15415)**
*ArXiv cs.AI*
A new benchmark evaluating how publicly available, reusable agent skills (hosted on platforms like ClawHub) can be misused for cyber attacks, fraud, and privacy violations — a gap left open by research focused only on prompt injection within skills.

---

## Vulnerabilities & Exploits

**[Vercel Breach Tied to Context AI Hack Exposes Limited Customer Credentials](https://thehackernews.com/2026/04/vercel-breach-tied-to-context-ai-hack.html)**
*The Hacker News*
Attackers compromised Context.ai, then used the resulting OAuth token to hijack a Vercel employee's Google Workspace account and gain access to internal Vercel systems. The incident is part of a pattern of OAuth token theft as a lateral movement technique, described by researchers as "the new attack surface."

**[Researchers Detect ZionSiphon Malware Targeting Israeli Water, Desalination OT Systems](https://thehackernews.com/2026/04/researchers-detect-zionsiphon-malware.html)**
*The Hacker News*
ZionSiphon is purpose-built malware that establishes persistence, tampers with local config files, and scans for OT-relevant services on the local subnet of Israeli water treatment facilities. The targeting of critical water infrastructure continues a multi-year trend of nation-state interest in physical-process disruption.

**[The Gentlemen Ransomware Now Uses SystemBC for Bot-Powered Attacks](https://www.bleepingcomputer.com/news/security/the-gentlemen-ransomware-now-uses-systembc-for-bot-powered-attacks/)**
*BleepingComputer*
A 1,570-host SystemBC proxy botnet, believed composed largely of corporate victims, was discovered backing a Gentlemen ransomware affiliate campaign. The combination of a commercial proxy malware framework with a ransomware gang affiliate model signals increasing operational professionalism.

**[Microsoft: Teams Increasingly Abused in Helpdesk Impersonation Attacks](https://www.bleepingcomputer.com/news/security/microsoft-teams-increasingly-abused-in-helpdesk-impersonation-attacks/)**
*BleepingComputer*
Threat actors are exploiting Microsoft Teams' external collaboration capabilities to impersonate IT helpdesk staff and gain initial access, then pivot using legitimate built-in tools. The abuse of trusted enterprise communication channels makes these attacks harder for users to recognize as malicious.

**[Serial-to-IP Devices Hide Thousands of Old and New Bugs](https://www.darkreading.com/ics-ot-security/serial-ip-devices-thousands-of-bugs)**
*Dark Reading*
OT-to-Internet translation devices are riddled with both legacy and newly discovered vulnerabilities, and are being targeted for attacks with increasing frequency. The devices' role as protocol bridges makes them a high-value pivot point for attackers seeking access to industrial systems.

**[Apple Account Change Alerts Abused to Send Phishing Emails](https://www.bleepingcomputer.com/news/security/apple-account-change-alerts-abused-to-send-phishing-emails/)**
*BleepingComputer*
Attackers are embedding phishing lures inside legitimate Apple account-change notification emails sent from Apple's own servers, bypassing spam filters by hitchhiking on Apple's infrastructure. The technique increases credibility of fake iPhone purchase scams substantially.

**[British Scattered Spider Hacker Pleads Guilty to Crypto Theft Charges](https://www.bleepingcomputer.com/news/security/british-scattered-spider-hacker-pleads-guilty-to-crypto-theft-charges/)**
*BleepingComputer*
The believed leader of the Scattered Spider cybercrime collective pleaded guilty to wire fraud and aggravated identity theft in the United States. Scattered Spider is known for sophisticated social engineering attacks against major enterprises and cryptocurrency platforms.

**[A Reality Check on SBOM-based Vulnerability Management](https://arxiv.org/abs/2511.20313)**
*ArXiv cs.CR*
A large-scale empirical study across 2,414 open-source repositories reveals that both SBOM generation and vulnerability scanning suffer from significant inaccuracies that undermine the tool's practical security value. The paper proposes using lock files with strong package managers as a more reliable foundation.

---

## Policy & Compliance

**[NIST to Stop Rating Non-Priority Flaws Due to Volume Increase](https://www.bleepingcomputer.com/news/security/nist-to-stop-rating-non-priority-flaws-due-to-volume-increase/)**
*BleepingComputer*
The National Institute of Standards and Technology will discontinue assigning CVSS severity scores to lower-priority vulnerabilities as submission volumes have grown beyond sustainable processing capacity. The change has downstream implications for any organization or toolchain that relies on NVD enrichment for automated triage.

**[PolicyGapper: Automated Detection of Inconsistencies Between Google Play Data Safety Sections and Privacy Policies Using LLMs](https://arxiv.org/abs/2604.16128)**
*ArXiv cs.CR*
A new LLM-based tool automatically detects gaps and contradictions between Android app developers' Data Safety Section declarations and their actual privacy policies, addressing a compliance challenge that manual review cannot scale to. The research has direct implications for privacy regulators and app marketplace oversight.
