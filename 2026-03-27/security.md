# Security Digest — 2026-03-27

Today's threat landscape is dominated by active exploitation of AI infrastructure — from a critical Langflow RCE being weaponized within hours of disclosure to novel prompt-injection research targeting MCP and browser-based AI agents — alongside a widening governance gap as the US steps back and the EU takes the lead on global cybersecurity coordination.

---

## AI Security Research

**[Claude Extension Flaw Enabled Zero-Click XSS Prompt Injection via Any Website](https://thehackernews.com/2026/03/claude-extension-flaw-enabled-zero.html)**
*The Hacker News*
A now-patched vulnerability in Anthropic's Claude Chrome Extension allowed any website to silently inject prompts into the assistant as if typed by the user — no clicks required, no user interaction needed. The flaw exposed the growing attack surface of AI browser extensions that operate with broad page access.

**[Claudini: Autoresearch Discovers State-of-the-Art Adversarial Attack Algorithms for LLMs](https://arxiv.org/abs/2603.24511)**
*ArXiv cs.LG*
Researchers used a Claude Code-powered autoresearch pipeline to autonomously discover white-box adversarial attack algorithms that significantly outperform all 30+ existing methods for jailbreaking and prompt injection. The result underscores that AI agents themselves can accelerate the development of AI attacks.

**[Invisible Threats from Model Context Protocol: Generating Stealthy Injection Payload via Tree-based Adaptive Search](https://arxiv.org/abs/2603.24203)**
*ArXiv cs.CR*
A new attack framework demonstrates how MCP tool responses can be stealthily manipulated to inject payloads into LLM agents, exploiting the under-examined gap between tool invocation and output validation. The authors show that existing indirect prompt injection defenses fail to account for this MCP-specific attack surface.

**[The Cognitive Firewall: Securing Browser-Based AI Agents Against Indirect Prompt Injection via Hybrid Edge-Cloud Defense](https://arxiv.org/abs/2603.23791)**
*ArXiv cs.CR*
A proposed three-stage split-compute architecture distributes security checks between client and cloud to defend browser-deployed LLM agents against indirect prompt injection, balancing latency, privacy, and semantic analysis depth. The system addresses the significant attack surface created when LLMs act as autonomous browser agents.

**[Enhancing Jailbreak Attacks on LLMs via Persona Prompts](https://arxiv.org/abs/2507.22171)**
*ArXiv cs.CR*
This updated study systematically explores how persona-based prompt framing amplifies jailbreak success rates against aligned LLMs, a vector that previous work largely overlooked in favor of direct harmful-intent manipulations. The findings have direct implications for safety evaluations and red-teaming frameworks.

**[AI-Powered Dependency Decisions Introduce, Ignore Security Bugs](https://www.darkreading.com/application-security/ai-powered-dependency-decisions-security-bugs)**
*Dark Reading*
AI models tasked with recommending software versions, upgrade paths, and security fixes frequently hallucinate or make costly errors, accumulating technical debt and leaving known vulnerabilities in place. The analysis highlights systemic risks in organizations that delegate dependency management decisions to AI assistants.

**[GitHub Adds AI-Powered Bug Detection to Expand Security Coverage](https://www.bleepingcomputer.com/news/security/github-adds-ai-powered-bug-detection-to-expand-security-coverage/)**
*BleepingComputer*
GitHub is extending its Code Security tool with AI-based scanning to detect vulnerabilities beyond what CodeQL's static analysis can catch, covering more languages and frameworks. The move reflects the industry's shift toward AI-augmented SAST to address coverage gaps in traditional rule-based tooling.

---

## Vulnerabilities & Exploits

**[CISA: New Langflow Flaw Actively Exploited to Hijack AI Workflows](https://www.bleepingcomputer.com/news/security/cisa-new-langflow-flaw-actively-exploited-to-hijack-ai-workflows/)**
*BleepingComputer*
CISA has added CVE-2026-33017, a critical code injection vulnerability in the Langflow AI agent framework, to its Known Exploited Vulnerabilities catalog after confirming active exploitation in the wild. Threat actors are using it to take over AI workflows, with attacks beginning within hours of public disclosure.

**[China-Linked Red Menshen Uses Stealthy BPFDoor Implants to Spy via Telecom Networks](https://thehackernews.com/2026/03/china-linked-red-menshen-uses-stealthy.html)**
*The Hacker News*
The China-nexus threat actor Red Menshen (also tracked as Earth Bluecrow) has embedded BPFDoor implants within telecom networks to conduct long-running espionage against government targets. The campaign exploits the deeply stealthy nature of BPF-based backdoors, which are notoriously difficult to detect with standard endpoint tooling.

**[Coruna iOS Exploit Framework Linked to Triangulation Attacks](https://www.bleepingcomputer.com/news/security/coruna-ios-exploit-framework-linked-to-triangulation-attacks/)**
*BleepingComputer*
The Coruna exploit kit — used in recent mass iOS attacks — has been confirmed as an evolution of the framework behind Operation Triangulation, which targeted iPhones via zero-click iMessage exploits in 2023. Its reuse of updated kernel exploit code suggests a well-resourced actor continuing to invest in the iOS attack chain.

**[WebRTC Skimmer Bypasses CSP to Steal Payment Data from E-Commerce Sites](https://thehackernews.com/2026/03/webrtc-skimmer-bypasses-csp-to-steal.html)**
*The Hacker News*
A newly discovered payment skimmer uses WebRTC data channels — rather than conventional HTTP or image beacon requests — to both load its payload and exfiltrate stolen card data, effectively circumventing Content Security Policy controls. The technique represents a novel covert channel that most CSP configurations do not account for.

**[PolyShell Attacks Target 56% of All Vulnerable Magento Stores](https://www.bleepingcomputer.com/news/security/polyshell-attacks-target-56-percent-of-all-vulnerable-magento-stores/)**
*BleepingComputer*
Attackers exploiting the PolyShell vulnerability in Magento Open Source v2 and Adobe Commerce have already hit more than half of all unpatched installations, making this one of the fastest-spreading e-commerce skimming campaigns on record. Site owners should treat patching as urgent given the scale and speed of exploitation.

---

## Policy & Compliance

**[As the US Midterms Approach, AI Is Going to Emerge as a Key Issue Concerning Voters](https://www.schneier.com/blog/archives/2026/03/as-the-us-midterms-approach-ai-is-going-to-emerge-as-a-key-issue-concerning-voters.html)**
*Schneier on Security*
Bruce Schneier argues that the Trump administration's executive order neutering state-level AI regulation — by threatening to sue and withhold funds from states that attempt oversight — will turn AI governance into a defining midterm issue. With industry lobbyists blocking federal rules and states blocked from acting, the resulting regulatory vacuum is increasingly visible to ordinary voters.

**[At RSAC, the EU Leads While US Officials Are Sidelined](https://www.darkreading.com/cyber-risk/rsac-eu-leads-us-officials-sidelined)**
*Dark Reading*
European officials are actively leading conversations on cybersecurity strategy at RSAC this year while the US government is conspicuously absent, a reversal that reflects the current administration's reduced engagement with international security coordination. The shift is drawing attention to the EU's expanding role as the de facto standard-setter in global cyber policy.

**[UK Sanctions Xinbi Marketplace Linked to Asian Scam Centers](https://www.bleepingcomputer.com/news/security/uk-sanctions-xinbi-marketplace-linked-to-asian-scam-centers/)**
*BleepingComputer*
The UK's FCDO has sanctioned Xinbi, a Chinese-language cryptocurrency marketplace that supplies stolen data and satellite internet equipment to Southeast Asian scam compounds. The action is part of a broader Western effort to dismantle the financial and technical infrastructure enabling large-scale fraud operations in the region.

**[Intermediaries Driving Global Spyware Market Expansion](https://www.darkreading.com/cyber-risk/intermediaries-driving-global-spyware-market-expansion)**
*Dark Reading*
A new study finds that third-party brokers and resellers are the primary mechanism by which commercial spyware evades government export restrictions and proliferates globally, undermining transparency efforts by obscuring the chain between developers and end-users. The findings suggest that sanctions on spyware vendors alone are insufficient without targeting the intermediary layer.
