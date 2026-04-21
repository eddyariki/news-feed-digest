# Security Digest — 2026-04-22

Active ransomware operations, unpatched Windows Defender exploits, and a wave of supply chain and infrastructure attacks dominate today's threat landscape, while AI security research focuses heavily on jailbreak evolution and prompt injection defenses for MCP-based agentic systems.

---

## AI Security Research

**[CASCADE: A Cascaded Hybrid Defense Architecture for Prompt Injection Detection in MCP-Based Systems](https://arxiv.org/abs/2604.17125)**
*ArXiv cs.CR*
The Model Context Protocol's multi-layer architecture introduces new attack surfaces including tool poisoning alongside traditional prompt injection; CASCADE proposes a cascaded hybrid detection architecture to address these threats. Timely as MCP adoption accelerates across LLM tooling ecosystems.

**[ASTRA: An Automated Framework for Strategy Discovery, Retrieval, and Evolution for Jailbreaking LLMs](https://arxiv.org/abs/2511.02356)**
*ArXiv cs.LG*
ASTRA demonstrates that LLMs remain vulnerable to jailbreaks even with extensive safety alignment, presenting an automated framework that continuously learns and evolves attack strategies from prior interactions. The self-improving nature of the approach highlights a key gap in static alignment defenses.

**[Jailbreaking Large Language Models with Morality Attacks](https://arxiv.org/abs/2604.17053)**
*ArXiv cs.CL*
This paper exploits AI pluralism alignment — the goal of serving morally diverse users — as an attack vector, using moral framing to bypass safety refusals. It surfaces a tension between building culturally inclusive AI and maintaining robust safety boundaries.

**[SafeDream: Safety World Model for Proactive Early Jailbreak Detection](https://arxiv.org/abs/2604.16824)**
*ArXiv cs.CR*
Multi-turn jailbreak attacks achieve success rates exceeding 90% against state-of-the-art models by progressively eroding alignment across innocuous conversation turns; SafeDream proposes a proactive world-model approach to detect malicious intent before it fully materializes. Existing guardrail and alignment methods are shown to fall short against this escalation pattern.

**[Adversarial Humanities Benchmark: Results on Stylistic Robustness in Frontier Model Safety](https://arxiv.org/abs/2604.18487)**
*ArXiv cs.CL*
The AHB evaluates whether frontier model safety refusals survive when harmful prompts are rewritten using literary, philosophical, or rhetorical styles drawn from the humanities. Results reveal that stylistic reformulation is a reliable evasion vector, suggesting safety training overfits to surface-level harmful prompt forms.

---

## Vulnerabilities & Exploits

**[Exploits Turn Windows Defender into Attacker Tool](https://www.darkreading.com/cyberattacks-data-breaches/exploits-turn-windows-defender-attacker-tool)**
*Dark Reading*
Three proof-of-concept exploits are actively weaponizing Microsoft's built-in security platform against users, with two of the three remaining unpatched. The attacks invert Defender's trusted OS position to facilitate lateral movement and payload delivery.

**[Surge in Bomgar RMM Exploitation Demonstrates Supply Chain Risk](https://www.darkreading.com/cyberattacks-data-breaches/surge-bomgar-rmm-exploitation-demonstrates-supply-chain-risk)**
*Dark Reading*
CVE-2026-1731, a critical RCE flaw in the BeyondTrust Bomgar remote monitoring and management tool, is being actively exploited to spread ransomware and compromise supply chains. The surge underscores how widely deployed RMM tools serve as high-value pivot points for attackers.

**[Google Patches Antigravity IDE Flaw Enabling Prompt Injection Code Execution](https://thehackernews.com/2026/04/google-patches-antigravity-ide-flaw.html)**
*The Hacker News*
A now-patched vulnerability in Google's agentic IDE Antigravity combined insufficient input sanitization with the tool's file-creation permissions to enable prompt injection–triggered sandbox escape and arbitrary code execution. The flaw is a concrete example of the security challenges unique to agentic AI tooling.

**[SystemBC C2 Server Reveals 1,570+ Victims in The Gentlemen Ransomware Operation](https://thehackernews.com/2026/04/systembc-c2-server-reveals-1570-victims.html)**
*The Hacker News*
Check Point researchers gained visibility into a SystemBC C2 server linked to The Gentlemen ransomware-as-a-service operation, exposing over 1,570 victim organizations. The findings illustrate both the scale of modern RaaS infrastructure and the intelligence value of C2 server access.

**[New Lotus Data Wiper Used Against Venezuelan Energy, Utility Firms](https://www.bleepingcomputer.com/news/security/new-lotus-data-wiper-used-against-venezuelan-energy-utility-firms/)**
*BleepingComputer*
A previously undocumented destructive malware called Lotus was deployed against energy and utility organizations in Venezuela, adding to a growing list of wiper attacks targeting critical infrastructure. The threat actor and attribution remain under investigation.

**[22 BRIDGE:BREAK Flaws Expose Thousands of Lantronix and Silex Serial-to-IP Converters](https://thehackernews.com/2026/04/22-bridgebreak-flaws-expose-20000.html)**
*The Hacker News*
Researchers at Forescout identified 22 vulnerabilities across popular serial-to-IP converter models, collectively dubbed BRIDGE:BREAK, that could allow attackers to hijack devices and tamper with industrial data streams. Thousands of internet-exposed converters remain at risk.

**[NGate Campaign Targets Brazil, Trojanizes HandyPay to Steal NFC Data and PINs](https://thehackernews.com/2026/04/ngate-campaign-targets-brazil.html)**
*The Hacker News*
A new NGate malware variant trojanizes the legitimate HandyPay NFC relay application to intercept contactless payment data and PINs from Brazilian Android users. The approach of repackaging trusted fintech apps marks an evolution from earlier NGate campaigns.

**[Actively Exploited Apache ActiveMQ Flaw Impacts 6,400 Servers](https://www.bleepingcomputer.com/news/security/actively-exploited-apache-activemq-flaw-impacts-6-400-servers/)**
*BleepingComputer*
Shadowserver identified over 6,400 internet-exposed Apache ActiveMQ servers vulnerable to active exploitation of a high-severity code injection flaw. Unpatched deployments remain a critical remediation priority.

**['Scattered Spider' Member 'Tylerb' Pleads Guilty](https://krebsonsecurity.com/2026/04/scattered-spider-member-tylerb-pleads-guilty/)**
*Krebs on Security*
Tyler Robert Buchanan, a 24-year-old British national and senior Scattered Spider member, pleaded guilty to wire fraud conspiracy and aggravated identity theft stemming from SMS phishing campaigns in summer 2022. His prosecution continues the slow but steady legal dismantling of one of the most disruptive English-language cybercrime groups.

**[Mexican Surveillance Company](https://www.schneier.com/blog/archives/2026/04/mexican-surveillance-company.html)**
*Schneier on Security*
Grupo Seguritech, a Mexican commercial surveillance vendor, is expanding its operations into the United States. The note flags the continued proliferation of surveillance-as-a-service vendors beyond traditional nation-state actors.

---

## Policy & Compliance

**[CISA Adds 8 Exploited Flaws to KEV, Sets April–May 2026 Federal Deadlines](https://thehackernews.com/2026/04/cisa-adds-8-exploited-flaws-to-kev-sets.html)**
*The Hacker News*
CISA added eight new entries to its Known Exploited Vulnerabilities catalog, including three Cisco Catalyst SD-WAN Manager flaws confirmed as actively exploited, with mandatory federal remediation deadlines in April and May 2026. The additions reinforce urgency for both government and private-sector operators running SD-WAN infrastructure.

**[CISA Flags New SD-WAN Flaw as Actively Exploited in Attacks](https://www.bleepingcomputer.com/news/security/cisa-flags-new-sd-wan-flaw-as-actively-exploited-in-attacks/)**
*BleepingComputer*
CISA issued a four-day remediation deadline to U.S. federal agencies for a newly flagged Cisco Catalyst SD-WAN Manager vulnerability under active exploitation. The compressed timeline reflects CISA's escalating posture on confirmed in-the-wild exploitation.

**[UK Probes Telegram, Teen Chat Sites Over CSAM Sharing Concerns](https://www.bleepingcomputer.com/news/security/uk-probes-telegram-teen-chat-sites-over-csam-sharing-concerns/)**
*BleepingComputer*
Ofcom has opened a formal investigation into Telegram and several teen-focused chat platforms over evidence they are being used to distribute child sexual abuse material. The probe invokes the UK's Online Safety Act and could result in significant enforcement action against platforms with end-to-end encryption.

**[Chinese APT Targets Indian Banks, Korean Policy Circles](https://www.darkreading.com/cyberattacks-data-breaches/chinese-apt-indian-banks-korean-policy)**
*Dark Reading*
A Chinese APT has been observed conducting espionage against India's financial sector and South Korean policy institutions, using notably stale TTPs that suggest either operational laziness or confidence in target defenses being equally outdated. The campaign highlights persistent geopolitical cyber targeting even without sophisticated tooling.
