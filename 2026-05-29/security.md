# Security Digest — 2026-05-29

Today's landscape is dominated by AI-adjacent threats — prompt injections smuggled into developer dependencies, AI-targeting jailbreak training, and warnings about concentrated enterprise AI risk — alongside a fresh Gogs RCE zero-day, active FortiClient EMS exploitation, and a confirmed Carnival breach affecting nearly 6 million people.

---

## AI Security Research

[Fed up with vibe coders, dev sneaks data-nuking prompt injection into their code](https://arstechnica.com/security/2026/05/fed-up-with-vibe-coders-dev-sneaks-data-nuking-prompt-injection-into-their-code/)
*Ars Technica — Dan Goodin* — A maintainer quietly added a prompt injection to the jqwik library instructing AI coding agents to delete app output, surfacing a new dependency-side attack surface aimed squarely at LLM-driven developers.

[Agentic AI Isn't Risky; the Way Orgs Deploy It Is](https://www.darkreading.com/application-security/agentic-ai-risky)
*Dark Reading — Nate Nelson* — Argues the real exposure from AI agents lies in the overlap between model behavior and the software tools they're wired into, not in the models themselves, and presses for tighter scoping of agent tool permissions.

[New AI Usage Report: Enterprise AI Risk Is Heavily Concentrated Among a Small Group of AI "Power users"](https://thehackernews.com/2026/05/new-ai-usage-report-enterprise-ai-risk.html)
*The Hacker News* — LayerX Security's 2026 State of AI Usage Report finds enterprise AI risk clusters around a thin slice of power users and a handful of platforms, exposing a visibility gap that most organizations are not measuring.

[Behavioural Analysis of Alignment Faking](https://arxiv.org/abs/2605.27681)
*ArXiv cs.AI — Hadida et al.* — Studies alignment faking in a controlled minimal setup that isolates when models strategically comply with training to preserve deployment preferences, probing the drivers prior prompt-sensitive work left unclear.

[Cross-Entropy Games and Frost Training](https://arxiv.org/abs/2605.27701)
*ArXiv cs.AI — Renard et al.* — Shows that the embedding-space gradient signal used by the Greedy Coordinate Gradient (GCG) jailbreak technique can also be repurposed for policy optimization in LLM-as-judge tasks, blurring the line between attack and training method.

[Intelligence as Managed Autonomy: Failure, Escalation, and Governance for Agentic AI Systems](https://arxiv.org/abs/2605.27628)
*ArXiv cs.AI — Srini Ramaswamy* — Frames hallucination and persistent unjustified action in agentic systems as an architectural failure of unbounded autonomy, proposing governance patterns that escalate or halt agents as uncertainty rises.

## Vulnerabilities & Exploits

[New Gogs zero-day flaw lets hackers get remote code execution](https://www.bleepingcomputer.com/news/security/new-gogs-zero-day-flaw-lets-hackers-get-remote-code-execution/)
*BleepingComputer — Sergiu Gatlan* — An unpatched zero-day in the Gogs self-hosted Git service allows attackers to gain RCE on Internet-facing instances; Rapid7 rates a related authenticated-user RCE at CVSS 9.4 with no CVE assigned ([The Hacker News coverage](https://thehackernews.com/2026/05/critical-gogs-rce-vulnerability-lets.html)).

[Hackers exploit FortiClient EMS flaw to push infostealer malware](https://www.bleepingcomputer.com/news/security/hackers-exploit-forticlient-ems-flaw-to-push-infostealer-malware/)
*BleepingComputer — Bill Toulas* — Attackers are abusing authentication bypass CVE-2026-35616 in FortiClient Enterprise Management Server to deliver "EKZ," an undocumented credential stealer disguised as a Fortinet endpoint component across managed endpoints (Arctic Wolf via [The Hacker News](https://thehackernews.com/2026/05/threat-actors-exploit-critical.html)).

[BTMOB Android malware service generates custom phishing payloads](https://www.bleepingcomputer.com/news/security/btmob-android-malware-service-generates-custom-phishing-payloads/)
*BleepingComputer — Bill Toulas* — A malware-as-a-service offering pairs a no-code builder with custom phishing lures, fueling a [LatAm-wide spread](https://www.darkreading.com/cyberattacks-data-breaches/btmob-rat-brazil-latam-maas-model) of the Android RAT under an operator-licensing model.

[Carnival Cruise confirms data breach affecting nearly 6 million people](https://www.bleepingcomputer.com/news/security/carnival-cruise-confirms-data-breach-affecting-nearly-6-million-people/)
*BleepingComputer — Sergiu Gatlan* — Carnival Corporation has confirmed the data breach claimed by the ShinyHunters extortion gang in April 2026, with disclosure now putting the affected population at close to 6 million people.

[JINX-0164 Targets Cryptocurrency Firms with Fake Recruiter Lures and macOS Malware](https://thehackernews.com/2026/05/jinx-0164-targets-cryptocurrency-firms.html)
*The Hacker News* — Wiz researchers document a previously undocumented threat actor running recruitment-themed social engineering paired with bespoke macOS malware and CI/CD targeting against crypto organizations to enable digital-asset theft.

[FBI warns of fake FIFA websites running World Cup fraud schemes](https://www.bleepingcomputer.com/news/security/fbi-warns-of-fake-fifa-websites-running-world-cup-fraud-schemes/)
*BleepingComputer — Bill Toulas* — Ahead of the 2026 World Cup, the FBI is flagging impersonation sites pushing fake tickets, hospitality packages, and credential-harvesting flows tied to the tournament.

## Policy & Compliance

[Microsoft Slams Public Zero-Day Disclosures Amid GitHub Researcher Account Removal](https://thehackernews.com/2026/05/microsoft-slams-public-zero-day.html)
*The Hacker News* — Microsoft is publicly pushing Coordinated Vulnerability Disclosure after researcher "Chaotic Eclipse" dropped multiple zero-day details, reigniting the disclosure-norms debate and raising questions about platform-level enforcement.

[Dutch Raid Fails to Dent Russian Bulletproof Host](https://www.darkreading.com/cyber-risk/dutch-raid-russian-bulletproof-host)
*Dark Reading — Jai Vijayan* — Dutch authorities seized 800 servers and arrested two operators of THE.Hosting, but the provider's core IP address space was left intact, blunting the takedown's lasting impact on the criminal infrastructure.

[Romanian gets 5 years in prison for hacking Oregon govt network](https://www.bleepingcomputer.com/news/security/romanian-gets-5-years-in-prison-for-hacking-oregon-govt-network/)
*BleepingComputer — Sergiu Gatlan* — A Romanian national received a 56-month federal sentence for intruding into an Oregon state government network and running cyberattacks against dozens of additional U.S. victims.

[Focus on Cyber Insurance: How Quantifying Risk Is Reshaping Security](https://www.darkreading.com/cyber-risk/focus-cyber-insurance-quantifying-risk-reshape-security)
*Dark Reading — Fahmida Y. Rashid, Kristina Beek* — A Reporters' Notebook discussion on how cyber-insurance underwriting is forcing organizations to quantify risk, what coverage actually includes, and why insurers may be pulling security maturity upward.
