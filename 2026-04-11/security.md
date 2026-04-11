# Security Digest — 2026-04-11

LLM-era threats dominated today's security landscape: researchers published a wave of papers on jailbreaks, prompt injection, and supply-chain attacks targeting AI agents, while real-world incidents ranged from a sensitive healthcare data breach to a supply-chain compromise of a popular developer toolchain.

---

## AI Security Research

**[Break Me If You Can: Self-Jailbreaking of Aligned LLMs via Lexical Insertion Prompting](https://arxiv.org/abs/2601.02670)**
*ArXiv cs.CL*

Researchers introduce "self-jailbreaking," a threat model in which an aligned LLM guides its own compromise using only its internal knowledge — no external red-team model required. The technique operationalizes the attack via lexical insertion prompts, raising the bar for what alignment must defend against.

**[TrajGuard: Streaming Hidden-state Trajectory Detection for Decoding-time Jailbreak Defense](https://arxiv.org/abs/2604.07727)**
*ArXiv cs.CR*

Existing jailbreak defenses focus on static prompt or output inspection; TrajGuard instead monitors the hidden-state trajectory during decoding to catch risk signals as they evolve, plugging a blind spot left by current defense systems.

**[PIArena: A Platform for Prompt Injection Evaluation](https://arxiv.org/abs/2604.08499)**
*ArXiv cs.CL*

PIArena is a unified benchmark platform for prompt injection attacks and defenses, addressing the fragmented evaluation landscape that makes it hard to compare mitigations or measure true robustness across diverse attack scenarios.

**[TRUSTDESC: Preventing Tool Poisoning in LLM Applications via Trusted Description Generation](https://arxiv.org/abs/2604.07536)**
*ArXiv cs.CR*

Tool poisoning attacks (TPAs) embed malicious instructions inside tool descriptions fed to LLM agents. TRUSTDESC generates verified, trusted descriptions to sanitize this attack surface before the LLM ever acts on external tool metadata.

**[MCP-DPT: A Defense-Placement Taxonomy and Coverage Analysis for Model Context Protocol Security](https://arxiv.org/abs/2604.07551)**
*ArXiv cs.CR*

The Model Context Protocol (MCP), which lets LLMs dynamically invoke third-party tools, introduces a distinct security landscape spanning pre-execution artifacts, shared context, and multi-turn workflows. This paper proposes a formal defense-placement taxonomy and shows coverage gaps in current mitigations.

**[Your Agent Is Mine: Measuring Malicious Intermediary Attacks on the LLM Supply Chain](https://arxiv.org/abs/2604.08407)**
*ArXiv cs.CR*

LLM agents increasingly route tool-calling requests through third-party API routers that have full plaintext access to every JSON payload, yet no provider enforces cryptographic integrity end-to-end. The paper measures the real attack surface this creates across the LLM supply chain.

**[Securing Retrieval-Augmented Generation: A Taxonomy of Attacks, Defenses, and Future Directions](https://arxiv.org/abs/2604.08304)**
*ArXiv cs.CR*

A comprehensive taxonomy separating RAG-specific security risks from baseline LLM risks, covering knowledge poisoning, retriever manipulation, and extraction attacks along with a structured view of current defenses and open problems.

**[Phantasia: Context-Adaptive Backdoors in Vision Language Models](https://arxiv.org/abs/2604.08395)**
*ArXiv cs.CV*

Phantasia demonstrates a new class of backdoor attacks against vision-language models that adapt to context rather than relying on fixed triggers, making them harder to detect while maintaining high attack success rates in multimodal pipelines.

**[Label Leakage Attacks in Machine Unlearning: A Parameter and Inversion-Based Approach](https://arxiv.org/abs/2604.07386)**
*ArXiv cs.CR*

Machine unlearning methods (designed to honor "right to be forgotten" requests) may inadvertently leak private labels through parameter updates. This paper demonstrates the attack and its implications for privacy-compliant AI systems.

---

## Vulnerabilities & Exploits

**[Hims Breach Exposes the Most Sensitive Kinds of PHI](https://www.darkreading.com/cyberattacks-data-breaches/hims-breach-exposes-sensitive-phi)**
*Dark Reading*

Threat actors breached the telehealth brand Hims, potentially exposing protected health information tied to conditions including obesity, hair loss, and erectile dysfunction. The sensitivity of this PHI class creates elevated risks for extortion and targeted fraud.

**[Nearly 4,000 US Industrial Devices Exposed to Iranian Cyberattacks](https://www.bleepingcomputer.com/news/security/nearly-4-000-us-industrial-devices-exposed-to-iranian-cyberattacks/)**
*BleepingComputer*

Researchers found roughly 4,000 internet-exposed Rockwell Automation programmable logic controllers (PLCs) within the attack surface being targeted by Iranian-linked hackers in campaigns against U.S. critical infrastructure.

**[GlassWorm Campaign Uses Zig Dropper to Infect Multiple Developer IDEs](https://thehackernews.com/2026/04/glassworm-campaign-uses-zig-dropper-to.html)**
*The Hacker News*

The ongoing GlassWorm campaign has evolved a new Zig-based dropper distributed via a malicious Open VSX extension masquerading as the popular WakaTime activity tracker, designed to silently infect all IDEs on a developer's machine.

**[CPUID Hacked to Deliver Malware via CPU-Z, HWMonitor Downloads](https://www.bleepingcomputer.com/news/security/supply-chain-attack-at-cpuid-pushes-malware-with-cpu-z-hwmonitor/)**
*BleepingComputer*

Attackers compromised an API for the CPUID project and swapped official download links for CPU-Z and HWMonitor to serve malicious executables, a supply-chain attack targeting developers and power users who trust the official site.

**[Marimo RCE Flaw CVE-2026-39987 Exploited Within 10 Hours of Disclosure](https://thehackernews.com/2026/04/marimo-rce-flaw-cve-2026-39987.html)**
*The Hacker News*

A pre-authenticated remote code execution vulnerability (CVSS 9.3) in the Marimo open-source Python notebook was exploited in the wild within 10 hours of public disclosure, underscoring how quickly attackers weaponize high-severity CVEs in developer tooling.

**[Microsoft: Canadian Employees Targeted in Payroll Pirate Attacks](https://www.bleepingcomputer.com/news/microsoft/microsoft-canadian-employees-targeted-in-payroll-pirate-attacks/)**
*BleepingComputer*

The financially motivated threat actor Storm-2755 is hijacking employee accounts to redirect salary payments, a credential-based fraud campaign Microsoft is actively tracking across Canadian organizations.

**[Can Anthropic Keep Its Exploit-Writing AI Out of the Wrong Hands?](https://www.darkreading.com/application-security/anthropic-exploit-writing-mythos-ai-safe)**
*Dark Reading*

Anthropic's Mythos Preview model is reportedly capable of finding and exploiting critical zero-days autonomously. The company says it has implemented access controls, but questions remain about whether those guardrails are sufficient given the model's offensive capabilities.

---

## Policy & Compliance

**[FINRA Launches Financial Intelligence Fusion Center to Combat Cybersecurity and Fraud Threats](https://www.darkreading.com/threat-intelligence/finra-launches-financial-intelligence-fusion-center)**
*Dark Reading*

FINRA has stood up a new Financial Intelligence Fusion Center to coordinate threat intelligence sharing and incident response across the brokerage and securities industry, focusing specifically on cybersecurity and fraud.

**[Analysis of One Billion CISA KEV Remediation Records Exposes Limits of Human-Scale Security](https://www.bleepingcomputer.com/news/security/analysis-of-one-billion-cisa-kev-remediation-records-exposes-limits-of-human-scale-security/)**
*BleepingComputer*

A Qualys analysis of over a billion CISA Known Exploited Vulnerability remediation records shows that most critical flaws are being exploited before defenders can patch them, pointing to a structural breaking point in the current patch-management model.
