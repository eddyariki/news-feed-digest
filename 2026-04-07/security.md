# Security Digest — 2026-04-07

A heavy week dominated by Fortinet zero-days under active exploitation, multiple supply chain attacks against npm and GitHub, and growing evidence that AI is being weaponized to scale both credential harvesting and social engineering. On the research side, new work exposes persistent memory-poisoning vectors in LLM-based agents and probes the limits of RLHF safety alignment.

---

## AI Security Research

**[Understanding the Effects of Safety Unalignment on Large Language Models](https://arxiv.org/abs/2604.02574)**
*ArXiv cs.AI*
New analysis of jailbreak-tuning and weight orthogonalization shows that safety guardrails in frontier LLMs can be largely disabled, leaving models compliant with requests they would normally refuse. The paper characterizes what is actually "unlearned" and what persists after these attacks.

**[Poison Once, Exploit Forever: Environment-Injected Memory Poisoning Attacks on Web Agents](https://arxiv.org/abs/2604.02623)**
*ArXiv cs.AI*
Demonstrates a realistic threat model where attackers contaminate LLM-agent memory through normal environmental interactions rather than direct storage access, creating a persistent attack surface that carries across sessions and websites. The attack bypasses assumptions in prior memory-security research.

**[AgenticRed: Evolving Agentic Systems for Red-Teaming](https://arxiv.org/abs/2604.03201)**
*ArXiv cs.AI*
Proposes an agentic red-teaming framework that evolves attack strategies autonomously, offering a structured methodology for stress-testing LLM-based systems at scale.

**[AI Offensive Cyber Capabilities Are Doubling Every Six Months, Safety Researcher Says](https://the-decoder.com/ai-offensive-cyber-capabilities-are-doubling-every-six-months-safety-researcher-says/)**
*The Decoder*
A safety researcher reports that AI-assisted offensive cyber capabilities are on a rapid doubling curve, raising alarms about the shrinking window between vulnerability discovery and automated exploitation.

**[OWASP GenAI Security Project Gets Update, New Tools Matrix](https://www.darkreading.com/application-security/owasp-genai-security-project-update-matrix)**
*Dark Reading*
OWASP has published an updated framework recognizing 21 generative AI risks and recommends separate but linked defensive approaches for GenAI systems versus agentic AI systems.

**[How LiteLLM Turned Developer Machines Into Credential Vaults for Attackers](https://thehackernews.com/2026/04/how-litellm-turned-developer-machines.html)**
*The Hacker News*
The March 2026 TeamPCP supply chain attack on LiteLLM targeted developer workstations as a rich credential store — API keys, cached tokens, and AI service credentials — highlighting dev machines as a high-value attack surface in the AI toolchain.

---

## Vulnerabilities & Exploits

**[Fortinet Issues Emergency Patch for FortiClient Zero-Day](https://www.darkreading.com/vulnerabilities-threats/fortinet-emergency-patch-forticlient-zero-day)**
*Dark Reading*
CVE-2026-35616, an authentication bypass in FortiClient EMS, is the latest in a string of Fortinet vulnerabilities actively exploited in the wild; CISA ordered federal agencies to patch by Friday.

**[Disgruntled Researcher Leaks "BlueHammer" Windows Zero-Day Exploit](https://www.bleepingcomputer.com/news/security/disgruntled-researcher-leaks-bluehammer-windows-zero-day-exploit/)**
*BleepingComputer*
An unpatched Windows privilege-escalation flaw reported privately to Microsoft has had its exploit code publicly released by a frustrated researcher, granting attackers a path to SYSTEM-level access before a patch exists.

**[AI-Assisted Supply Chain Attack Targets GitHub](https://www.darkreading.com/application-security/ai-assisted-supply-chain-attack-targets-github)**
*Dark Reading*
The PRT-scan campaign is the second recent attack where a threat actor used AI to automate targeting of a widespread GitHub misconfiguration, signaling industrialized supply chain reconnaissance.

**[Axios Attack Shows Social Engineering Is Industrialized](https://www.darkreading.com/threat-intelligence/axios-attack-complex-social-engineering-industrialized)**
*Dark Reading*
The compromise of the widely-used Axios npm package illustrates how sophisticated social engineering targeting open-source maintainers is now being scaled with automation, threatening downstream consumers at package-manager scale.

**[36 Malicious npm Packages Exploited Redis, PostgreSQL to Deploy Persistent Implants](https://thehackernews.com/2026/04/36-malicious-npm-packages-exploited.html)**
*The Hacker News*
Thirty-six malicious packages in the npm registry abused Redis and PostgreSQL connections as covert channels to establish persistence on developer machines, expanding the blast radius of the ongoing npm supply chain crisis.

**[DPRK-Linked Hackers Use GitHub as C2 in Multi-Stage Attacks Targeting South Korea](https://thehackernews.com/2026/04/dprk-linked-hackers-use-github-as-c2-in.html)**
*The Hacker News*
North Korea-linked actors are abusing GitHub repositories as command-and-control infrastructure in campaigns against South Korean organizations, with obfuscated LNK files as the initial vector and decoy PDFs to avoid suspicion.

**[$285 Million Drift Hack Traced to Six-Month DPRK Social Engineering Operation](https://thehackernews.com/2026/04/285-million-drift-hack-traced-to-six.html)**
*The Hacker News*
The Drift Protocol theft — initially reported as $280M — is now attributed to a prolonged DPRK-linked operation that spent six months building a legitimate operational presence inside the Drift ecosystem before executing the heist.

**[Qilin and Warlock Ransomware Use Vulnerable Drivers to Disable 300+ EDR Tools](https://thehackernews.com/2026/04/qilin-and-warlock-ransomware-use.html)**
*The Hacker News*
Both ransomware groups are deploying BYOVD (bring your own vulnerable driver) techniques to silently kill security tools on compromised hosts, with Qilin using a malicious `msimg32.dll` sideload as the entry point.

**[New GPUBreach Attack Enables System Takeover via GPU Rowhammer](https://www.bleepingcomputer.com/news/security/new-gpubreach-attack-enables-system-takeover-via-gpu-rowhammer/)**
*BleepingComputer*
GPUBreach induces Rowhammer bit-flips in GDDR6 GPU memory to escalate privileges and achieve full system compromise, extending hardware-level memory attacks beyond DRAM to the GPU for the first time.

---

## Policy & Compliance

**[New Mexico's Meta Ruling and Encryption](https://www.schneier.com/blog/archives/2026/04/new-mexicos-meta-ruling-and-encryption.html)**
*Schneier on Security*
Bruce Schneier highlights that the New Mexico court's "design choices create liability" framework — which cited Meta's 2023 addition of end-to-end encryption to Messenger as evidence of negligence — sets a troubling precedent that could pressure companies to weaken encryption.

**[Google Wants to Transition to Post-Quantum Cryptography by 2029](https://www.schneier.com/blog/archives/2026/04/google-wants-to-transition-to-post-quantum-cryptography-by-2029.html)**
*Schneier on Security*
Google has committed to completing a full post-quantum cryptography migration by 2029; Schneier endorses the move as sound crypto-agility practice regardless of whether a cryptographically relevant quantum computer arrives by then.

**[CISA Orders Feds to Patch Exploited Fortinet EMS Flaw by Friday](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-fortinet-flaw-exploited-in-attacks-by-friday/)**
*BleepingComputer*
CISA issued a binding operational directive requiring federal agencies to remediate the actively exploited FortiClient EMS vulnerability on an emergency timeline, underscoring the severity of the Fortinet exploitation wave.
