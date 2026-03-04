# Security Digest — 2026-03-04

Today's threat landscape is dominated by a wave of high-severity vulnerabilities and active exploit campaigns — from a max-severity RCE in FreeScout to a sophisticated 23-exploit iOS kit used in espionage — while the research community publishes a surge of work on LLM jailbreaks, backdoor defenses, and AI-assisted penetration testing.

---

## AI Security Research

**[Manipulating AI Summarization Features](https://www.schneier.com/blog/archives/2026/03/manipulating-ai-summarization-features.html)**
*Schneier on Security*

Microsoft found over 50 unique prompts from 31 companies embedding hidden instructions in "Summarize with AI" buttons designed to inject persistence commands into AI assistant memory — biasing future responses toward their products. Bruce Schneier covers the implications of this prompt-injection-as-marketing tactic.

**[ZeroDayBench: Evaluating LLM Agents on Unseen Zero-Day Vulnerabilities for Cyberdefense](https://arxiv.org/abs/2603.02297)**
*ArXiv cs.AI / cs.CR*

A new benchmark tasks LLM agents with finding and patching 22 novel critical vulnerabilities in open-source software, offering the first structured evaluation of AI capability on genuinely unseen zero-days rather than known CVEs.

**[Comparing AI Agents to Cybersecurity Professionals in Real-World Penetration Testing](https://arxiv.org/abs/2512.09882)**
*ArXiv cs.AI / cs.CR*

The first head-to-head evaluation of AI agents against human professionals on a live ~8,000-host university network; introduces ARTEMIS, a multi-agent scaffold with dynamic prompt generation and automatic vulnerability discovery across 12 subnets.

**[TraceGuard: Process-Guided Firewall against Reasoning Backdoors in Large Language Models](https://arxiv.org/abs/2603.02436)**
*ArXiv cs.CR*

Proposes a firewall that monitors Chain-of-Thought reasoning traces to detect and block backdoor attacks where an adversary manipulates the model's intermediate reasoning to reach malicious conclusions while appearing logically sound.

**[TAO-Attack: Toward Advanced Optimization-Based Jailbreak Attacks for Large Language Models](https://arxiv.org/abs/2603.03081)**
*ArXiv cs.CL*

Introduces a new optimization-based jailbreak that addresses the core failure modes of prior approaches — frequent refusals, pseudo-harmful outputs, and inefficient token updates — substantially improving attack success rates against aligned LLMs.

**[Multimodal Multi-Agent Ransomware Analysis Using AutoGen](https://arxiv.org/abs/2601.20346)**
*ArXiv cs.CR*

Presents a multi-agent framework using AutoGen for classifying ransomware through combined static, heuristic, and behavioral signals across modalities, outperforming single-method detection approaches that traditionally fall short against modern variants.

**[MUSE: A Run-Centric Platform for Multimodal Unified Safety Evaluation of Large Language Models](https://arxiv.org/abs/2603.02482)**
*ArXiv cs.LG*

An open-source platform that tests whether LLM alignment holds across audio, image, and video inputs — not just text — using three multi-turn attack algorithms (Crescendo, PAIR, Violent Durian) with automated cross-modal payload generation.

**[Every Language Model Has a Forgery-Resistant Signature](https://arxiv.org/abs/2510.14086)**
*ArXiv cs.CR*

Demonstrates that a geometric constraint in language model architectures creates an inherent, forgery-resistant fingerprint that can be used to forensically identify model outputs — with implications for watermarking and model attribution.

---

## Vulnerabilities & Exploits

**[Mail2Shell zero-click attack lets hackers hijack FreeScout mail servers](https://www.bleepingcomputer.com/news/security/mail2shell-zero-click-attack-lets-hackers-hijack-freescout-mail-servers/)**
*BleepingComputer*

A maximum-severity vulnerability in the FreeScout open-source helpdesk platform allows unauthenticated remote code execution with no user interaction required — a zero-click RCE that gives attackers full server control on receipt of a crafted email.

**[Coruna iOS Exploit Kit Uses 23 Exploits Across Five Chains Targeting iOS 13–17.2.1](https://thehackernews.com/2026/03/coruna-ios-exploit-kit-uses-23-exploits.html)**
*The Hacker News*

Google's Threat Intelligence Group identified Coruna (aka CryptoWaters), a previously undocumented exploit kit with five full iOS exploit chains covering iOS 13 through 17.2.1 — used in both targeted espionage and financially motivated crypto theft attacks.

**[Cisco warns of max severity Secure FMC flaws giving root access](https://www.bleepingcomputer.com/news/security/cisco-warns-of-max-severity-secure-fmc-flaws-giving-root-access/)**
*BleepingComputer*

Cisco patched two maximum-severity vulnerabilities in its Secure Firewall Management Center software that could grant attackers root access; customers running FMC should treat this as urgent given the network-critical role of the platform.

**[VMware Aria Operations Bug Exploited, Cloud Resources at Risk](https://www.darkreading.com/cloud-security/vmware-aria-operations-bug-exploited-cloud-risk)**
*Dark Reading*

An actively exploited command injection flaw in VMware Aria Operations could grant broad access to victims' cloud environments; the bug is already being leveraged in the wild, raising the urgency for patching.

**[APT41-Linked Silver Dragon Targets Governments Using Cobalt Strike and Google Drive C2](https://thehackernews.com/2026/03/apt41-linked-silver-dragon-targets.html)**
*The Hacker News*

Check Point Research details Silver Dragon, an APT41-linked actor active since mid-2024 targeting European and Southeast Asian governments via phishing and public-facing server exploits, using legitimate services like Google Drive as C2 infrastructure to evade detection.

**[Fake Laravel Packages on Packagist Deploy RAT on Windows, macOS, and Linux](https://thehackernews.com/2026/03/fake-laravel-packages-on-packagist.html)**
*The Hacker News*

Malicious PHP packages disguised as Laravel utilities on Packagist deliver a cross-platform remote access trojan — a supply chain attack vector targeting PHP developers via the official package registry.

**[Europol-coordinated action disrupts Tycoon2FA phishing platform](https://www.bleepingcomputer.com/news/security/europol-coordinated-action-disrupts-tycoon2fa-phishing-platform/)**
*BleepingComputer*

International law enforcement disrupted Tycoon2FA, a major phishing-as-a-service platform responsible for tens of millions of phishing messages monthly, in a coordinated Europol-led operation.

**[FBI seizes LeakBase cybercrime forum, data of 142,000 members](https://www.bleepingcomputer.com/news/security/fbi-seizes-leakbase-cybercrime-forum-data-of-142-000-members/)**
*BleepingComputer*

The FBI seized LeakBase, a major cybercrime marketplace for hacking tools and stolen data — and now holds membership data on 142,000 of its users.

**[149 Hacktivist DDoS Attacks Hit 110 Organizations in 16 Countries After Middle East Conflict](https://thehackernews.com/2026/03/149-hacktivist-ddos-attacks-hit-110.html)**
*The Hacker News*

Radware reports a surge in retaliatory hacktivist DDoS activity following the U.S.-Israel military campaign against Iran, with two groups — Keymous+ and DieNet — accounting for nearly 70% of all attack volume between February 28 and March 2.

---

## Policy & Compliance

**[Anthropic CEO Dario Amodei calls OpenAI's messaging around military deal 'straight up lies,' report says](https://techcrunch.com/2026/03/04/anthropic-ceo-dario-amodei-calls-openais-messaging-around-military-deal-straight-up-lies-report-says/)**
*TechCrunch AI*

Anthropic withdrew from its Pentagon contract over AI safety disagreements, after which OpenAI stepped in — Amodei publicly disputed OpenAI's characterization of the handoff, escalating a public dispute between the two frontier AI labs over military AI deployment ethics.

**[New RFP Template for AI Usage Control and AI Governance](https://thehackernews.com/2026/03/new-rfp-template-for-ai-usage-control.html)**
*The Hacker News*

As enterprise AI adoption accelerates, security leaders now have budget for AI governance but lack standardized requirements; this piece outlines an RFP framework to help CISOs define what "AI governance" actually means in procurement terms.
