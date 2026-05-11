# Security Digest — 2026-05-12

The week opens with Google publicly naming the first zero-day exploit it attributes to AI-assisted development, fresh supply-chain compromises in the DevOps tool chain, and a wave of arXiv preprints probing jailbreaks, prompt injection, and agentic-workflow risks.

---

## AI Security Research

[Language Models Can Autonomously Hack and Self-Replicate](https://arxiv.org/abs/2605.06760)
*ArXiv cs.CR* — Researchers demonstrate an LLM agent that propagates its weights across a network by exploiting vulnerable hosts, raising the bar for what "autonomous worm" means in a post-agent world.

[Cross-Modal Backdoors in Multimodal Large Language Models](https://arxiv.org/abs/2605.07490)
*ArXiv cs.CR* — Assembling MLLMs from pretrained components opens supply-chain attack surfaces; the paper shows triggers planted in one modality can fire malicious behavior in another.

[Demystifying and Detecting Agentic Workflow Injection Vulnerabilities in GitHub Actions](https://arxiv.org/abs/2605.07135)
*ArXiv cs.CR* — As LLM agents are wired into repo automation (issue triage, PR review, code edits), the authors characterize a new class of injection bugs unique to agentic GitHub Actions workflows.

[Membership Inference Attacks on Vision-Language-Action Models](https://arxiv.org/abs/2605.07088)
*ArXiv cs.CR* — Extends membership-inference threat analysis from LLMs and VLMs to VLA models, with implications for robotic-policy training data privacy.

[Hard to Read, Easy to Jailbreak: How Visual Degradation Bypasses MLLM Safety Alignment](https://arxiv.org/abs/2605.07250)
*ArXiv cs.AI* — Image perturbations that look like noise to humans reliably slip past multimodal safety filters, illustrating how alignment trained on clean inputs fails under distribution shift.

[OrchJail: Jailbreaking Tool-Calling Text-to-Image Agents by Orchestration-Guided Fuzzing](https://arxiv.org/abs/2605.07414)
*ArXiv cs.AI* — A fuzzing harness targets the orchestration layer between LLM tool-callers and image generators, finding jailbreaks that single-prompt attacks miss.

[Searching for Privacy Risks in LLM Agents via Simulation](https://arxiv.org/abs/2508.10880)
*ArXiv cs.AI* — Simulation-based red teaming surfaces leakage paths in agent stacks where private context flows between tools, memory, and outputs.

[MIPIAD: Multilingual Indirect Prompt Injection Attack Defense with Qwen — TF-IDF Hybrid and Meta-Ensemble Learning](https://arxiv.org/abs/2605.07269)
*ArXiv cs.LG* — Proposes a defense that combines classical TF-IDF features with a Qwen backbone to catch indirect prompt injections across languages, an under-studied evasion vector.

[Asymmetric Phase Coding Audio Watermarking](https://arxiv.org/abs/2605.07241)
*ArXiv cs.CR* — Active watermarking scheme aimed at deepfake-resistant voice authentication, intended as a complement to passive detectors that degrade as generative models evolve.

[LLMs and Text-in-Text Steganography](https://www.schneier.com/blog/archives/2026/05/llms-and-text-in-text-steganography.html)
*Schneier on Security* — Short note flagging recent results showing LLMs are unusually effective at hiding messages inside ordinary-looking text, with obvious implications for covert channels.

## Vulnerabilities & Exploits

[Google stopped a zero-day hack that it says was developed with AI](https://www.theverge.com/tech/928007/google-ai-zero-day-exploit-stopped)
*The Verge AI* — Google Threat Intelligence Group says it caught "prominent cyber crime threat actors" using a zero-day that GTIG assesses was likely generated with an AI system — the first publicly named case of AI-built mass-exploitation tooling.

[Hackers Used AI to Develop First Known Zero-Day 2FA Bypass for Mass Exploitation](https://thehackernews.com/2026/05/hackers-used-ai-to-develop-first-known.html)
*The Hacker News* — Companion reporting identifies the bug as a 2FA-bypass in a popular open-source web admin tool, with GTIG releasing indicators and prompts recovered from the actor's tooling.

[TeamPCP Compromises Checkmarx Jenkins AST Plugin Weeks After KICS Supply Chain Attack](https://thehackernews.com/2026/05/teampcp-compromises-checkmarx-jenkins.html)
*The Hacker News* — A trojanized Jenkins AST plugin was pushed to the Jenkins Marketplace; Checkmarx is directing users to patched build 2.0.13-829.vc72453fa_1c16, the second supply-chain hit on the vendor in weeks.

[cPanel CVE-2026-41940 Under Active Exploitation to Deploy Filemanager Backdoor](https://thehackernews.com/2026/05/cpanel-cve-2026-41940-under-active.html)
*The Hacker News* — Threat actor "Mr_Rot13" is chaining a recently disclosed critical cPanel flaw to drop a persistent "Filemanager" backdoor; admins should treat the patch as urgent.

['Dirty Frag' Exploit Poised to Blow Up on Enterprise Linux Distros](https://www.darkreading.com/vulnerabilities-threats/dirty-frag-exploit-blow-up-enterprise-linux-distros)
*Dark Reading* — A Linux privilege-escalation flaw in the Dirty Pipe / Copy Fail lineage is reportedly under limited exploitation, with enterprise distros squarely in scope.

[Ollama Out-of-Bounds Read Vulnerability Allows Remote Process Memory Leak](https://thehackernews.com/2026/05/ollama-out-of-bounds-read-vulnerability.html)
*The Hacker News* — A critical OOB-read in Ollama can let a remote, unauthenticated attacker exfiltrate the full process memory of self-hosted model servers — a fast-growing footprint inside enterprises.

[Fake OpenAI Privacy Filter Repo Hits #1 on Hugging Face, Draws 244K Downloads](https://thehackernews.com/2026/05/fake-openai-privacy-filter-repo-hits-1.html)
*The Hacker News* — A malicious "Open-OSS/Privacy-Filter" repo impersonated an OpenAI open-weight release and shipped a Rust-based Windows infostealer, reaching the platform's trending list before takedown.

[Instructure confirms hackers used Canvas flaw to deface portals](https://www.bleepingcomputer.com/news/security/instructure-confirms-hackers-used-canvas-flaw-to-deface-portals/)
*BleepingComputer* — Instructure confirms attackers exploited a Canvas LMS vulnerability to alter login portals and post extortion messages across customer institutions.

[Hackers abuse Google ads, Claude.ai chats to push Mac malware](https://www.bleepingcomputer.com/news/security/hackers-abuse-google-ads-claudeai-chats-to-push-mac-malware/)
*BleepingComputer* — A malvertising campaign for "Claude mac download" uses sponsored Google results and weaponized Claude.ai shared chats to funnel macOS users to a stealer.

[TrickMo Android banker adopts TON blockchain for covert comms](https://www.bleepingcomputer.com/news/security/trickmo-android-banker-adopts-ton-blockchain-for-covert-comms/)
*BleepingComputer* — A new TrickMo variant routes command-and-control through The Open Network, joining a small but growing set of malware families abusing public blockchains for resilience.

[Cyber Espionage Group Targets Aviation Firms to Steal Map Data](https://www.darkreading.com/vulnerabilities-threats/cyber-espionage-group-aviation-firms-steal-map-data)
*Dark Reading* — A long-running intrusion set is quietly compromising aerospace and drone operators to exfiltrate GIS files, terrain models, and GPS data — espionage tradecraft aimed at adversary situational awareness.

## Policy & Compliance

[FCC Softens Ban on Foreign-Made Routers](https://www.darkreading.com/endpoint-security/fcc-softens-foreign-router-ban)
*Dark Reading* — The FCC has eased some restrictions and extended deadlines for foreign router manufacturers, but the underlying ban remains in force.

[Police shut down reboot of Crimenetwork marketplace, arrest admin](https://www.bleepingcomputer.com/news/security/police-shut-down-reboot-of-crimenetwork-marketplace-arrest-admin/)
*BleepingComputer* — German authorities dismantled a relaunched "Crimenetwork" cybercrime market that had moved more than €3.6M in goods, and arrested the operator.

[An Automated Framework for Cybersecurity Policy Compliance Assessment Against Security Control Standards](https://arxiv.org/abs/2605.07515)
*ArXiv cs.CR* — Proposes an automated pipeline for checking organizational security policies against standard control catalogs, targeting the manual bottleneck in compliance audits.
