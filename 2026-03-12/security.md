# Security Digest — 2026-03-12

AI-generated malware has crossed from research into active ransomware campaigns, while critical RCEs in Veeam and n8n join a wave of breach disclosures — and researchers published a record volume of work on LLM jailbreaks, indirect prompt injection, and MCP protocol vulnerabilities.

---

## AI Security Research

**[AI-generated Slopoly malware used in Interlock ransomware attack](https://www.bleepingcomputer.com/news/security/ai-generated-slopoly-malware-used-in-interlock-ransomware-attack/)**
*BleepingComputer*
A new malware strain almost certainly built with generative AI allowed threat actor Hive0163 to persist on a compromised server for over a week and exfiltrate data as part of an Interlock ransomware operation — a concrete demonstration that AI-assisted malware development has moved into real attacks.

**[ADVERSA: Measuring Multi-Turn Guardrail Degradation and Judge Reliability in Large Language Models](https://arxiv.org/abs/2603.10068)**
*ArXiv cs.CR / cs.AI*
ADVERSA is an automated red-teaming framework that tracks how LLM safety guardrails erode across sustained adversarial dialogue, finding that most models exhibit measurable compliance drift long before a full jailbreak — a flaw missed by single-prompt evaluations.

**[Multi-Stream Perturbation Attack: Breaking Safety Alignment of Thinking LLMs Through Concurrent Task Interference](https://arxiv.org/abs/2603.10091)**
*ArXiv cs.CR / cs.AI*
Researchers show that chain-of-thought "thinking mode" LLMs are uniquely vulnerable: when subjected to multi-stream jailbreaks, the step-by-step reasoning process amplifies harmful detail rather than filtering it, representing a new attack surface specific to reasoning models.

**[Compatibility at a Cost: Systematic Discovery and Exploitation of MCP Clause-Compliance Vulnerabilities](https://arxiv.org/abs/2603.10163)**
*ArXiv cs.CR / cs.AI*
A systematic audit of the Model Context Protocol (MCP) standard uncovers clause-compliance loopholes that adversaries can exploit to redirect AI agents connected to external tools — raising supply-chain-style concerns for the growing ecosystem of MCP-based integrations.

**[AttriGuard: Defeating Indirect Prompt Injection in LLM Agents via Causal Attribution of Tool Invocations](https://arxiv.org/abs/2603.10749)**
*ArXiv cs.CR*
AttriGuard proposes causal attribution of tool calls as a defense against indirect prompt injection (IPI), going beyond input-level filtering to detect when malicious content embedded in tool outputs has actually influenced agent behavior — generalizing better to unseen payloads.

**[Shadow in the Cache: Unveiling and Mitigating Privacy Risks of KV-cache in LLM Inference](https://arxiv.org/abs/2508.09442)**
*ArXiv cs.CR / cs.AI*
The first comprehensive analysis of KV-cache privacy risks in LLM serving finds that cached attention states can leak sensitive context across tenants, with attacks viable in multi-tenant inference environments even without direct model access.

**[The Orthogonal Vulnerabilities of Generative AI Watermarks: A Comparative Empirical Benchmark](https://arxiv.org/abs/2603.10323)**
*ArXiv cs.CR / cs.CV*
A benchmark of invisible watermarking schemes for AI-generated imagery reveals that spatial-domain and latent-domain approaches have largely orthogonal attack surfaces — meaning a watermark robust to one class of attack is often trivially broken by the other.

**[Defensive Refusal Bias: How Safety Alignment Fails Cyber Defenders](https://arxiv.org/abs/2603.01246)**
*ArXiv cs.CR / cs.AI*
Safety-tuned frontier LLMs systematically refuse to assist legitimate security defenders on tasks involving malware analysis, exploit research, and vulnerability assessment — a complementary failure mode to misuse prevention that leaves blue teams without AI assistance.

---

## Vulnerabilities & Exploits

**[Veeam warns of critical flaws exposing backup servers to RCE attacks](https://www.bleepingcomputer.com/news/security/veeam-warns-of-critical-flaws-exposing-backup-servers-to-rce-attacks/)**
*BleepingComputer*
Veeam patched four critical remote code execution vulnerabilities in Backup & Replication; backup infrastructure is high-value ransomware pre-positioning territory and these flaws should be treated as urgent.

**[CISA Flags Actively Exploited n8n RCE Bug as 24,700 Instances Remain Exposed](https://thehackernews.com/2026/03/cisa-flags-actively-exploited-n8n-rce.html)**
*The Hacker News*
CISA added CVE-2025-68613 (CVSS 9.9) — a critical expression-injection RCE in the n8n workflow automation platform — to its Known Exploited Vulnerabilities catalog, with roughly 24,700 internet-exposed instances still unpatched.

**[Apple Issues Security Updates for Older iOS Devices Targeted by Coruna WebKit Exploit](https://thehackernews.com/2026/03/apple-issues-security-updates-for-older.html)**
*The Hacker News*
Apple backported a fix for CVE-2023-43010, a WebKit memory corruption flaw actively exploited by the Coruna exploit kit in cyberespionage and crypto-theft campaigns, to older iPhone and iPad models that missed the original patch.

**[Telus Digital confirms breach after hacker claims 1 petabyte data theft](https://www.bleepingcomputer.com/news/security/telus-digital-confirms-breach-after-hacker-claims-1-petabyte-data-theft/)**
*BleepingComputer*
Canadian BPO giant Telus Digital confirmed a security incident after threat actors claimed to have stolen close to 1 petabyte of data over a multi-month intrusion — one of the largest claimed data theft volumes disclosed this year.

**[Six Android Malware Families Target Pix Payments, Banking Apps, and Crypto Wallets](https://thehackernews.com/2026/03/six-android-malware-families-target-pix.html)**
*The Hacker News*
Researchers disclosed six new Android malware families — including PixRevolution, TaxiSpy RAT, BeatBanker, Mirax, Oblivion RAT, and SURXRAT — targeting Brazilian mobile banking users via overlay attacks on Pix instant payments and cryptocurrency wallets.

**[US disrupts SocksEscort proxy network powered by Linux malware](https://www.bleepingcomputer.com/news/security/us-disrupts-socksescort-proxy-network-powered-by-linux-malware/)**
*BleepingComputer*
A joint US-European law enforcement operation dismantled the SocksEscort proxy network, which was built exclusively from edge devices compromised by the AVRecon Linux malware and used to launder malicious traffic through residential IP space.

**[INC Ransomware Group Holds Healthcare Hostage in Oceania](https://www.darkreading.com/threat-intelligence/inc-ransomware-healthcare-oceania)**
*Dark Reading*
Government agencies, emergency clinics, and other healthcare organizations across Australia, New Zealand, and Tonga have been hit by the INC ransomware group, disrupting critical services in a region with limited incident-response capacity.

**[US charges another ransomware negotiator linked to BlackCat attacks](https://www.bleepingcomputer.com/news/security/us-charges-another-ransomware-negotiator-linked-to-blackcat-attacks/)**
*BleepingComputer*
The DOJ charged a second former DigitalMint employee for secretly partnering with the BlackCat (ALPHV) ransomware operation while posing as a neutral negotiator — part of an ongoing insider-scheme prosecution targeting the ransomware-negotiation industry.

---

## Policy & Compliance

**[Commercial Spyware Opponents Fear US Policy Shifting](https://www.darkreading.com/threat-intelligence/commercial-spyware-opponents-fear-us-policy-shifting)**
*Dark Reading*
Rescinded sanctions against NSO Group and reactivated government contracts have created widespread confusion about whether the Trump administration intends to enforce or abandon prior US restrictions on commercial spyware vendors.

**[iPhones and iPads Approved for NATO Classified Data](https://www.schneier.com/blog/archives/2026/03/iphones-and-ipads-approved-for-nato-classified-data.html)**
*Schneier on Security*
Apple announced that iPhone and iPad are now the first consumer devices certified for use with NATO restricted-level classified information out of the box — a significant milestone in government mobile device policy that no Android device has yet achieved.

**[Google paid $17.1 million for vulnerability reports in 2025](https://www.bleepingcomputer.com/news/google/google-paid-171-million-for-vulnerability-reports-in-2025/)**
*BleepingComputer*
Google distributed $17.1 million to 747 researchers through its Vulnerability Reward Program in 2025, continuing its trend of increasing payouts as a mechanism for proactive vulnerability discovery across its expanding product surface.
