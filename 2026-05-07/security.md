# Security Digest — 2026-05-07

A heavy day on the offensive side: Palo Alto's PAN-OS is under active zero-day exploitation, vm2 sandboxes can be escaped, and a new Rowhammer line of work shows full host compromise via NVIDIA GPU bit-flips. On the research side, papers continue to push at the seams of LLM agent security — from MoE-aware attacks to fine-tuning-induced collapse of guard-model safety geometry.

---

## AI Security Research

[Rowhammer Attack Against NVIDIA Chips](https://www.schneier.com/blog/archives/2026/05/rowhammer-attack-against-nvidia-chips.html) — *Schneier on Security* — Two independent teams demonstrate GDDR Rowhammer bit-flips on Ampere-generation NVIDIA cards that escalate from GPU memory corruption to full host-CPU memory control and system compromise, provided IOMMU is disabled (the default).

[GPUBreach: Privilege Escalation Attacks on GPUs using Rowhammer](https://arxiv.org/abs/2605.03812) — *ArXiv cs.CR* — The technical paper behind the headlines: GPU Rowhammer is shown to be as potent as the CPU variant, moving beyond untargeted weight corruption to targeted bit-flips usable for privilege escalation.

[When Safety Geometry Collapses: Fine-Tuning Vulnerabilities in Agentic Guard Models](https://arxiv.org/abs/2605.02914) — *ArXiv cs.LG* — LlamaGuard, WildGuard, and Granite Guardian can lose all safety alignment after fine-tuning on entirely benign data — no adversary required — because domain specialization destroys the latent harmful/benign geometry the guard relies on.

[RouteHijack: Routing-Aware Attack on Mixture-of-Experts LLMs](https://arxiv.org/abs/2605.02946) — *ArXiv cs.LG* — A new attack class targets MoE LLMs by manipulating expert routing rather than token-level prompts, exposing a safety axis that prior jailbreak and intervention attacks miss.

[EvoJail: Evolutionary Diverse Jailbreak Prompt Generation for Large Language Models](https://arxiv.org/abs/2605.02921) — *ArXiv cs.LG* — An evolutionary search method that adapts to newer safety-tuned models and produces diverse jailbreak prompts, addressing two gaps (adaptability, diversity) that limited prior automated jailbreak generators.

[ARGUS: Defending LLM Agents Against Context-Aware Prompt Injection](https://arxiv.org/abs/2605.03378) — *ArXiv cs.CR* — Prior prompt-injection benchmarks assume the agent runs against a fully specified user goal; ARGUS introduces context-aware evaluation and a defense that holds up where attackers exploit ambiguity in the user's actual intent.

[MAGE: Safeguarding LLM Agents against Long-Horizon Threats via Shadow Memory](https://arxiv.org/abs/2605.03228) — *ArXiv cs.CR* — Defends LLM agents against attacks that exploit extended multi-turn interactions to drift toward malicious objectives, by enforcing guardrails through a shadow-memory layer rather than per-turn filtering.

[Towards Understanding Specification Gaming in Reasoning Models](https://arxiv.org/abs/2605.02269) — *ArXiv cs.AI* — Across an open-sourced suite of eight tasks (five non-coding), every tested reasoning model exploits its specification at non-trivial rates, providing the first systematic baseline for when and why specification gaming arises.

[Do Multimodal RAG Systems Leak Data? A Comprehensive Evaluation of Membership Inference and Image Caption Retrieval Attacks](https://arxiv.org/abs/2601.17644) — *ArXiv cs.CR* — An empirical privacy audit of multimodal RAG pipelines shows that connecting private image datasets to retrieval can leak membership and reconstruct caption-level content under realistic attacker access.

## Vulnerabilities & Exploits

[Palo Alto PAN-OS Flaw Under Active Exploitation Enables Remote Code Execution](https://thehackernews.com/2026/05/palo-alto-pan-os-flaw-under-active.html) — *The Hacker News* — CVE-2026-0300, an unauthenticated buffer-overflow RCE in PAN-OS (CVSS 9.3 when the User-ID Authentication Portal is internet-exposed), is being exploited in the wild per Palo Alto's advisory.

[Palo Alto Networks warns of firewall RCE zero-day exploited in attacks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-warns-of-actively-exploited-firewall-zero-day/) — *BleepingComputer* — Companion coverage of the same PAN-OS User-ID Authentication Portal zero-day, emphasizing that no patch was available at disclosure and active exploitation is already underway.

[Critical vm2 sandbox bug lets attackers execute code on hosts](https://www.bleepingcomputer.com/news/security/critical-vm2-sandbox-bug-lets-attackers-execute-code-on-hosts/) — *BleepingComputer* — A new escape in the widely depended-upon Node.js sandboxing library vm2 lets attacker-controlled code break out and run arbitrary code on the host — relevant to anyone running untrusted JS via vm2 (including LLM tool runners).

[DAEMON Tools devs confirm breach, release malware-free version](https://www.bleepingcomputer.com/news/security/daemon-tools-devs-confirm-breach-release-malware-free-version/) — *BleepingComputer* — Disc Soft confirms a supply-chain compromise that trojanized DAEMON Tools Lite installers and has shipped a clean rebuild; users who installed during the affected window should rotate and reinstall.

[Yet Another Way to Bypass Google Chrome's Encryption Protection](https://www.darkreading.com/endpoint-security/yet-another-way-bypass-google-chromes-encryption-protection) — *Dark Reading* — The VoidStealer Trojan's authors found a fresh route around Chrome's App-Bound Encryption, undoing a control that was supposed to make infostealer credential theft materially harder.

[Attacks Abuse Windows Phone Link to Steal Texts & Bypass 2FA](https://www.darkreading.com/cyberattacks-data-breaches/attacks-abuse-windows-phone-link-texts-bypass-2fa) — *Dark Reading* — Operators are dropping the CloudZ RAT plus a new "Pheno" plug-in to ride the trusted PC-to-phone bridge, harvesting SMS-delivered codes and defeating 2FA without obvious endpoint signals.

[Instructure Breach Exposes Schools' Vendor Dependence](https://www.darkreading.com/cyberattacks-data-breaches/instructure-breach-exposes-schools-vendor-dependence) — *Dark Reading* — ShinyHunters' breach of Canvas-maker Instructure raises hard questions about how concentrated educational SaaS dependence has become, and what schools can actually inspect or require from a single dominant LMS vendor.

[MuddyWater hackers use Chaos ransomware as a decoy in attacks](https://www.bleepingcomputer.com/news/security/muddywater-hackers-use-chaos-ransomware-as-a-decoy-in-attacks/) — *BleepingComputer* — Iran-linked MuddyWater is using Microsoft Teams social engineering to gain initial access, then deploying Chaos ransomware purely as misdirection to disguise espionage tradecraft as a financially motivated incident.

[Hackers abuse Google ads for GoDaddy ManageWP login phishing](https://www.bleepingcomputer.com/news/security/hackers-abuse-google-ads-for-godaddy-managewp-login-phishing/) — *BleepingComputer* — Sponsored Google search results are being used to phish credentials for ManageWP, the GoDaddy console used to administer fleets of WordPress sites — a high-leverage target for downstream site compromise.

[New Cisco DoS flaw requires manual reboot to revive devices](https://www.bleepingcomputer.com/news/security/new-cisco-dos-flaw-requires-manual-reboot-to-revive-devices/) — *BleepingComputer* — Cisco patched a Crosswork Network Controller and Network Services Orchestrator DoS bug whose exploited state can only be cleared by a manual reboot — a notable operational hazard for orchestration-tier infrastructure.

## Policy & Compliance

[Google's Android Apps Get Public Verification to Stop Supply Chain Attacks](https://thehackernews.com/2026/05/android-apps-get-public-verification.html) — *The Hacker News* — Google is extending Binary Transparency from Pixel firmware to Android apps via a public ledger, so independent parties can verify that the binaries on a device match what Google intended to publish — an industry standard-setting move against supply-chain tampering.
