# Security Digest — 2026-05-23

A heavy news day on the operational side: CISA is still scrambling to contain a contractor-leaked credential trove while law enforcement dismantled a criminal VPN, seized 800 servers in the Netherlands, and arrested the alleged Kimwolf DDoS botmaster. Research-wise, the spotlight is on tool-augmented LLMs — MCP authentication, descriptor manipulation, and grammar-guided jailbreaks — alongside several new training-data extraction and watermarking results.

---

## AI Security Research

### [Autonomous LLM Agents & CTFs: A Second Look](https://arxiv.org/abs/2605.21497)
*ArXiv cs.CR.* Revisits recent claims of near-human CTF performance by LLM agents. The authors engineer increasingly complex agent architectures and find that headline success rates depend heavily on harness design, casting doubt on prior benchmarks.

### [Measuring Security Without Fooling Ourselves: Why Benchmarking Agents Is Hard](https://arxiv.org/abs/2605.22568)
*ArXiv cs.CR.* Identifies three structural weaknesses in current security-agent benchmarks — benchmark vulnerabilities, temporal staleness, and runtime uncertainty — and proposes directions toward more robust evaluations.

### [When Grammar Guides the Attack: Uncovering Control-Plane Vulnerabilities in LLMs with Structured Output](https://arxiv.org/abs/2503.24191)
*ArXiv cs.CR.* Shows that the grammar-guided decoding behind structured output APIs opens a new control-plane attack surface, distinct from traditional prompt-injection attacks on tool-using LLMs.

### [Semantic Attacks on Tool-Augmented LLMs: Securing the Model Context Protocol Against Descriptor-Level Manipulation](https://arxiv.org/abs/2512.06556)
*ArXiv cs.CR.* MCP deployments treat tool descriptors as trusted metadata, but adversarially crafted descriptors can steer agent behavior. Proposes defenses against descriptor-level injection in tool-augmented systems.

### [A First Measurement Study on Authentication Security in Real-World Remote MCP Servers](https://arxiv.org/abs/2605.22333)
*ArXiv cs.CR.* Empirical look at how authentication boundaries are (mis)implemented in deployed remote MCP servers connecting LLMs to user-linked online services. The picture is not flattering.

### [Adversarial Reframing: A Framework for Targeted Generation in Language Models](https://arxiv.org/abs/2605.21674)
*ArXiv cs.CR.* Introduces THREAT, a reasoning-driven jailbreak framework that coordinates multiple LLMs in an iterative loop to bypass safety filters via reframing and exploitation of adversarial tactics.

### [RADAR: Defending RAG Dynamically against Retrieval Corruption](https://arxiv.org/abs/2605.22041)
*ArXiv cs.CR.* RAG systems deployed against the live web face temporal volatility that amplifies adversarial risk. RADAR models reliable context selection as a graph problem, avoiding the storage blowup of static defenses.

### [LeakyCLIP: Extracting Training Data from CLIP](https://arxiv.org/abs/2508.00756)
*ArXiv cs.CR.* Demonstrates that contrastive image-text pretraining leaks memorized examples, extending training-data extraction attacks beyond diffusion models into multimodal embedding models.

### [Lost in Modality: Evaluating the Effectiveness of Text-Based Membership Inference Attacks on Large Multimodal Models](https://arxiv.org/abs/2512.03121)
*ArXiv cs.CR.* Log-probability-based MIAs translate poorly to multimodal models. The paper characterizes why text-only MIA signals weaken when the training data is image-text paired.

### [PEMark: Watermarking API Responses Based on Proxy Gateways and Position Encoding](https://arxiv.org/abs/2605.21865)
*ArXiv cs.CR.* Proposes a watermarking scheme that operates at the proxy-gateway layer rather than modifying database content or business logic, easing deployment for API abuse traceability.

### [Provable Robustness against Backdoor Attacks via the Primal-Dual Perspective on Differential Privacy](https://arxiv.org/abs/2605.21780)
*ArXiv cs.CR.* Extends randomized-smoothing certified robustness from evasion and poisoning to backdoor attacks, where training and test data are jointly perturbed, using a primal-dual DP analysis.

### [Frequency-Domain Regularized Adversarial Alignment for Transferable Attacks against Closed-Source MLLMs](https://arxiv.org/abs/2605.21541)
*ArXiv cs.CR.* Crafts transfer-based adversarial perturbations on open-source surrogate encoders that generalize to closed-source MLLMs by aligning frequency-domain visual focus across models.

---

## Vulnerabilities & Exploits

### [Trend Micro warns of Apex One zero-day exploited in the wild](https://www.bleepingcomputer.com/news/security/trend-micro-warns-of-apex-one-zero-day-exploited-in-attacks/)
*BleepingComputer.* Trend Micro has shipped fixes for an Apex One zero-day already used in active attacks against Windows systems; CISA followed by adding it to KEV the same week.

### [CISA Adds Exploited Langflow and Trend Micro Apex One Vulnerabilities to KEV](https://thehackernews.com/2026/05/cisa-adds-exploited-langflow-and-trend.html)
*The Hacker News.* CISA added CVE-2025-34291 (Langflow, CVSS 9.4 origin-validation flaw) and the Apex One zero-day to its Known Exploited Vulnerabilities catalog citing active exploitation.

### [Cisco Patches CVSS 10.0 Secure Workload REST API Flaw Enabling Data Access](https://thehackernews.com/2026/05/cisco-patches-cvss-100-secure-workload.html)
*The Hacker News.* CVE-2026-20223 (CVSS 10.0) lets an unauthenticated remote attacker reach sensitive data via insufficient REST API validation and authentication in Cisco Secure Workload.

### [Drupal: Critical SQL injection flaw now targeted in attacks](https://www.bleepingcomputer.com/news/security/drupal-critical-sql-injection-flaw-now-targeted-in-attacks/)
*BleepingComputer.* The "highly critical" SQL injection vulnerability Drupal disclosed earlier this week is now seeing exploitation attempts in the wild.

### [Ubiquiti patches three max severity UniFi OS vulnerabilities](https://www.bleepingcomputer.com/news/security/ubiquiti-patches-three-max-severity-unifi-os-vulnerabilities/)
*BleepingComputer.* Three maximum-severity UniFi OS flaws allow remote unauthenticated attackers to compromise affected devices; updates are available.

### [Megalodon GitHub Attack Targets 5,561 Repos with Malicious CI/CD Workflows](https://thehackernews.com/2026/05/megalodon-github-attack-targets-5561.html)
*The Hacker News.* An automated campaign pushed 5,718 commits across 5,561 repos in six hours, injecting GitHub Actions workflows with base64-encoded bash payloads that exfiltrate CI secrets — a clear supply-chain escalation pattern.

### [Making Vulnerable Drivers Exploitable Without Hardware — The BYOVD Perspective](https://thehackernews.com/2026/05/making-vulnerable-drivers-exploitable.html)
*The Hacker News.* Technical analysis of how Windows kernel-mode drivers can be reached from user mode without the original hardware, broadening the BYOVD attack surface for vulnerability research.

### [Lawmakers Demand Answers as CISA Tries to Contain Data Leak](https://krebsonsecurity.com/2026/05/lawmakers-demand-answers-as-cisa-tries-to-contain-data-leak/)
*Krebs on Security.* CISA is still struggling to invalidate the AWS GovCloud keys and internal secrets a contractor pushed to a public GitHub repo, while Congress opens its own inquiry.

### [CISA Security Leak](https://www.schneier.com/blog/archives/2026/05/cisa-security-leak.html)
*Schneier on Security.* Schneier's read on the CISA contractor leak: a public GitHub repo exposed credentials to multiple highly privileged AWS GovCloud accounts plus build, test, and deploy details for internal CISA systems.

### [First VPN Dismantled in Global Takedown Over Use by 25 Ransomware Groups](https://thehackernews.com/2026/05/first-vpn-dismantled-in-global-takedown.html)
*The Hacker News.* Authorities in Europe and North America, led by France and the Netherlands, dismantled "First VPN Service," used by 25 ransomware crews to obscure ransomware, data theft, scanning, and DDoS activity.

### [Netherlands seizes 800 servers of hosting firm enabling cyberattacks](https://www.bleepingcomputer.com/news/security/netherlands-seizes-800-servers-of-hosting-firm-enabling-cyberattacks/)
*BleepingComputer.* Dutch financial-crime investigators arrested two men and seized 800 servers tied to a hosting provider that knowingly enabled cyberattacks, interference operations, and disinformation campaigns.

### [Alleged Kimwolf Botmaster 'Dort' Arrested, Charged in U.S. and Canada](https://krebsonsecurity.com/2026/05/alleged-kimwolf-botmaster-dort-arrested-charged-in-u-s-and-canada/)
*Krebs on Security.* Canadian authorities arrested 23-year-old Jacob Butler in Ottawa, alleged operator of the Kimwolf IoT botnet (an AISURU variant) that enslaved nearly two million devices for DDoS-for-hire over the past six months.

### [Ghostwriter Targets Ukraine Government Entities with Prometheus Phishing Malware](https://thehackernews.com/2026/05/ghostwriter-targets-ukraine-government.html)
*The Hacker News.* Belarus-aligned UAC-0057 is sending phishing lures impersonating the Ukrainian Prometheus learning platform to government targets, per CERT-UA.

### [China's Webworm Uses Discord, Microsoft Graphs to Hack EU Governments](https://www.darkreading.com/endpoint-security/chinas-webworm-discord-microsoft-graphs)
*Dark Reading.* The APT group is abusing Discord and Microsoft Graph for command-and-control while relying on SoftEther VPN-based SOCKS proxies to tunnel between victim and operator.

### [Chain Reactions: How Nonce Collisions in ECDSA Compromise Polygon MEV Searchers](https://arxiv.org/abs/2605.21498)
*ArXiv cs.CR.* On-chain analysis reveals systematic ECDSA nonce reuse by Polygon MEV searchers — driven by latency pressure — that yields full private-key recovery.

### [Charge It to My Neighbor: A Relay Attack on ISO 15118 Plug and Charge Payment](https://arxiv.org/abs/2512.15966)
*ArXiv cs.CR.* Demonstrates a relay attack against ISO 15118 Plug-and-Charge: a fake charging station plugged into a victim's EV relays the cryptographic exchange to bill a different driver.

---

## Policy & Compliance

### [Trump pulls AI safety order after last-minute calls from Musk, Zuckerberg, and Sacks](https://the-decoder.com/trump-pulls-ai-safety-order-after-last-minute-calls-from-musk-zuckerberg-and-sacks/)
*The Decoder.* A planned executive order that would have set up a voluntary frontier-model review with a 90-day pre-release window was killed at the last minute following calls from Musk, Zuckerberg, and former advisor David Sacks.

### [Verizon DBIR: Healthcare Fends Off Increased Social Engineering Attacks](https://www.darkreading.com/cyber-risk/verizon-dbir-healthcare-fends-off-increased-social-engineering-attacks)
*Dark Reading.* The 2026 Data Breach Investigations Report highlights ransomware and vendor breaches as persistent threats and notes evolving social-engineering tactics making healthcare more vulnerable.

### [Former US execs plead guilty to aiding tech support scammers](https://www.bleepingcomputer.com/news/security/former-us-execs-plead-guilty-to-aiding-tech-support-scammers/)
*BleepingComputer.* Two former executives of a call-tracking and analytics firm pleaded guilty to concealing a multi-year tech-support fraud operation that victimized people worldwide.
