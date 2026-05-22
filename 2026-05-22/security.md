# Security Digest — 2026-05-22

A heavy day across the stack: actively exploited Microsoft Defender zero-days and a max-severity Cisco flaw on the vulnerability side, fresh details on the Nx/TanStack supply-chain blast radius, and a wave of AI-security research focused on jailbreaks, agent egress monitoring, and unlearning audits.

---

## AI Security Research

[REFLECTOR: Internalizing Step-wise Reflection against Indirect Jailbreak](https://arxiv.org/abs/2605.20654)
*ArXiv cs.LG* — Proposes a two-stage framework that bakes self-reflection into the generation trajectory itself to resist multi-step jailbreaks that bypass surface-level safety alignment by exploiting the internal generation process.

[LASH: Adaptive Semantic Hybridization for Black-Box Jailbreaking of Large Language Models](https://arxiv.org/abs/2605.21362)
*ArXiv cs.CL* — Existing automated jailbreak methods each commit to a single attack family and none dominates across targets; LASH hybridizes refinement loops, tree search, and mutation strategies adaptively, raising the bar for what aligned models must defend against.

[Towards Context-Invariant Safety Alignment for Large Language Models](https://arxiv.org/abs/2605.20994)
*ArXiv cs.CL* — Argues that robust safety requires invariance to surface form: models that refuse a harmful prompt directly but comply when the same intent is rewrapped reveal that preference-based alignment is brittle along the context axis.

[VIPER-MCP: Detecting and Exploiting Taint-Style Vulnerabilities in Model Context Protocol Servers](https://arxiv.org/abs/2605.21392)
*ArXiv cs.CR* — Because MCP servers expose shell execution, network, and filesystem operations to agent-driven invocation, taint-style flaws in tool handlers can turn natural-language input into RCE; VIPER-MCP automates discovery and exploitation across real servers.

[An Application-Layer Multi-Modal Covert-Channel Reference Monitor for LLM Agent Egress](https://arxiv.org/abs/2605.20734)
*ArXiv cs.CR* — Allowlists and content scanners miss covert channels in benign-looking payloads — zero-width characters, homoglyphs, JSON key ordering, timing, image LSBs. The paper builds a reference monitor that polices these channels on agent egress.

[Can Vision Models Truly Forget? Mirage: Representation-Level Certification of Visual Unlearning](https://arxiv.org/abs/2605.20282)
*ArXiv cs.CV* — Output-level "forgetting" metrics overstate unlearning in vertical federated vision models; Mirage's four representation-level diagnostics (linear probes, CKA, feature separability, layer-wise recovery) reveal information that survives.

[Detecting Trojaned DNNs via Spectral Regression Analysis](https://arxiv.org/abs/2605.21146)
*ArXiv cs.CR* — Iterative fine-tuning opens a backdoor-insertion window when training data isn't fully trusted. MIST detects Trojans by tracking how internal representations evolve across fine-tuning rather than reconstructing triggers.

[Auditing Apple's DifferentialPrivacy.framework: Implementation Bugs, Misconfigurations, and Practical Risks](https://arxiv.org/abs/2605.21378)
*ArXiv cs.CR* — First external audit of Apple's closed-source DP implementation, which protects Safari domains, keyboard events, and health signals; the authors find concrete bugs and misconfigurations that weaken the privacy claims Apple has made since 2016.

[Refusal Evaluation in Coding LLMs and Code Agents: A Systematic Review of Thirteen Malicious-Code Prompt Corpora (2023-2025)](https://arxiv.org/abs/2605.20351)
*ArXiv cs.CR* — Compares thirteen public corpora (AdvBench, CyberSecEval, RedCode, JailbreakBench, MalwareBench, others) used to evaluate code-LLM refusal, exposing how inconsistent construction protocols and licensing make cross-paper claims hard to trust.

[CTFExplorer: Evaluating LLM Offensive Agents Through Multi-Target Web CTF Benchmarking](https://arxiv.org/abs/2602.08023)
*ArXiv cs.CR* — Existing offensive-LLM benchmarks use single-target setups with known vulnerable services; CTFExplorer evaluates triage, target prioritization, and effort allocation across multi-target web CTFs, closer to how real attackers operate.

[Backchaining Loss of Control Mitigations from Mission-Specific Benchmarks in National Security](https://arxiv.org/abs/2605.21095)
*ArXiv cs.CR* — Argues defense/intelligence deployers should derive affordance and permission limits for AI systems by backchaining from mission-specific benchmarks rather than relying solely on generic safety cases or pre-deployment evals.

## Vulnerabilities & Exploits

[Microsoft warns of new Defender zero-days exploited in attacks](https://www.bleepingcomputer.com/news/security/microsoft-warns-of-new-defender-zero-days-exploited-in-attacks/)
*BleepingComputer* — Microsoft is pushing patches for two Defender flaws — a privilege escalation (CVE-2026-41091, CVSS 7.8) and a denial-of-service bug — that have been seen exploited in the wild. *(Also covered by [The Hacker News](https://thehackernews.com/2026/05/microsoft-warns-of-two-actively.html).)*

[Max severity Cisco Secure Workload flaw gives Site Admin privileges](https://www.bleepingcomputer.com/news/security/cisco-max-severity-secure-workload-flaw-gives-hackers-site-admin-privileges/)
*BleepingComputer* — Cisco shipped fixes for a maximum-severity vulnerability in Secure Workload that lets attackers escalate straight to Site Admin; patch immediately.

[Highly Critical Drupal Core Flaw Exposes PostgreSQL Sites to RCE Attacks](https://thehackernews.com/2026/05/highly-critical-drupal-core-flaw.html)
*The Hacker News* — Drupal pushed updates for a "highly critical" Core vulnerability allowing remote code execution, privilege escalation, or info disclosure on PostgreSQL-backed sites.

[9-Year-Old Linux Kernel Flaw Enables Root Command Execution on Major Distros](https://thehackernews.com/2026/05/9-year-old-linux-kernel-flaw-enables.html)
*The Hacker News* — CVE-2026-46333 (CVSS 5.5) is a long-undetected Linux kernel bug that, despite its modest score, lets attackers run commands as root on major distributions.

[GitHub Internal Repositories Breached via Malicious Nx Console VS Code Extension](https://thehackernews.com/2026/05/github-internal-repositories-breached.html)
*The Hacker News* — GitHub confirms the breach of 3,800 internal repositories traces back to an employee device poisoned by a malicious Nx Console build, itself the downstream effect of the TanStack npm supply-chain compromise. *(See also [BleepingComputer's GitHub→TanStack writeup](https://www.bleepingcomputer.com/news/security/github-links-repo-breach-to-tanstack-npm-supply-chain-attack/).)*

[Google accidentally exposed details of unfixed Chromium flaw](https://www.bleepingcomputer.com/news/security/google-accidentally-exposed-details-of-unfixed-chromium-flaw/)
*BleepingComputer* — Google inadvertently published details of an unpatched Chromium bug that keeps JavaScript running after the browser is closed, opening a path to remote code execution before the fix shipped.

[Google API Keys Remain Active After Deletion](https://www.darkreading.com/identity-access-management-security/google-api-keys-active-after-deletion)
*Dark Reading* — A researcher found Google Cloud API keys remain usable for ~23 minutes after deletion, contradicting Google's claim that deletion takes effect immediately.

[Chinese hackers target telcos with new Linux, Windows malware](https://www.bleepingcomputer.com/news/security/chinese-hackers-target-telcos-with-new-linux-windows-malware/)
*BleepingComputer* — A Chinese cyber-espionage campaign is hitting telecommunications providers with two newly identified implants — "Showboat" on Linux and "JFMBackdoor" on Windows. *(Also covered by [The Hacker News](https://thehackernews.com/2026/05/showboat-linux-malware-hits-middle-east.html) and [Dark Reading](https://www.darkreading.com/threat-intelligence/chinese-apts-linux-backdoor-telco-attacks).)*

[macOS Kernel Memory Corruption Exploit](https://www.schneier.com/blog/archives/2026/05/macos-kernel-memory-corruption-exploit.html)
*Schneier on Security* — A group used Anthropic's Mythos model to assist in discovering a kernel memory-corruption vulnerability and exploit on Apple's M5 — an early concrete case of frontier-LLM-assisted vulnerability research landing in the wild.

[Content Delivery Exploit Opens Websites to Brand Hijacking](https://www.darkreading.com/cyber-risk/content-delivery-exploit-websites-brand-hijacking)
*Dark Reading* — The "Underminr" domain-fronting technique lets attackers modify web requests through trusted CDNs, cloaking malicious traffic behind legitimate brand domains.

[Police seize "First VPN" service used in ransomware, data theft attacks](https://www.bleepingcomputer.com/news/security/police-seize-first-vpn-service-used-in-ransomware-data-theft-attacks/)
*BleepingComputer* — A joint international operation took down "First VPN," a service that had become infrastructure for ransomware and data-theft crews.

[Ukraine identifies infostealer operator tied to 28,000 stolen accounts](https://www.bleepingcomputer.com/news/security/ukraine-identifies-infostealer-operator-tied-to-28-000-stolen-accounts/)
*BleepingComputer* — Ukrainian cyberpolice, working with U.S. law enforcement, identified an 18-year-old in Odesa suspected of running an infostealer operation against users of a major online platform.

## Policy & Compliance

[How CISOs Should Prep for Agentic-Ready AI BOMs](https://www.darkreading.com/cyber-risk/how-cisos-should-prep-for-agentic-ready-ai-boms)
*Dark Reading* — Guidance on extending the AI bill of materials concept to cover not just component provenance but execution-time attributes, as agentic systems become harder to bound with static SBOM-style documentation.

[AI Agents Are Shifting Identity Security Budget Dynamics](https://www.darkreading.com/identity-access-management-security/shifting-budget-dynamics-identity-security-ai-agents)
*Dark Reading* — New Omdia research shows enterprises are reallocating identity-security budgets to cover the proliferation of AI agent identities, which need their own management, security, and governance regimes.

[US Cyber Command races to deploy AI on top-secret networks](https://the-decoder.com/us-cyber-command-races-to-deploy-ai-on-top-secret-networks/)
*The Decoder* — U.S. Cyber Command is accelerating AI deployment onto top-secret networks, signaling a shift in how national-security organizations are weighing the operational benefits of frontier AI against the classification and supply-chain risks of running it inside SCI environments.
