# Security Digest — 2026-04-16

April's Patch Tuesday dominated the week with a record-breaking 169 Microsoft CVEs including a SharePoint zero-day and a Windows Defender disclosure, while AI-specific threats intensified across jailbreak research, prompt injection, and supply-chain backdoors in agentic systems.

---

## AI Security Research

**[OpenAI Launches GPT-5.4-Cyber with Expanded Access for Security Teams](https://thehackernews.com/2026/04/openai-launches-gpt-54-cyber-with.html)**
*The Hacker News*
OpenAI unveiled GPT-5.4-Cyber, a variant of its flagship model optimized for defensive cybersecurity use cases, days after Anthropic's own frontier release. The model is being offered with expanded API access to security teams for vulnerability research and threat analysis.

**[Microsoft, Salesforce Patch AI Agent Data Leak Flaws](https://www.darkreading.com/cloud-security/microsoft-salesforce-patch-ai-agent-data-leak-flaws)**
*Dark Reading*
Prompt injection flaws in Salesforce Agentforce and Microsoft Copilot would have allowed external attackers to exfiltrate sensitive data through the agents' reasoning pipelines. Both vendors have shipped patches; the disclosures underscore the emerging attack surface introduced by enterprise AI agents.

**[Malice in Agentland: Down the Rabbit Hole of Backdoors in the AI Supply Chain](https://arxiv.org/abs/2510.05159)**
*ArXiv cs.AI*
Researchers show that fine-tuning AI agents on interaction data (web browsing, tool use) introduces critical supply-chain vulnerabilities, enabling adversaries to poison the data collection pipeline at multiple stages and embed hard-to-detect backdoors. The work highlights how capability improvements and security risks are tightly coupled in agentic AI systems.

**[TEMPLATEFUZZ: Fine-Grained Chat Template Fuzzing for Jailbreaking and Red Teaming LLMs](https://arxiv.org/abs/2604.12232)**
*ArXiv cs.AI*
A new fuzzing approach targets the chat template layer of LLMs — rather than prompt content — to bypass safety mechanisms without requiring expensive optimization. The technique exposes a systematic and under-explored attack surface in how model providers format system and user turns.

**[Every Picture Tells a Dangerous Story: Memory-Augmented Multi-Agent Jailbreak Attacks on VLMs](https://arxiv.org/abs/2604.12616)**
*ArXiv cs.AI*
This paper presents memory-augmented, multi-agent jailbreak strategies against Vision-Language Models that go beyond pixel perturbations to exploit cross-modal reasoning. The work argues that expanded modality support in modern VLMs has dramatically broadened the adversarial attack surface.

**[WebAgentGuard: A Reasoning-Driven Guard Model for Detecting Prompt Injection Attacks in Web Agents](https://arxiv.org/abs/2604.12284)**
*ArXiv cs.CR*
A guard model specifically designed for web agents detects adversarial instructions injected via HTML or rendered screenshots before they can hijack the agent's task execution. The authors demonstrate strong detection rates against prompt injection attacks embedded in realistic web environments.

**[Can we Watermark Low-Entropy LLM Outputs?](https://arxiv.org/abs/2604.12051)**
*ArXiv cs.CR*
This paper tackles a hard open problem: embedding provably undetectable watermarks in LLM outputs that have low randomness (code, factual answers), where prior token-distribution schemes fail. The proposed construction maintains output quality while enabling reliable attribution of model-generated text.

---

## Vulnerabilities & Exploits

**[Patch Tuesday, April 2026 Edition](https://krebsonsecurity.com/2026/04/patch-tuesday-april-2026-edition/)**
*Krebs on Security*
Microsoft fixed 167 vulnerabilities including a SharePoint Server zero-day and a publicly disclosed Windows Defender weakness dubbed "BlueHammer"; separately, Google Chrome patched its fourth zero-day of 2026 and Adobe Reader received an emergency fix for an actively exploited flaw. The month's patch load sets a new bar for volume.

**[Microsoft Issues Patches for SharePoint Zero-Day and 168 Other New Vulnerabilities](https://thehackernews.com/2026/04/microsoft-issues-patches-for-sharepoint.html)**
*The Hacker News*
Of the 169 CVEs addressed, 93 allow remote code execution and 8 are rated Critical; 11 are flagged as either publicly known or actively exploited at release time. Privilege escalation flaws account for more than half the total, reflecting a continued attacker focus on post-compromise lateral movement.

**[Actively Exploited nginx-ui Flaw (CVE-2026-33032) Enables Full Nginx Server Takeover](https://thehackernews.com/2026/04/critical-nginx-ui-vulnerability-cve.html)**
*The Hacker News*
CVE-2026-33032 (CVSS 9.8), dubbed MCPwn, is an authentication bypass in the nginx-ui management tool that grants full control over the Nginx service and is being actively exploited in the wild. Organizations using nginx-ui should apply patches or restrict network access immediately.

**[CISA flags Windows Task Host vulnerability as exploited in attacks](https://www.bleepingcomputer.com/news/security/cisa-flags-windows-task-host-vulnerability-as-exploited-in-attacks/)**
*BleepingComputer*
CISA added a Windows Task Host privilege escalation flaw to its Known Exploited Vulnerabilities catalog, warning federal agencies to patch before the deadline as it can be chained to achieve SYSTEM privileges. The advisory follows confirmed in-the-wild exploitation.

**[WordPress plugin suite hacked to push malware to thousands of sites](https://www.bleepingcomputer.com/news/security/wordpress-plugin-suite-hacked-to-push-malware-to-thousands-of-sites/)**
*BleepingComputer*
More than 30 plugins in the EssentialPlugin package were backdoored with malicious code granting unauthorized access to sites running them — a supply-chain compromise affecting thousands of WordPress installations. Site operators should audit plugin integrity and rotate credentials.

**[Signed software abused to deploy antivirus-killing scripts](https://www.bleepingcomputer.com/news/security/signed-software-abused-to-deploy-antivirus-killing-scripts/)**
*BleepingComputer*
A digitally signed adware tool was weaponized to drop payloads running with SYSTEM privileges that disabled endpoint antivirus protections across educational, utilities, government, and healthcare targets. The abuse of code-signing trust highlights how legitimate signatures alone are insufficient as a security control.

**[Crypto-exchange Kraken extorted by hackers after insider breach](https://www.bleepingcomputer.com/news/security/crypto-exchange-kraken-extorted-by-hackers-after-insider-breach/)**
*BleepingComputer*
A cybercrime group is threatening to release video footage of Kraken's internal systems containing client data unless a ransom is paid, following an insider-assisted breach. The incident underscores the risk of privileged insider access at high-value financial targets.

---

## Policy & Compliance

**[Audit: Big Tech Often Ignores CA Privacy Law Opt-Out Requests](https://www.darkreading.com/cyber-risk/audit-big-tech-ignores-data-collection-requests)**
*Dark Reading*
A privacy watchdog found that Google, Meta, and Microsoft comply with California opt-out-of-tracking requests only about half the time despite legal mandate. The findings are expected to inform ongoing California Privacy Protection Agency enforcement actions.

**[Microsoft Bets $10B to Boost Japan's AI, Cybersecurity](https://www.darkreading.com/cloud-security/microsoft-bets-10-billion-to-boost-japan-s-ai-cybersecurity)**
*Dark Reading*
Microsoft announced a $10 billion investment in Japan aimed at accelerating AI adoption, workforce training, and cybersecurity partnership development — part of a broader hyperscaler competition for sovereign AI infrastructure and data center contracts in the Asia-Pacific region.
