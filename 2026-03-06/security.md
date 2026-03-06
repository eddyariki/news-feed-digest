# Security Digest — 2026-03-06

AI is reshaping both offense and defense today: researchers are deploying LLMs to find real vulnerabilities in Firefox and Chromium while threat actors are using the same models to orchestrate government intrusions and mass-produce malware. Meanwhile, critical infrastructure faces active exploitation from nation-state actors across the US, South America, and the Middle East.

---

## AI Security Research

**[Anthropic's Claude found 22 vulnerabilities in Firefox over two weeks](https://techcrunch.com/2026/03/06/anthropics-claude-found-22-vulnerabilities-in-firefox-over-two-weeks/)**
*TechCrunch AI*
In a security partnership with Mozilla, Anthropic's Claude identified 22 separate vulnerabilities in Firefox, 14 classified as high-severity. The engagement demonstrates how LLM-powered automated auditing is becoming a practical complement to traditional security review.

**[Codex Security: now in research preview](https://openai.com/index/codex-security-now-in-research-preview)**
*OpenAI Blog*
OpenAI's Codex Security agent analyzes project context to detect, validate, and patch complex vulnerabilities with higher confidence and less noise than static analyzers. Early results include findings in OpenSSH and Chromium.

**[Clinejection — Compromising Cline's Production Releases just by Prompting an Issue Triager](https://simonwillison.net/2026/Mar/6/clinejection/#atom-everything)**
*Simon Willison's Weblog*
Adnan Khan demonstrated a prompt injection attack on Cline's AI-powered GitHub issue triager that propagated into the repository's CI/CD pipeline, enabling a supply-chain compromise via a single maliciously crafted issue title. This is a sharp illustration of the risks of giving LLM agents write access to release infrastructure.

**[Fake Claude Code install guides push infostealers in InstallFix attacks](https://www.bleepingcomputer.com/news/security/fake-claude-code-install-guides-push-infostealers-in-installfix-attacks/)**
*BleepingComputer*
Attackers are using a ClickFix variant called "InstallFix" that lures developers with fake CLI tool installation instructions for tools like Claude Code, tricking them into running infostealer payloads. The campaign specifically targets developers who interact with LLM tooling.

**[Alignment Backfire: Language-Dependent Reversal of Safety Interventions Across 16 Languages in LLM Multi-Agent Systems](https://arxiv.org/abs/2603.04904)**
*ArXiv cs.AI*
Four pre-registered studies across 1,584 multi-agent simulations find that safety alignment in LLMs can reverse in non-English languages — a model may refuse harmful prompts in English while complying in other languages. The results hold across three model families and have direct implications for deploying aligned models in multilingual deployments.

**[Beyond Input Guardrails: Reconstructing Cross-Agent Semantic Flows for Execution-Aware Attack Detection](https://arxiv.org/abs/2603.04469)**
*ArXiv cs.CR*
Researchers propose a framework that reconstructs the semantic flow across agent-to-agent communication to detect indirect prompt injection attacks that bypass input-level guardrails. The method addresses a known blind spot in current multi-agent system defenses.

**[When Denoising Becomes Unsigning: Theoretical and Empirical Analysis of Watermark Fragility Under Diffusion-Based Image Editing](https://arxiv.org/abs/2603.04696)**
*ArXiv cs.CR*
Diffusion-based image editing — now a default transformation for many content pipelines — systematically destroys invisible watermarks that survive JPEG compression and cropping. The paper provides both a theoretical account and empirical results across six watermarking schemes, raising questions about relying on watermarking alone for AI content provenance.

---

## Vulnerabilities & Exploits

**[FBI investigates breach of surveillance and wiretap systems](https://www.bleepingcomputer.com/news/security/fbi-investigates-breach-of-surveillance-and-wiretap-systems/)**
*BleepingComputer*
The FBI confirmed it is investigating a breach affecting systems used to manage surveillance and wiretap warrants. No further details on scope or attribution have been released, but a compromise of warrant management infrastructure represents a significant law enforcement security incident.

**[Cognizant TriZetto breach exposes health data of 3.4 million patients](https://www.bleepingcomputer.com/news/security/cognizant-trizetto-breach-exposes-health-data-of-34-million-patients/)**
*BleepingComputer*
TriZetto Provider Solutions, which provides billing and claims software to health insurers and providers, suffered a breach exposing sensitive personal and health information for over 3.4 million people. The incident adds to a growing list of healthcare IT supply-chain breaches.

**[Hikvision and Rockwell Automation CVSS 9.8 Flaws Added to CISA KEV Catalog](https://thehackernews.com/2026/03/hikvision-and-rockwell-automation-cvss.html)**
*The Hacker News*
CISA added two critical vulnerabilities — CVE-2017-7921 (Hikvision improper authentication, CVSS 9.8) and a Rockwell Automation flaw — to its Known Exploited Vulnerabilities catalog. The Hikvision CVE is nearly a decade old, highlighting continued exploitation of unpatched OT/IoT assets.

**[CISA warns feds to patch iOS flaws exploited in crypto-theft attacks](https://www.bleepingcomputer.com/news/security/cisa-warns-of-apple-flaws-exploited-in-spyware-crypto-theft-attacks/)**
*BleepingComputer*
CISA ordered federal agencies to patch three iOS flaws actively exploited via the Coruna exploit kit in both cyberespionage and cryptocurrency-theft campaigns. Ars Technica reports the exploits form a large, unusually complex iOS exploit assembly with murky attribution.

**[Iran-Linked MuddyWater Hackers Target U.S. Networks With New Dindoor Backdoor](https://thehackernews.com/2026/03/iran-linked-muddywater-hackers-target.html)**
*The Hacker News*
Broadcom's Symantec and Carbon Black teams found Iranian state-sponsored group MuddyWater (Seedworm) embedded in several US organizations including banks, airports, and non-profits, using a new backdoor called Dindoor. The group also compromised the Israeli arm of a software company.

**[Claude Used to Hack Mexican Government](https://www.schneier.com/blog/archives/2026/03/claude-used-to-hack-mexican-government.html)**
*Schneier on Security*
An unknown attacker used Anthropic's Claude to systematically probe Mexican government networks — prompting the model to act as an elite hacker, find vulnerabilities, write exploit scripts, and automate data exfiltration. Anthropic said Claude's safety systems were eventually triggered, but only after the intrusion had already progressed.

**[China-Linked Hackers Use TernDoor, PeerTime, BruteEntry in South American Telecom Attacks](https://thehackernews.com/2026/03/china-linked-hackers-use-terndoor.html)**
*The Hacker News*
Cisco Talos is tracking UAT-9244, a China-linked APT closely associated with FamousSparrow, deploying three distinct implants against South American telecom infrastructure across Windows, Linux, and network edge devices since 2024.

**[Microsoft Reveals ClickFix Campaign Using Windows Terminal to Deploy Lumma Stealer](https://thehackernews.com/2026/03/microsoft-reveals-clickfix-campaign.html)**
*The Hacker News*
A February 2026 ClickFix campaign observed by Microsoft abused Windows Terminal — rather than the more common Run dialog — to deliver the Lumma Stealer malware, adding a new execution vector to a social engineering technique that shows no signs of slowing down.

**[Transparent Tribe Uses AI to Mass-Produce Malware Implants in Campaign Targeting India](https://thehackernews.com/2026/03/transparent-tribe-uses-ai-to-mass.html)**
*The Hacker News*
The Pakistan-aligned APT Transparent Tribe is using AI coding tools to rapidly generate malware implants in lesser-known languages (Nim, Zig, Crystal) distributed over trusted services, prioritizing volume and evasion over sophistication.

---

## Policy & Compliance

**[EU Auto Rules Shift Gears on Cybersecurity Standards](https://www.darkreading.com/cyber-risk/eu-auto-rules-shift-gears-on-cybersecurity-standards)**
*Dark Reading*
The European Union is updating automotive cybersecurity requirements as connected and autonomous vehicles become targets for both climate-related physical damage and cyberattacks. The revised framework signals tighter scrutiny of software-defined vehicles across the EU market.

**[Secure human oversight of AI: Threat modeling in a socio-technical context](https://arxiv.org/abs/2509.12290)**
*ArXiv cs.CR*
This updated paper argues that discussions of human oversight of AI have focused on effectiveness while neglecting the security of the oversight mechanisms themselves. It proposes a socio-technical threat model covering how oversight systems could be compromised, manipulated, or circumvented — directly relevant to EU AI Act compliance design.
