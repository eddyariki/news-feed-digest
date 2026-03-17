# Security Digest — 2026-03-18

Today's threat landscape is defined by active AI-targeted attack research and simultaneous nation-state espionage campaigns, with new jailbreak and memory-hijack techniques for LLM agents leading the research front while ransomware groups refine stealthy initial-access tactics in the wild.

---

## AI Security Research

**[Activation Surgery: Jailbreaking White-box LLMs without Touching the Prompt](https://arxiv.org/abs/2603.14278)**
*ArXiv cs.CR — Jenny et al.*
A new jailbreak method bypasses LLM safety by surgically modifying internal activations at runtime rather than crafting adversarial prompts, sidestepping prompt-based defenses entirely. The technique exposes a blind spot in safety evaluations that focus only on input-layer controls.

**[From Storage to Steering: Memory Control Flow Attacks on LLM Agents](https://arxiv.org/abs/2603.15125)**
*ArXiv cs.CR — Xu et al.*
Researchers show that attackers can hijack an LLM agent's decision-making by poisoning its persistent memory store, redirecting which tools get called and in what order without modifying the model or its prompt. The attack affects any agentic system that uses external memory to build task control flows.

**[When Scanners Lie: Evaluator Instability in LLM Red-Teaming](https://arxiv.org/abs/2603.14633)**
*ArXiv cs.CR — Erez et al.*
Automated red-teaming scanners that measure attack success rates (ASR) produce inconsistent results because their embedded evaluators are themselves unreliable, potentially giving false confidence in LLM safety posture. The study calls for standardized, stable evaluation protocols before ASR becomes a compliance metric.

**[AI Flaws in Amazon Bedrock, LangSmith, and SGLang Enable Data Exfiltration and RCE](https://thehackernews.com)**
*The Hacker News*
Researchers disclosed a method for exfiltrating sensitive data from AI code-execution sandboxes by encoding stolen information in DNS queries — a channel typically left unmonitored in AI infrastructure. Affected platforms include Amazon Bedrock, LangSmith, and SGLang.

**[New font-rendering trick hides malicious commands from AI tools](https://www.bleepingcomputer.com)**
*BleepingComputer*
A novel attack embeds malicious instructions inside HTML using non-rendering Unicode characters, causing AI assistants parsing web content to silently execute attacker commands they visually cannot "see." The technique bypasses content-inspection defenses that rely on rendered text.

**[Governing Dynamic Capabilities: Cryptographic Binding and Reproducibility Verification for AI Agent Tool Use](https://arxiv.org/abs/2603.14332)**
*ArXiv cs.CR — Zhou*
This paper introduces a framework to close the "capability-identity gap," where AI agents silently acquire new tools at runtime via MCP/A2A protocols without re-authorization — a behavior that violates EU AI Act traceability requirements. The proposed solution uses cryptographic binding to lock capabilities to their authorized state.

**[CTI-REALM: Benchmark to Evaluate Agent Performance on Security Detection Rule Generation](https://arxiv.org/abs/2603.13517)**
*ArXiv cs.CR — Chakraborty et al.*
CTI-REALM provides a realistic benchmark for measuring how well AI agents translate cyber threat intelligence (CTI) into actionable detection rules, exposing significant gaps between current LLM capabilities and production SOC requirements.

**[Ransomware and Artificial Intelligence: A Comprehensive Systematic Review of Reviews](https://arxiv.org/abs/2603.13734)**
*ArXiv cs.CR — Daengsi et al.*
A PRISMA-based meta-analysis synthesizes findings across dozens of prior reviews on ML/DL-based ransomware defense, identifying recurring blind spots and highlighting where AI detection techniques consistently fail against novel variants.

---

## Vulnerabilities & Exploits

**[China-Nexus Hackers Skulk in Southeast Asian Military Orgs for Years](https://www.darkreading.com/threat-intelligence/china-nexus-hackers-southeast-asian-military-orgs)**
*Dark Reading — Rob Wright*
Researchers uncovered a sustained espionage campaign using novel backdoors and evasion techniques to maintain multi-year persistence inside Southeast Asian military networks. The operation's longevity points to sophisticated operational security and high-value target prioritization.

**[LeakNet Ransomware Uses ClickFix via Hacked Sites, Deploys Deno In-Memory Loader](https://thehackernews.com)**
*The Hacker News*
The LeakNet ransomware group is now using ClickFix social engineering — delivered through compromised websites — to lure victims into executing payloads, then staging a Deno-based in-memory loader that leaves minimal forensic artifacts. The combination of living-off-the-land runtime and social engineering represents a significant detection evasion upgrade.

**[Researchers disclose vulnerabilities in IP KVMs from four manufacturers](https://arstechnica.com)**
*Ars Technica*
Multiple critical vulnerabilities were found in Internet-exposed IP KVM devices from four vendors, allowing unauthenticated attackers to gain BIOS-level access to servers. The flaws highlight risks in out-of-band management interfaces that are frequently overlooked in enterprise patch cycles.

**[Warlock Ransomware Group Augments Post-Exploitation Activities](https://www.darkreading.com)**
*Dark Reading*
Warlock has added a BYOVD (Bring Your Own Vulnerable Driver) technique to its arsenal, enabling stealthier lateral movement across networks after initial compromise. The group's expanding toolkit suggests active development investment to outpace endpoint detection.

**[Konni Deploys EndRAT Through Phishing, Uses KakaoTalk to Propagate Malware](https://thehackernews.com)**
*The Hacker News*
North Korean threat actors affiliated with Konni are using phishing to gain initial access, then pivoting to the victim's KakaoTalk desktop client to distribute EndRAT to additional contacts — effectively weaponizing trusted messaging apps as a lateral spread vector.

**[CISA Flags Actively Exploited Wing FTP Vulnerability Leaking Server Paths](https://thehackernews.com)**
*The Hacker News*
CISA added a medium-severity Wing FTP Server flaw (CVE-2025-47813) to its Known Exploited Vulnerabilities catalog after evidence of active exploitation emerged, with the bug exposing server file paths that can aid further intrusion.

**[WAFFLED: Exploiting Parsing Discrepancies to Bypass Web Application Firewalls](https://arxiv.org/abs/2503.10846)**
*ArXiv cs.CR — Akhavani et al.*
The paper demonstrates how subtle HTTP parsing differences between WAFs and backend servers can be exploited to smuggle malicious payloads past firewall inspection undetected. Researchers tested the technique against multiple commercial WAFs with high bypass success rates.

---

## Policy & Compliance

**[Europe sanctions Chinese and Iranian firms for cyberattacks](https://www.bleepingcomputer.com)**
*BleepingComputer*
The EU Council announced sanctions against three entities and two individuals from China and Iran for cyberattacks targeting European critical infrastructure, marking an escalation in Europe's willingness to name and formally punish state-linked cyber actors.

**[South Korean Police Accidentally Post Cryptocurrency Wallet Password](https://www.schneier.com)**
*Schneier on Security*
South Korea's National Tax Service publicly exposed the mnemonic recovery phrase for a seized cryptocurrency wallet, allowing an opportunistic actor to drain $4.4 million in assets before authorities could respond. The incident underscores operational security failures in government handling of digital asset evidence.

**[AI is Everywhere, But CISOs are Still Securing It with Yesterday's Skills and Tools](https://thehackernews.com)**
*The Hacker News*
The AI and Adversarial Testing Benchmark Report 2026 finds that a majority of security leaders lack the tools and expertise needed to defend AI systems, with most organizations still applying traditional security frameworks to fundamentally different attack surfaces.
