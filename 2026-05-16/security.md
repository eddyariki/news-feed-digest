# Security Digest — 2026-05-16

Today's headlines split between an active on-prem Exchange zero-day under exploitation and a flood of new research into the security of LLM agents, their third-party skills, and their supply chains. AI is showing up on both sides of the fence: Microsoft is using fleets of agents to hunt Windows bugs, while researchers keep finding new ways those same agents can be tricked, fingerprinted, or co-opted.

---

## AI Security Research

[The Great Pretender: A Stochasticity Problem in LLM Jailbreak](https://arxiv.org/abs/2605.14418) — *ArXiv cs.CR.* The authors argue that the dominant jailbreak-attack benchmarks systematically overstate success rates because they ignore the inherent stochasticity of LLM sampling, calling much of the published jailbreak literature into question.

[WARD: Adversarially Robust Defense of Web Agents Against Prompt Injections](https://arxiv.org/abs/2605.15030) — *ArXiv cs.CR.* Existing guard models for web agents collapse under adaptive prompt-injection attacks embedded in HTML or visual interfaces; WARD proposes an adversarially trained defense aimed at closing that gap.

[AgentTrap: Measuring Runtime Trust Failures in Third-Party Agent Skills](https://arxiv.org/abs/2605.13940) — *ArXiv cs.CR.* As third-party "skills" become the de facto package ecosystem for LLM agents, this work introduces a framework to measure how often skills violate trust boundaries at runtime — a precursor to treating skill marketplaces as a real attack surface.

[Exploiting LLM Agent Supply Chains via Payload-less Skills](https://arxiv.org/abs/2605.14460) — *ArXiv cs.CR.* A companion line of work shows that malicious agent skills don't need executable payloads at all: natural-language instructions and templates alone are enough to hijack agent behavior across an open marketplace.

[ExploitBench: A Capability Ladder Benchmark for LLM Cybersecurity Agents](https://arxiv.org/abs/2605.14153) — *ArXiv cs.CR.* Rather than treating "did it crash?" as exploitation success, ExploitBench grades agents along a ladder from triggering a buggy line to achieving full target control, giving a more honest picture of offensive LLM capability.

[RLCracker: Evaluating the Worst-Case Vulnerability of LLM Watermarks with Adaptive RL Attacks](https://arxiv.org/abs/2509.20924) — *ArXiv cs.CR.* Prior watermarking schemes claimed robustness to paraphrasing; RLCracker trains an RL attacker that adaptively erases watermarks, exposing those robustness claims as fragile in the adversarial worst case.

["Tab, Tab, Bug": Security Pitfalls of Next Edit Suggestions in AI-Integrated IDEs](https://arxiv.org/abs/2602.06759) — *ArXiv cs.CR.* Next Edit Suggestion features in IDEs construct rich context from across the workspace, and the authors show this enables novel injection paths where a single tainted file can steer the assistant into emitting vulnerable edits elsewhere in the project.

[Capacitive Touchscreens at Risk: A Practical Side-Channel Attack on Smartphones via Electromagnetic Emanations](https://arxiv.org/abs/2605.14633) — *ArXiv cs.CR.* TESLA, a contactless EM side-channel attack, is shown to recover touchscreen input from smartphones without invasive probes, raising the bar for what counts as a "physical-only" threat model.

[Bypassing On-Camera Age-Verification Checks](https://www.schneier.com/blog/archives/2026/05/bypassing-on-camera-age-verification-checks.html) — *Schneier on Security.* AI-based video age-verification systems can be defeated with a fake mustache — a small but pointed reminder that biometric gating is only as strong as its weakest visual feature.

[Microsoft pits more than 100 AI agents against each other to find Windows vulnerabilities](https://the-decoder.com/microsoft-pits-more-than-100-ai-agents-against-each-other-to-find-windows-vulnerabilities/) — *The Decoder.* Microsoft's MDASH system used over 100 specialized agents to surface 16 Windows security flaws on a single Patch Tuesday, four of them critical — though it declined to disclose which models power the swarm.

[The Boring Stuff is Dangerous Now](https://www.darkreading.com/cyber-risk/ai-code-and-agents-forces-defenders-adapt) — *Dark Reading.* AI agents that can hunt and exploit obscure vulnerabilities are arriving at the same time as a tide of AI-generated code that may itself be flawed, forcing defenders to rethink what "low-priority" bugs even mean.

## Vulnerabilities & Exploits

[On-Prem Microsoft Exchange Server CVE-2026-42897 Exploited via Crafted Email](https://thehackernews.com/2026/05/on-prem-microsoft-exchange-server-cve.html) — *The Hacker News.* Microsoft has disclosed an actively exploited spoofing/XSS vulnerability (CVSS 8.1) in on-premise Exchange that lets attackers run arbitrary code against Outlook-on-the-web users via a crafted email. Mitigation guidance is [also out from Microsoft](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-exchange-zero-day-flaw-exploited-in-attacks/) for the same flaw.

[Microsoft Exchange, Windows 11 hacked on second day of Pwn2Own](https://www.bleepingcomputer.com/news/security/pwn2own-day-two-hackers-demo-microsoft-exchange-windows-11-red-had-enterprise-linux-zero-days/) — *BleepingComputer.* Day two of Pwn2Own Berlin 2026 produced 15 unique zero-days against Windows 11, Microsoft Exchange, and Red Hat Enterprise Linux for Workstations, with $385,750 in awards paid out.

[Popular node-ipc npm package compromised to steal credentials](https://www.bleepingcomputer.com/news/security/popular-node-ipc-npm-package-compromised-to-steal-credentials/) — *BleepingComputer.* Malicious versions of the widely used node-ipc package were published to npm with credential-stealing payloads, marking yet another high-impact supply-chain compromise in the JavaScript ecosystem.

[TanStack Supply Chain Attack Hits Two OpenAI Employee Devices, Forces macOS Updates](https://thehackernews.com/2026/05/tanstack-supply-chain-attack-hits-two.html) — *The Hacker News.* OpenAI disclosed that the "Mini Shai-Hulud" supply chain attack on TanStack reached two corporate devices; the company says no user data, production systems, or IP were affected, but the incident triggered company-wide macOS updates.

[NGINX Remote Code Execution Vulnerability Disclosed](https://gigazine.net/news/20260515-nginx-remote-code-execution/) — *Gigazine.* Researchers at DepthFirst found four memory-corruption issues in NGINX, including CVE-2026-42945 — a heap buffer overflow that traces back to 2008 and went unpatched for nearly 18 years before being caught.

[Funnel Builder WordPress plugin bug exploited to steal credit cards](https://www.bleepingcomputer.com/news/security/funnel-builder-wordpress-plugin-bug-exploited-to-steal-credit-cards/) — *BleepingComputer.* A critical flaw in the Funnel Builder plugin is being abused in the wild to inject JavaScript skimmers into WooCommerce checkout pages. A separate set of [Avada Builder plugin flaws](https://www.bleepingcomputer.com/news/security/avada-builder-wordpress-plugin-flaws-allow-site-credential-theft/) — installed on ~1M sites — also enable arbitrary file reads and database extraction.

[Turla Turns Kazuar Backdoor Into Modular P2P Botnet for Persistent Access](https://thehackernews.com/2026/05/turla-turns-kazuar-backdoor-into.html) — *The Hacker News.* The Russian state-sponsored Turla group has re-engineered its long-running Kazuar backdoor into a modular peer-to-peer botnet, trading central infrastructure for stealth and persistence on compromised hosts.

[Four OpenClaw Flaws Enable Data Theft, Privilege Escalation, and Persistence](https://thehackernews.com/2026/05/four-openclaw-flaws-enable-data-theft.html) — *The Hacker News.* Cyera disclosed "Claw Chain," a set of four flaws in OpenClaw that can be combined to steal data, escalate privileges, and persist — notable because OpenClaw is increasingly being adopted as an agentic backbone.

[Taiwan Bullet Train Hack Highlights Cybersecurity Gaps in Rail Systems](https://www.darkreading.com/ics-ot-security/taiwan-incident-highlights-cybersecurity-gaps) — *Dark Reading.* A student using software-defined radio shut down three Taiwanese bullet trains for nearly an hour, triggering an anti-terrorism response and exposing how fragile rail control systems remain to entry-level RF attacks.

## Policy & Compliance

[CISA Adds Cisco SD-WAN CVE-2026-20182 to KEV After Admin Access Exploits](https://thehackernews.com/2026/05/cisa-adds-cisco-sd-wan-cve-2026-20182.html) — *The Hacker News.* CISA added a newly disclosed Cisco Catalyst SD-WAN Controller flaw to its Known Exploited Vulnerabilities catalog, putting federal agencies on a mandatory remediation clock.

[Congress Puts Heat on Instructure After Canvas Outage](https://www.darkreading.com/cyberattacks-data-breaches/congress-instructure-shinyhunters-attacks) — *Dark Reading.* The House Homeland Security Committee sent a formal letter to Instructure on the same day the company said it had reached "an agreement" with the ShinyHunters extortion crew behind the Canvas cyberattack — escalating scrutiny of edtech incident handling.

[Microsoft backpedals: Edge to stop loading passwords into memory](https://www.bleepingcomputer.com/news/microsoft/microsoft-edge-to-stop-loading-cleartext-passwords-in-memory-on-startup/) — *BleepingComputer.* After previously calling the behavior "by design," Microsoft will change Edge so it no longer loads saved passwords into process memory in cleartext at startup — a reversal driven by sustained public pressure.

[Microsoft to automatically roll back faulty Windows drivers](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-automatically-roll-back-faulty-windows-drivers/) — *BleepingComputer.* Microsoft is rolling out a capability to remotely revert problematic drivers delivered through Windows Update, a clear post-CrowdStrike posture shift toward platform-level rollback as a baseline safety control.
