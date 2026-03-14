# Security Digest — 2026-03-14

Today's threat landscape is dominated by supply-chain attacks targeting developer tooling and widely-used SDKs, while ransomware continues to hammer small and midsize businesses and Microsoft rushes an out-of-band patch for an actively threatening RCE flaw.

---

## AI Security Research

**[OpenClaw AI Agent Flaws Could Enable Prompt Injection and Data Exfiltration](https://thehackernews.com/2026/03/openclaw-ai-agent-flaws-could-enable.html)**
*The Hacker News*

China's CNCERT has warned that OpenClaw (formerly Clawdbot/Moltbot), a popular open-source autonomous AI agent platform, ships with weak default security configurations that leave deployments vulnerable to prompt injection and data exfiltration. The advisory highlights the systemic risk of AI agent frameworks that prioritize capability over secure-by-default posture.

---

## Vulnerabilities & Exploits

**[Microsoft releases Windows 11 OOB hotpatch to fix RRAS RCE flaw](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-windows-11-oob-hotpatch-to-fix-rras-rce-flaw/)**
*BleepingComputer*

Microsoft issued an out-of-band hotpatch for Windows 11 Enterprise devices to address a remote code execution vulnerability in the Routing and Remote Access Service (RRAS). The emergency patch bypasses the normal Patch Tuesday cycle, signaling elevated urgency for affected enterprise deployments.

**[AppsFlyer Web SDK hijacked to spread crypto-stealing JavaScript code](https://www.bleepingcomputer.com/news/security/appsflyer-web-sdk-used-to-spread-crypto-stealer-javascript-code/)**
*BleepingComputer*

The AppsFlyer Web SDK was briefly compromised this week with malicious JavaScript designed to steal cryptocurrency from visitors of sites that had integrated the SDK. The incident is a textbook supply-chain attack, underscoring the risk of third-party script dependencies in web applications.

**[GlassWorm Supply-Chain Attack Abuses 72 Open VSX Extensions to Target Developers](https://thehackernews.com/2026/03/glassworm-supply-chain-attack-abuses-72.html)**
*The Hacker News*

Researchers have uncovered a significant escalation of the GlassWorm campaign, which now exploits `extensionPack` and `extensionDependencies` metadata in the Open VSX registry to propagate malicious code transitively through 72 extensions — without embedding a loader in each listing directly. Developers using VS Code-compatible editors who rely on the Open VSX marketplace should audit installed extensions immediately.

**[Ransomware Attacks Hitting Japan's Small, Midsize Firms](https://japannews.yomiuri.co.jp/business/companies/20260315-316491/)**
*The Japan News*

Japan's National Police Agency reported 143 ransomware attacks on small and midsize companies in 2025, representing 60% of all domestic ransomware incidents for the second consecutive year. The trend reflects attackers' continued preference for targeting resource-constrained organizations with weaker defenses over large enterprises.
