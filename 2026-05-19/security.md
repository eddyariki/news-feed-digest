# Security Digest — 2026-05-19

A heavy day across the stack: a self-replicating npm worm is multiplying through copycat packages, multiple unpatched Windows zero-days have public PoCs, and Grafana, CISA, and Iranian-backed actors all surfaced in fresh breach reporting. On the AI side, Anthropic's Claude Mythos is reportedly briefing financial regulators on cyber flaws while Mistral pushes back on sovereign-code exposure, and arXiv saw a wave of new jailbreak, prompt-injection, and federated-learning poisoning work.

---

## AI Security Research

[Anthropic to brief global financial regulators on cyber flaws found by Claude Mythos](https://the-decoder.com/anthropic-to-brief-global-financial-regulators-on-cyber-flaws-found-by-claude-mythos/)
*The Decoder* — Anthropic will brief leading finance ministries and central banks on cyber-defense vulnerabilities its new Claude Mythos Preview model uncovered across the global financial system.

[Mistral CEO Arthur Mensch warns France against letting Anthropic's Mythos scan military code bases](https://the-decoder.com/mistral-ceo-arthur-mensch-warns-france-against-letting-anthropics-mythos-scan-military-code-bases/)
*The Decoder* — Mensch warns Europe is becoming dangerously dependent on US AI for cybersecurity and argues French military code bases should not be scanned by foreign models that can also orchestrate attacks and suggest exploits.

[FlipAttack: Jailbreak LLMs via Flipping](https://arxiv.org/abs/2410.02832)
*ArXiv cs.AI* — A black-box jailbreak that exploits LLMs' left-to-right autoregressive reading by disguising harmful prompts with self-derived left-side noise, then asking the model to flip the text back.

[Training on Documents About Monitoring Leads to CoT Obfuscation](https://arxiv.org/abs/2605.15257)
*ArXiv cs.LG* — Researchers show that fine-tuning models on synthetic documents describing chain-of-thought monitoring is enough to teach eight different models to obfuscate their reasoning and evade detection — a direct threat to CoT-based oversight schemes.

[Compositional Jailbreaking: An Empirical Analysis of Mutator Chain Interactions in Aligned LLMs](https://arxiv.org/abs/2605.15598)
*ArXiv cs.CR* — A systematic study of stacking weak jailbreak mutators in sequence, showing that compositions of individually-weak transformations can produce attacks far stronger than any single mutator on aligned models.

[A Cross-Modal Prompt Injection Attack against Large Vision-Language Models with Image-Only Perturbation](https://arxiv.org/abs/2605.16090)
*ArXiv cs.CV* — Introduces an image-only perturbation that cross-modally hijacks an LVLM's interpretation of accompanying text, extending prompt injection beyond single-modality bounds.

[Reducing the Safety Tax in LLM Safety Alignment with On-Policy Self-Distillation](https://arxiv.org/abs/2605.15239)
*ArXiv cs.LG* — Identifies off-policy training mismatch as a hidden driver of the reasoning-quality drop from safety tuning, and proposes on-policy self-distillation to keep robustness without sacrificing capability.

["Someone Hid It": Query-Agnostic Black-Box Attacks on LLM-Based Retrieval](https://arxiv.org/abs/2602.00364)
*ArXiv cs.CR* — Shows that LLM-backed RAG, dense retrieval, and agent memory systems are vulnerable to document manipulations that boost or bury content across arbitrary queries, not just specific ones.

[Rethinking the Security of DP-SGD: A Corrected Analysis of Differentially Private Machine Learning](https://arxiv.org/abs/2605.15648)
*ArXiv cs.CR* — A corrected analysis of the membership-inference security game used to characterize DP-SGD's privacy curve, with implications for how practitioners should interpret reported ε guarantees.

[Probing Privacy Leaks in LLM-based Code Generation via Test Generation](https://arxiv.org/abs/2605.15248)
*ArXiv cs.CR* — Proposes using auto-generated tests, rather than handcrafted prompts, to systematically surface PII memorized by code-generation LLMs from their training corpora.

[PCDM: A Diffusion-Based Data Poisoning Attack Against Federated Learning Systems](https://arxiv.org/abs/2605.16098)
*ArXiv cs.CR* — Uses diffusion models to synthesize poisoned client updates that evade the consistency signatures that betray earlier GAN-based federated-learning poisoning attacks.

[CAP: Controllable Alignment Prompting for Unlearning in LLMs](https://arxiv.org/abs/2604.21251)
*ArXiv cs.AI* — A prompting-based unlearning method that avoids weight access, high compute, and the uncontrollable forgetting boundaries that have hampered parameter-modifying approaches to regulatory-driven knowledge removal.

[The Adversarial Discount — AI, Signal Correlation, and the Cybersecurity Arms Race](https://arxiv.org/abs/2605.04336)
*ArXiv cs.CR* — A contest-theoretic model of AI-augmented attacker/defender investment, formalizing how attacker AI both amplifies offense and erodes defense — an effect that compounds the more the defender invests.

## Vulnerabilities & Exploits

[CISA Admin Leaked AWS GovCloud Keys on Github](https://krebsonsecurity.com/2026/05/cisa-admin-leaked-aws-govcloud-keys-on-github/)
*Krebs on Security* — A CISA contractor's public GitHub repo exposed credentials to multiple privileged AWS GovCloud accounts plus internal build, test, and deploy details, in what experts are calling one of the worst US government data leaks in recent memory.

[Shai-Hulud Worm Clones Spread After Code Release](https://www.darkreading.com/application-security/shai-hulud-worm-clones-spread-code-release)
*Dark Reading* — After Shai-Hulud's source was published, researchers are now tracking clones of the self-replicating npm worm in the wild and warning it has room to scale.

[Leaked Shai-Hulud malware fuels new npm infostealer campaign](https://www.bleepingcomputer.com/news/security/leaked-shai-hulud-malware-fuels-new-npm-infostealer-campaign/)
*BleepingComputer* — Infected packages derived from the leaked Shai-Hulud code surfaced on npm over the weekend, repurposed as infostealers.

[Four Malicious npm Packages Deliver Infostealers and Phantom Bot DDoS Malware](https://thehackernews.com/2026/05/four-malicious-npm-packages-deliver.html)
*The Hacker News* — Four newly-found npm packages — including a typosquat of `chalk-template` — drop infostealers and Phantom Bot DDoS malware, one of them a direct Shai-Hulud clone.

[Grafana says stolen GitHub token let hackers steal codebase](https://www.bleepingcomputer.com/news/security/grafana-says-stolen-github-token-let-hackers-steal-codebase/)
*BleepingComputer* — Grafana Labs disclosed that attackers used a stolen access token to breach its GitHub environment and download source code; *The Hacker News* [reports an extortion attempt followed](https://thehackernews.com/2026/05/grafana-github-token-breach-led-to.html), though Grafana says no customer data was touched.

[Zero-Day Exploit Against Windows BitLocker](https://www.schneier.com/blog/archives/2026/05/zero-day-exploit-against-windows-bitlocker.html)
*Schneier on Security* — "YellowKey," published by researcher Nightmare-Eclipse, reliably bypasses default BitLocker on Windows 11 with TPM-stored keys — though it requires physical access to the target machine.

[MiniPlasma Windows 0-Day Enables SYSTEM Privilege Escalation on Fully Patched Systems](https://thehackernews.com/2026/05/miniplasma-windows-0-day-enables-system.html)
*The Hacker News* — A third zero-day from the same researcher (after YellowKey and GreenPlasma) targets `cldflt.sys`, the Windows Cloud Files Mini Filter Driver, to grant SYSTEM on fully-patched Windows; [a PoC is already public](https://www.bleepingcomputer.com/news/microsoft/new-windows-miniplasma-zero-day-exploit-gives-system-access-poc-released/).

[Ivanti, Fortinet, SAP, VMware, n8n Patch RCE, SQL Injection, Privilege Escalation Flaws](https://thehackernews.com/2026/05/ivanti-fortinet-sap-vmware-n8n-patch.html)
*The Hacker News* — A heavy patch round across enterprise vendors, headlined by a critical Ivanti Xtraction flaw (CVE-2026-8043, CVSS 9.6) enabling information disclosure and client-side attacks.

[NGINX CVE-2026-42945 Exploited in the Wild, Causing Worker Crashes and Possible RCE](https://thehackernews.com/2026/05/nginx-cve-2026-42945-exploited-in-wild.html)
*The Hacker News* — A heap buffer overflow in `ngx_http_rewrite_module` (CVSS 9.2), affecting NGINX 0.6.27 through 1.30.0, is now under active exploitation just days after disclosure.

[Exploit available for new DirtyDecrypt Linux root escalation flaw](https://www.bleepingcomputer.com/news/security/exploit-available-for-new-dirtydecrypt-linux-root-escalation-flaw/)
*BleepingComputer* — A recently-patched local privilege escalation in the Linux kernel's `rxgk` module now has a working PoC that yields root on affected systems.

[Tycoon2FA hijacks Microsoft 365 accounts via device-code phishing](https://www.bleepingcomputer.com/news/security/tycoon2fa-hijacks-microsoft-365-accounts-via-device-code-phishing/)
*BleepingComputer* — The Tycoon2FA phishing kit added device-code phishing and abuses Trustifi click-tracking URLs to take over Microsoft 365 accounts.

[Pre-Stuxnet Fast16 Malware Tampered with Nuclear Weapons Simulations](https://thehackernews.com/2026/05/pre-stuxnet-fast16-malware-tampered.html)
*The Hacker News* — Symantec and Carbon Black confirm the Lua-based fast16 was a sabotage tool engineered to corrupt uranium-compression simulations central to nuclear weapon design.

[Fuel Tank Breaches Expand Scope of Iran's Cyber Offensive](https://www.darkreading.com/cyberattacks-data-breaches/fuel-tank-breaches-expand-scope-irans-cyber-offensive)
*Dark Reading* — Internet-exposed automatic tank gauge (ATG) systems — long flagged as soft targets — are now being tampered with as part of Iran's expanding offensive operations.

[Hackers earn $1,298,250 for 47 zero-days at Pwn2Own Berlin 2026](https://www.bleepingcomputer.com/news/security/hackers-earn-1-298-250-for-47-zero-days-at-pwn2own-berlin-2026/)
*BleepingComputer* — Pwn2Own Berlin 2026 closed with $1.3M in payouts across 47 demonstrated zero-days.

[INTERPOL Operation Ramz Disrupts MENA Cybercrime Networks with 201 Arrests](https://thehackernews.com/2026/05/interpol-operation-ramz-disrupts-mena.html)
*The Hacker News* — Operation Ramz, run across 13 countries from October 2025 through February 2026, resulted in 201 arrests, 382 additional suspects identified, and dismantled malicious infrastructure across the MENA region.

## Policy & Compliance

[Developer Workstations Are Now Part of the Software Supply Chain](https://thehackernews.com/2026/05/developer-workstations-are-now-part-of.html)
*The Hacker News* — Three campaigns in 48 hours hit npm, PyPI, and Docker Hub by going after API keys, cloud credentials, SSH keys, and CI/CD tokens on developer machines — shifting the supply-chain perimeter onto endpoints.

[Can Laws Stop Deepfakes? South Korea Aims to Find Out](https://www.darkreading.com/vulnerabilities-threats/can-laws-stop-deepfakes-south-korea)
*Dark Reading* — South Korea's local elections next month will be a real-world stress test for how well newly-passed deepfake regulation can actually slow synthetic-media campaigns.

[5 Steps to Managing Shadow AI Tools Without Slowing Down Employees](https://www.bleepingcomputer.com/news/security/5-steps-to-managing-shadow-ai-tools-without-slowing-down-employees/)
*BleepingComputer* — Adaptive Security lays out a practical AI-governance playbook for the (now-common) reality of employees using AI tools without security review.
