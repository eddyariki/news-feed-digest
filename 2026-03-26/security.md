# Security Digest — 2026-03-26

AI is now front and center in both offense and defense: SANS Institute named AI-powered techniques all five of its top attack vectors for the first time, while a wave of new research addresses agent memory poisoning, LLM red-teaming, and adaptive jailbreaks. On the exploit front, large-scale Microsoft 365 phishing and critical router vulnerabilities dominated the patch cycle.

---

## AI Security Research

**[T-MAP: Red-Teaming LLM Agents with Trajectory-aware Evolutionary Search](https://arxiv.org/abs/2603.22341)**
*ArXiv cs.CR / cs.AI*
Researchers introduce T-MAP, a trajectory-aware evolutionary method that red-teams LLM agents operating over multi-step tool calls—especially those using the Model Context Protocol (MCP)—exposing agent-specific vulnerabilities invisible to standard single-turn evaluations.

**[Mind Your HEARTBEAT! Claw Background Execution Enables Silent Memory Pollution](https://arxiv.org/abs/2603.23064)**
*ArXiv cs.CR / cs.AI*
A newly identified architectural flaw in "Claw" personal AI agents lets untrusted content encountered during heartbeat-driven background execution silently corrupt persistent agent memory and alter user-facing behavior without any visible indicator.

**[Robust Safety Monitoring of Language Models via Activation Watermarking](https://arxiv.org/abs/2603.23171)**
*ArXiv cs.CR / cs.AI*
This paper proposes embedding cryptographic watermarks into LLM activation spaces so that safety monitors can detect adaptive adversaries who craft inputs to simultaneously evade detection while eliciting unsafe outputs such as malware or weapons instructions.

**[SANS: Top 5 Most Dangerous New Attack Techniques to Watch](https://www.darkreading.com/threat-intelligence/sans-most-dangerous-attack-techniques)**
*Dark Reading*
For the first time in its history, all five of SANS Institute's top dangerous new attack techniques share a common theme—AI—reflecting how adversaries are operationalizing LLMs for reconnaissance, exploit generation, and social engineering at machine speed.

**[The Kill Chain Is Obsolete When Your AI Agent Is the Threat](https://thehackernews.com/2026/03/the-kill-chain-is-obsolete-when-your-ai.html)**
*The Hacker News*
Drawing on Anthropic's September 2025 disclosure of a state-sponsored AI coding agent that handled 80–90% of a cyber espionage campaign autonomously, the analysis argues that traditional kill-chain frameworks break down against AI agents capable of independent reconnaissance, exploit writing, and lateral movement.

---

## Vulnerabilities & Exploits

**[Device Code Phishing Hits 340+ Microsoft 365 Orgs Across Five Countries via OAuth Abuse](https://thehackernews.com/2026/03/device-code-phishing-hits-340-microsoft.html)**
*The Hacker News*
An active campaign first spotted in February 2026 is targeting Microsoft 365 accounts across the U.S., Canada, Australia, New Zealand, and Germany by abusing the OAuth device authorization flow; the attack volume has been accelerating sharply since detection.

**[Citrix Urges Admins to Patch NetScaler Flaws as Soon as Possible](https://www.bleepingcomputer.com/news/security/citrix-urges-admins-to-patch-netscaler-flaws-as-soon-as-possible/)**
*BleepingComputer*
Citrix has patched two NetScaler ADC and Gateway vulnerabilities, one of which closely resembles CitrixBleed and CitrixBleed2—flaws previously exploited as zero-days—and is urging immediate patching given the known exploitation patterns for similar issues.

**[TP-Link Warns Users to Patch Critical Router Auth Bypass Flaw](https://www.bleepingcomputer.com/news/security/tp-link-warns-users-to-patch-critical-router-auth-bypass-flaw/)**
*BleepingComputer*
A critical flaw in TP-Link's Archer NX router series allows unauthenticated attackers to bypass authentication and upload arbitrary firmware, enabling full device takeover.

**[GlassWorm Malware Uses Solana Dead Drops to Deliver RAT and Steal Browser, Crypto Data](https://thehackernews.com/2026/03/glassworm-malware-uses-solana-dead.html)**
*The Hacker News*
An evolved GlassWorm campaign delivers a multi-stage framework that installs a RAT and deploys a Chrome extension masquerading as offline Google Docs—logging keystrokes, stealing cookies and session tokens, and exfiltrating crypto wallet data.

**[Bubble AI App Builder Abused to Steal Microsoft Account Credentials](https://www.bleepingcomputer.com/news/security/bubble-ai-app-builder-abused-to-steal-microsoft-account-credentials/)**
*BleepingComputer*
Threat actors are generating and hosting phishing pages on the no-code Bubble platform to steal Microsoft credentials, leveraging the legitimate domain to evade standard phishing detection.

**[Manager of Botnet Used in Ransomware Attacks Gets 2 Years in Prison](https://www.bleepingcomputer.com/news/security/russian-man-sentenced-for-operating-botnet-used-in-ransomware-attacks/)**
*BleepingComputer*
A Russian national was sentenced to two years in prison for managing a phishing botnet used to launch BitPaymer ransomware attacks against 72 U.S. companies, one of the few successful prosecutions of ransomware infrastructure operators.

---

## Policy & Compliance

**[FCC Bans New Foreign-Made Routers Over Supply Chain and Cyber Risk Concerns](https://thehackernews.com/2026/03/fcc-bans-new-foreign-made-routers-over.html)**
*The Hacker News*
FCC Chairman Brendan Carr announced a ban on importing new consumer routers manufactured by foreign entities, citing "unacceptable" national security and cyber risks to U.S. communications infrastructure.

**[Sen. Wyden Warns of Another Section 702 Abuse](https://www.schneier.com/blog/archives/2026/03/sen-wyden-warns-of-another-section-702-abuse.html)**
*Schneier on Security*
In a Senate floor speech opposing the NSA director nominee, Sen. Ron Wyden surfaced a previously undisclosed abuse of Section 702 surveillance authority ahead of its upcoming reauthorization deadline, renewing concerns about warrantless collection practices.

**[Ex-NSA Directors Discuss 'Red Line' for Offensive Cyberattacks](https://www.darkreading.com/cyber-risk/ex-nsa-directors-red-line-offensive-cyberattacks)**
*Dark Reading*
Four former NSA chiefs representing nearly the full history of U.S. Cyber Command debated where to draw the line on offensive cyber operations, with disagreement surfacing over appropriate escalation thresholds against state-level adversaries.
