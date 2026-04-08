# Security Digest — 2026-04-08

AI-native threats dominate today's landscape: Anthropic's Project Glasswing debuts autonomous vulnerability discovery, while researchers document a wave of injection and supply-chain attacks targeting LLM agents — and nation-state actors continue exploiting unpatched routers and containers at scale.

---

## AI Security Research

**[A new Anthropic model found security problems 'in every major operating system and web browser'](https://www.theverge.com/ai-artificial-intelligence/908114/anthropic-project-glasswing-cybersecurity)**
*The Verge AI*
Anthropic's Project Glasswing, a cybersecurity-focused model built with Nvidia, Google, AWS, Apple, and Microsoft, autonomously flagged vulnerabilities across major OSes and browsers with virtually no human intervention.

**[Anthropic debuts preview of powerful new AI model Mythos in new cybersecurity initiative](https://techcrunch.com/2026/04/07/anthropic-mythos-ai-model-preview-security/)**
*TechCrunch AI*
The Mythos model preview is being deployed by a small group of high-profile companies for defensive cybersecurity work, marking a significant step toward AI-driven autonomous security operations.

**[Cybersecurity in the Age of Instant Software](https://www.schneier.com/blog/archives/2026/04/cybersecurity-in-the-age-of-instant-software.html)**
*Schneier on Security*
Bruce Schneier examines how AI's ability to generate custom software on demand transforms the economics of patching: when software is ephemeral and bespoke, traditional vulnerability management models may break down entirely.

**[Flowise AI Agent Builder Under Active CVSS 10.0 RCE Exploitation; 12,000+ Instances Exposed](https://thehackernews.com/2026/04/flowise-ai-agent-builder-under-active.html)**
*The Hacker News*
A maximum-severity remote code execution flaw in the popular Flowise open-source AI platform is being actively exploited in the wild, with over 12,000 internet-exposed instances at risk.

**[Grafana Patches AI Bug That Could Have Leaked User Data](https://www.darkreading.com/application-security/grafana-patches-ai-bug-leaked-user-data)**
*Dark Reading*
Attackers could embed malicious instructions on a web page to manipulate Grafana's AI assistant into exfiltrating sensitive user data to an attacker-controlled server — a prompt injection attack in a production observability platform.

**[ShieldNet: Network-Level Guardrails against Emerging Supply-Chain Injections in Agentic Systems](https://arxiv.org/abs/2604.04426)**
*ArXiv cs.AI*
Proposes a network-layer defense framework for LLM agents that monitors third-party tool and API interactions to block supply-chain injection attacks that bypass input/output-level defenses.

**[CoopGuard: Stateful Cooperative Agents Safeguarding LLMs Against Evolving Multi-Round Attacks](https://arxiv.org/abs/2604.04060)**
*ArXiv cs.AI*
Introduces a multi-agent monitoring architecture where cooperative guard agents maintain conversational state to detect adversarial attacks that evolve across multiple rounds of interaction.

**[Mapping the Exploitation Surface: A 10,000-Trial Taxonomy of What Makes LLM Agents Exploit Vulnerabilities](https://arxiv.org/abs/2604.04561)**
*ArXiv cs.AI*
A large-scale empirical study of 10,000 trials identifies specific system-prompt features that reliably trigger or suppress vulnerability exploitation by LLM agents — providing a concrete taxonomy for safer agent deployment.

**[Your Agent is More Brittle Than You Think: Uncovering Indirect Injection Vulnerabilities in Agentic LLMs](https://arxiv.org/abs/2604.03870)**
*ArXiv cs.CL*
Systematically documents indirect prompt injection vulnerabilities in agentic LLM systems, showing that agents are far more susceptible to manipulation through retrieved content than typically assumed.

**[ClawSafety: "Safe" LLMs, Unsafe Agents](https://arxiv.org/abs/2604.01438)**
*ArXiv cs.AI*
Demonstrates that safety-tuned LLMs can still be weaponized when deployed as personal agents (e.g., OpenClaw) with elevated local privileges — a single successful prompt injection can leak credentials or execute arbitrary commands.

**[Mind Your HEARTBEAT! Claw Background Execution Inherently Enables Silent Memory Pollution](https://arxiv.org/abs/2603.23064)**
*ArXiv cs.AI*
Identifies a critical vulnerability in heartbeat-driven background execution in Claw personal AI agents, where untrusted content encountered during autonomous background tasks can silently corrupt agent memory.

**[Agentic AI Security: Threats, Defenses, Evaluation, and Open Challenges](https://arxiv.org/abs/2510.23883)**
*ArXiv cs.AI*
A comprehensive survey of agentic AI security covering prompt injection, tool misuse, memory poisoning, and multi-agent collusion — with evaluation benchmarks and open research challenges.

**[SecPI: Secure Code Generation with Reasoning Models via Security Reasoning Internalization](https://arxiv.org/abs/2604.03587)**
*ArXiv cs.AI*
Addresses persistent security vulnerabilities in code generated by reasoning language models by internalizing security-aware reasoning patterns during training, reducing critical CWE introductions in generated code.

---

## Vulnerabilities & Exploits

**[Russian State-Linked APT28 Exploits SOHO Routers in Global DNS Hijacking Campaign](https://thehackernews.com/2026/04/russian-state-linked-apt28-exploits.html)**
*The Hacker News*
APT28 (Forest Blizzard) has compromised insecure MikroTik and TP-Link routers, reconfiguring them to hijack DNS and intercept credentials — a campaign consistent with the Krebs-reported Microsoft Office token theft.

**[Russia Hacked Routers to Steal Microsoft Office Tokens](https://krebsonsecurity.com/2026/04/russia-hacked-routers-to-steal-microsoft-office-tokens/)**
*Krebs on Security*
Russian intelligence operatives exploited home and office routers to intercept Microsoft Office authentication tokens, enabling persistent access to enterprise environments without triggering standard credential alerts.

**[Docker CVE-2026-34040 Lets Attackers Bypass Authorization and Gain Host Access](https://thehackernews.com/2026/04/docker-cve-2026-34040-lets-attackers.html)**
*The Hacker News*
A high-severity flaw in Docker Engine allows attackers to bypass authorization plugins under specific conditions, potentially granting host-level access from within containers.

**[China-Linked Storm-1175 Exploits Zero-Days to Rapidly Deploy Medusa Ransomware](https://thehackernews.com/2026/04/china-linked-storm-1175-exploits-zero.html)**
*The Hacker News*
The financially motivated Storm-1175 threat actor chained zero-day and N-day vulnerabilities to deploy Medusa ransomware at unprecedented speed, leaving defenders little time to respond between initial access and encryption.

**[New GPUBreach Attack Enables Full CPU Privilege Escalation via GDDR6 Bit-Flips](https://thehackernews.com/2026/04/new-gpubreach-attack-enables-full-cpu.html)**
*The Hacker News*
Academic research demonstrates multiple RowHammer-style attacks against GDDR6 GPU memory that can be leveraged to escalate privileges all the way to the host CPU — a novel cross-component attack surface.

**[Snowflake Customers Hit in Data Theft Attacks after SaaS Integrator Breach](https://www.bleepingcomputer.com/news/security/snowflake-customers-hit-in-data-theft-attacks-after-saas-integrator-breach/)**
*BleepingComputer*
More than a dozen companies suffered data theft after a SaaS integration provider was compromised and authentication tokens stolen, once again highlighting the risks of third-party identity chains.

**[Over 1,000 Exposed ComfyUI Instances Targeted in Cryptomining Botnet Campaign](https://thehackernews.com/2026/04/over-1000-exposed-comfyui-instances.html)**
*The Hacker News*
Attackers are actively scanning for internet-exposed ComfyUI instances to enlist them in a cryptocurrency mining and proxy botnet, exploiting the platform's lack of authentication in default configurations.

**[FBI: Americans Lost a Record $21 Billion to Cybercrime Last Year](https://www.bleepingcomputer.com/news/security/fbi-americans-lost-a-record-21-billion-to-cybercrime-last-year/)**
*BleepingComputer*
The FBI reports a record $21 billion in losses to cyber-enabled crime in the US last year, led by investment scams, business email compromise, tech support fraud, and data breaches.

---

## Policy & Compliance

**[Hong Kong Police Can Force You to Reveal Your Encryption Keys](https://www.schneier.com/blog/archives/2026/04/hong-kong-police-can-force-you-to-reveal-your-encryption-keys.html)**
*Schneier on Security*
A new Hong Kong law grants police the authority to compel individuals — including airport transit passengers — to disclose encryption keys for devices such as computers, phones, and hard drives.
