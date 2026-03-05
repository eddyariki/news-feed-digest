# Security Digest — 2026-03-05

A day of major law enforcement wins — Europol dismantled the Tycoon 2FA phishing platform and seized the LeakBase credential forum — while Cisco SD-WAN vulnerabilities reached active exploitation status and AI researchers catalogued a growing range of adversarial attacks on multimodal and RAG-backed LLM systems.

---

## AI Security Research

**[Image-based Prompt Injection: Hijacking Multimodal LLMs through Visually Embedded Adversarial Instructions](https://arxiv.org/abs/2603.03637)**
*arXiv cs.CR*
Researchers study a black-box attack in which adversarial instructions are embedded directly into images to hijack multimodal LLMs, bypassing text-layer defenses. The work highlights a structural vulnerability in any vision-language pipeline that processes untrusted visual inputs.

**[When Safety Becomes a Vulnerability: Exploiting LLM Alignment Homogeneity for Transferable Blocking in RAG](https://arxiv.org/abs/2603.03919)**
*arXiv cs.CR*
Attackers can exploit the uniformity of safety-aligned LLMs to craft adversarially poisoned documents that block RAG systems from answering targeted queries across different model families. The availability attack requires no access to the target model's weights.

**[When Memory Becomes a Vulnerability: Multi-turn Jailbreak Attacks against Text-to-Image Generation Systems](https://arxiv.org/abs/2504.20376)**
*arXiv cs.CR*
The multi-turn memory mechanism in T2I systems like DALL·E 3 — designed to improve coherence — can be exploited to progressively smuggle harmful generation intent across conversation turns. This paper analyzes the attack surface and proposes defenses.

**[Dual-Modality Multi-Stage Adversarial Safety Training for Multimodal Web Agents](https://arxiv.org/abs/2603.04364)**
*arXiv cs.CR*
Web agents that process both screenshots and accessibility trees face cross-modal injection attacks; this paper proposes adversarial training across both modalities to harden agents against prompt injection via either channel.

**[Safety Guardrails for LLM-Enabled Robots](https://arxiv.org/abs/2503.07885)**
*arXiv cs.CR*
This work surveys and tests guardrail mechanisms for LLM-backed robots, covering both average-case hallucination failures and targeted jailbreak attacks that could cause unsafe physical actions.

**[ceLLMate: Sandboxing Browser AI Agents](https://arxiv.org/abs/2512.12594)**
*arXiv cs.CR*
Browser-using agents are increasingly exposed to adversarial web content; ceLLMate proposes a sandboxing framework that enforces least-privilege execution policies to contain malicious instructions encountered during browsing.

**[Reasoning models struggle to control their chains of thought, and that's good](https://openai.com/index/reasoning-models-chain-of-thought-controllability)**
*OpenAI*
OpenAI's CoT-Control study finds that reasoning models resist attempts to manipulate or suppress their internal thought chains, reinforcing chain-of-thought monitorability as a practical AI safety property.

---

## Vulnerabilities & Exploits

**[Europol-Led Operation Takes Down Tycoon 2FA Phishing-as-a-Service Linked to 64,000 Attacks](https://thehackernews.com/2026/03/europol-led-operation-takes-down-tycoon.html)**
*The Hacker News*
Tycoon 2FA, a subscription-based PhaaS toolkit capable of bypassing MFA via adversary-in-the-middle credential harvesting, was dismantled by a coalition of law enforcement agencies and private vendors. The platform had powered over 64,000 attacks.

**[FBI and Europol Seize LeakBase Forum Used to Trade Stolen Credentials](https://thehackernews.com/2026/03/fbi-and-europol-seize-leakbase-forum.html)**
*The Hacker News*
LeakBase, a forum with 142,000+ members used to buy and sell stolen data and cybercrime tools, was seized in a joint U.S.–European operation. The DOJ is pursuing charges against its operators.

**[Wikipedia hit by self-propagating JavaScript worm that vandalized pages](https://www.bleepingcomputer.com/news/security/wikipedia-hit-by-self-propagating-javascript-worm-that-vandalized-pages/)**
*Bleeping Computer*
A self-replicating JavaScript worm spread across multiple Wikimedia wikis by modifying user scripts, enabling it to propagate automatically to anyone who loaded the compromised pages. The Wikimedia Foundation has since contained the incident.

**[Cisco Drops 48 New Firewall Vulnerabilities, 2 Critical](https://www.darkreading.com/vulnerabilities-threats/cisco-48-firewall-vulnerabilities-2-critical)**
*Dark Reading*
Cisco released patches for 50 edge device vulnerabilities, including two rated 10/10 on the CVSS scale. Administrators should prioritize patching immediately given Cisco's current active-exploitation track record.

**[Cisco Confirms Active Exploitation of Two Catalyst SD-WAN Manager Vulnerabilities](https://thehackernews.com/2026/03/cisco-confirms-active-exploitation-of.html)**
*The Hacker News*
CVE-2026-20122 (arbitrary file overwrite, CVSS 7.1) and a second flaw in Catalyst SD-WAN Manager are being actively exploited in the wild. Cisco urges immediate upgrades.

**[WordPress membership plugin bug exploited to create admin accounts](https://www.bleepingcomputer.com/news/security/wordpress-membership-plugin-bug-exploited-to-create-admin-accounts/)**
*Bleeping Computer*
A critical vulnerability in the User Registration & Membership plugin (60,000+ installs) is being actively exploited to silently create administrator-level accounts. Sites running the plugin should update immediately.

**[Google says 90 zero-days were exploited in attacks last year](https://www.bleepingcomputer.com/news/security/google-says-90-zero-days-were-exploited-in-attacks-last-year/)**
*Bleeping Computer*
Google's Threat Intelligence Group tracked 90 zero-day exploits throughout 2025, with nearly half targeting enterprise software and appliances — a trend that underscores attackers' continued focus on network infrastructure and security tooling.

**[APT28-Linked Campaign Deploys BadPaw Loader and MeowMeow Backdoor in Ukraine](https://thehackernews.com/2026/03/apt28-linked-campaign-deploys-badpaw.html)**
*The Hacker News*
A Russian APT28-linked campaign is targeting Ukrainian entities with two previously undocumented malware families — BadPaw (loader) and MeowMeow (backdoor) — delivered via phishing emails with ZIP archive lures.

**[Hacked App Part of US/Israeli Propaganda Campaign Against Iran](https://www.schneier.com/blog/archives/2026/03/hacked-app-part-of-us-israeli-propaganda-campaign-against-iran.html)**
*Schneier on Security*
The BadeSaba Calendar prayer app, downloaded over 5 million times, was compromised and used to push push notifications to Iranian users timed around Israeli military operations. Bruce Schneier contextualizes the operation within the broader US/Israeli intelligence campaign.

**[Israel Hacked Traffic Cameras in Iran](https://www.schneier.com/blog/archives/2026/03/israel-hacked-traffic-cameras-in-iran.html)**
*Schneier on Security*
Reporting confirms Israeli intelligence used hacked Iranian traffic cameras as part of the operation that assisted in targeting that country's leadership. The New York Times story details the intelligence tradecraft involved.

**[Phobos ransomware admin pleads guilty to wire fraud conspiracy](https://www.bleepingcomputer.com/news/security/phobos-ransomware-admin-pleads-guilty-to-wire-fraud-conspiracy/)**
*Bleeping Computer*
A Russian national pleaded guilty to administering the Phobos ransomware-as-a-service operation, which breached hundreds of victims worldwide. The case is a rare successful prosecution of a ransomware platform operator.

---

## Policy & Compliance

**[Preparing for the Quantum Era: Post-Quantum Cryptography for Security Leaders](https://thehackernews.com/2026/03/preparing-for-quantum-era-post-quantum.html)**
*The Hacker News*
With adversaries already conducting "harvest now, decrypt later" campaigns against encrypted data, this primer outlines what security leaders need to know about NIST's finalized post-quantum cryptographic standards and the transition timeline.

**[2026 Browser Data Reveals Major Enterprise Security Blind Spots](https://www.bleepingcomputer.com/news/security/2026-browser-data-reveals-major-enterprise-security-blind-spots/)**
*Bleeping Computer*
Keep Aware's 2026 State of Browser Security Report finds 41% of enterprise employees use AI web tools through the browser, yet most organizations still treat the browser as an extension of network or endpoint security rather than managing it as a distinct risk surface.

**[Where Multi-Factor Authentication Stops and Credential Abuse Starts](https://thehackernews.com/2026/03/where-multi-factor-authentication-stops.html)**
*The Hacker News*
Attackers continue to compromise Windows environments daily using valid credentials despite MFA rollouts, exploiting coverage gaps in legacy authentication protocols. The article outlines the specific Windows credential pathways MFA typically does not cover.
