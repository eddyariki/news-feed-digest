# Security Digest — 2026-05-14

Patch Tuesday dominates the news cycle, with Microsoft pushing fixes for 138 vulnerabilities — many of them surfaced by its new AI-driven scanning system — while researchers warn that AI agents are now both finding and weaponizing exploits at scale. The arXiv firehose is heavy on jailbreaks, indirect prompt injection, and red-teaming of agent frameworks, alongside ransomware hits on Foxconn and a sustained China-linked intrusion against an Azerbaijani energy firm.

---

## AI Security Research

[OpenAI's GPT-5.5 is as Good as Mythos at Finding Security Vulnerabilities](https://www.schneier.com/blog/archives/2026/05/openais-gpt-5-5-is-as-good-as-mythos-at-finding-security-vulnerabilities.html)
*Schneier on Security* — The UK AI Security Institute finds GPT-5.5 matches Claude Mythos at vulnerability discovery, requiring more prompt scaffolding but reaching comparable results — and OpenAI's model is generally available, lowering the bar for both defenders and attackers.

[MT-JailBench: A Modular Benchmark for Understanding Multi-Turn Jailbreak Attacks](https://arxiv.org/abs/2605.11002)
*ArXiv cs.AI* — A standardized benchmark for multi-turn jailbreaks that decouples attack strategy from judge model and retry budget, addressing the inconsistent evaluation conditions that have made prior multi-turn results hard to compare.

[Few-Shot Truly Benign DPO Attack for Jailbreaking LLMs](https://arxiv.org/abs/2605.10998)
*ArXiv cs.AI* — Researchers show Direct Preference Optimization fine-tuning APIs introduce a harder-to-audit safety failure mode than SFT, weakening alignment with even small amounts of innocuous-looking preference data.

[IPI-proxy: An Intercepting Proxy for Red-Teaming Web-Browsing AI Agents Against Indirect Prompt Injection](https://arxiv.org/abs/2605.11868)
*ArXiv cs.AI* — A tool that injects adversarial instructions into responses from whitelisted domains, exposing a gap in current IPI benchmarks that ship pre-built adversarial pages unreachable to domain-restricted enterprise agents.

[ExploitGym: Can AI Agents Turn Security Vulnerabilities into Real Attacks?](https://arxiv.org/abs/2605.11086)
*ArXiv cs.AI* — A new evaluation environment measures whether AI agents can convert known vulnerabilities into working exploits — testing the harder downstream capability of memory-layout reasoning and runtime adaptation, not just bug discovery.

[AgentShield: Deception-based Compromise Detection for Tool-using LLM Agents](https://arxiv.org/abs/2605.11026)
*ArXiv cs.CL* — A detection-first defense that plants decoy tools and resources to surface IPI compromises that slipped past prevention, with multilingual evaluation including Kurdish and Arabic.

[Robust LLM Unlearning Against Relearning Attacks: The Minor Components in Representations Matter](https://arxiv.org/abs/2605.11685)
*ArXiv cs.CL* — Existing unlearning techniques are fragile because residual "minor components" in hidden representations let removed knowledge be rapidly relearned — a particular concern for open-weight model releases.

[Context-Aware Spear Phishing: Generative AI-Enabled Attacks Against Individuals via Public Social Media Data](https://arxiv.org/abs/2605.11268)
*ArXiv cs.CR* — A demonstration that minimal public social-media data is enough for GenAI to produce highly personalized, style-matched phishing messages that bypass generic content-moderation safeguards.

[FlowSteer: Prompt-Only Workflow Steering Exposes Planning-Time Vulnerabilities in Multi-Agent LLM Systems](https://arxiv.org/abs/2605.11514)
*ArXiv cs.CR* — Prompts alone can reshape planner-executor agent organizations — assigning roles, routing, and dependencies — opening a planning-time attack surface that doesn't require touching the underlying infrastructure.

[Five Attacks on x402 Agentic Payment Protocol](https://arxiv.org/abs/2605.11781)
*ArXiv cs.CR* — A formal and empirical security analysis of the HTTP 402-based agent payments protocol identifies five exploitable cross-layer flaws spanning synchronous authorization and asynchronous blockchain settlement.

## Vulnerabilities & Exploits

[Microsoft's MDASH AI System Finds 16 Windows Flaws Fixed in Patch Tuesday](https://thehackernews.com/2026/05/microsofts-mdash-ai-system-finds-16.html)
*The Hacker News* — Microsoft revealed MDASH, a multi-model agentic scanning harness using specialized AI agents per vulnerability class; it surfaced 16 of this month's Windows fixes and is in limited private preview with select customers.

[Microsoft Patches 138 Vulnerabilities, Including DNS and Netlogon RCE Flaws](https://thehackernews.com/2026/05/microsoft-patches-138-vulnerabilities.html)
*The Hacker News* — May's Patch Tuesday addresses 138 flaws (30 Critical, 104 Important), with 61 privilege-escalation bugs leading the pack; none are listed as publicly known or under active attack at release.

[Patch Tuesday, May 2026 Edition](https://krebsonsecurity.com/2026/05/patch-tuesday-may-2026-edition/)
*Krebs on Security* — Apple, Google, Microsoft, Mozilla, and Oracle all pushed near-record patch volumes this cycle, with Krebs noting that AI-assisted code review is visibly accelerating the cadence of vendor disclosures.

[New critical Exim mailer flaw allows remote code execution](https://www.bleepingcomputer.com/news/security/new-critical-exim-mailer-flaw-allows-remote-code-execution/)
*BleepingComputer* — A critical bug in certain Exim configurations enables unauthenticated remote code execution against the open-source MTA, which remains widely deployed on internet-facing Linux mail servers.

[Windows BitLocker zero-day gives access to protected drives, PoC released](https://www.bleepingcomputer.com/news/security/windows-bitlocker-zero-day-gives-access-to-protected-drives-poc-released/)
*BleepingComputer* — Proof-of-concept exploits for two unpatched Windows flaws — "YellowKey" (BitLocker bypass) and "GreenPlasma" (privilege escalation) — have been published, exposing encrypted drives ahead of any vendor fix.

[Foxconn confirms cyberattack claimed by Nitrogen ransomware gang](https://www.bleepingcomputer.com/news/security/electronics-giant-foxconn-confirms-cyberattack-on-north-american-factories/)
*BleepingComputer* — The world's largest electronics manufacturer confirmed a Nitrogen ransomware intrusion against its North American factories and says operations are progressively returning to normal.

[Foxconn Attack Highlights Manufacturing's Cyber Crisis](https://www.darkreading.com/cyberattacks-data-breaches/foxconn-attack-manufacturing-cyber-crisis)
*Dark Reading* — The Foxconn breach is one of roughly 600 manufacturing-sector hits this year, as ransomware crews increasingly target factories for their low downtime tolerance and willingness to pay quickly.

[China's 'FamousSparrow' APT Nests in South Caucasus Energy Firm](https://www.darkreading.com/cyberattacks-data-breaches/china-famoussparrow-apt-south-caucasus-energy-firm)
*Dark Reading* — Bitdefender attributes a multi-wave intrusion against an Azerbaijani oil and gas company (late 2025 through Feb 2026) to China-linked FamousSparrow, marking the group's expansion beyond its traditional hospitality, telecom, and government targets.

[GemStuffer Abuses 150+ RubyGems to Exfiltrate Scraped U.K. Council Portal Data](https://thehackernews.com/2026/05/gemstuffer-abuses-150-rubygems-to.html)
*The Hacker News* — Socket researchers describe a campaign weaponizing 150+ RubyGems packages not for developer compromise but as exfiltration channels for data scraped from public-facing UK government servers.

[LatAm Vibe Hackers Generate Custom Hacking Tools on the Fly](https://www.darkreading.com/cloud-security/ai-agents-generate-custom-hacking-tools)
*Dark Reading* — Two recent campaigns against Mexican and Brazilian targets used AI agents to generate bespoke attack tooling on demand — an operational step beyond static AI-assisted phishing.

[Android Adds Intrusion Logging for Sophisticated Spyware Forensics](https://thehackernews.com/2026/05/android-adds-intrusion-logging-for.html)
*The Hacker News* — Google's new opt-in Intrusion Logging feature in Advanced Protection Mode stores persistent, privacy-preserving forensic logs to support post-compromise investigation of high-end mobile spyware.

[Tables Turn on 'The Gentlemen' RaaS Gang With Data Leak](https://www.darkreading.com/threat-intelligence/gentlemen-raas-gang-data-leak)
*Dark Reading* — An OPSEC failure leaks internal data from "The Gentlemen" ransomware-as-a-service operation, exposing the generous affiliate model and organizational structure behind the group's rise.

## Policy & Compliance

[US govt seeks Instructure testimony on massive Canvas cyberattack](https://www.bleepingcomputer.com/news/security/us-govt-seeks-instructure-testimony-on-massive-canvas-cyberattack/)
*BleepingComputer* — The House Homeland Security Committee is calling Instructure executives to testify on two ShinyHunters-linked attacks against Canvas that stole student data and disrupted schools during final exams.

[Checkbox Assessments Aren't Fit to Measure to Risk](https://www.darkreading.com/cyber-risk/checkbox-assessments-aren-t-fit-to-measure-to-risk)
*Dark Reading* — Annual compliance-style audits keep producing security governance theater; a wave of new vendors is targeting the gap between audit checkboxes and actual risk posture.

[Most Remediation Programs Never Confirm the Fix Actually Worked](https://thehackernews.com/2026/05/most-remediation-programs-never-confirm.html)
*The Hacker News* — Mandiant's M-Trends 2026 puts mean time to exploit at roughly negative seven days against a 32-day median remediation window, exposing how few programs validate that closed tickets actually correspond to closed vulnerabilities.
