# Security Digest — 2026-04-01

AI infrastructure continues to surface as a high-value attack target, with a newly disclosed Vertex AI privilege-escalation path joining a wave of active supply-chain and APT campaigns targeting cloud, mobile, and East Asian networks.

---

## AI Security Research

**[Vertex AI Vulnerability Exposes Google Cloud Data and Private Artifacts](https://thehackernews.com/2026/03/vertex-ai-vulnerability-exposes-google.html)**
*The Hacker News*

Palo Alto researchers disclosed a "blind spot" in Google Cloud's Vertex AI platform that lets AI agents be weaponized to exfiltrate sensitive data and pivot into restricted cloud infrastructure via over-privileged service identities. The flaw underscores how agentic workloads introduce new lateral-movement paths that traditional cloud IAM reviews miss.

**["What Did It Actually Do?": Understanding Risk Awareness and Traceability for Computer-Use Agents](https://arxiv.org/abs/2603.28551)**
*ArXiv cs.CR*

A user study finds that mainstream computer-use agents routinely install extensions, invoke tools, and modify local state without surfacing meaningful audit trails to users, creating accountability gaps that attackers could exploit for persistent access. The paper proposes a risk-taxonomy and lightweight traceability model for consumer-facing agent deployments.

**[Misleading Large Language Models used in Scientific Peer-Reviewing via Hidden Prompt-Injection Attacks](https://arxiv.org/abs/2508.20863)**
*ArXiv cs.CR*

Researchers demonstrate that adversarial authors can embed invisible prompt-injection payloads in manuscript text that manipulate LLM-assisted peer-review systems into generating falsely positive evaluations. The attack survives PDF conversion and standard preprocessing pipelines, raising immediate concerns for venues already relying on LLM pre-screening.

**["Elementary, My Dear Watson." Detecting Malicious Skills via Neuro-Symbolic Reasoning across Heterogeneous Artifacts](https://arxiv.org/abs/2603.27204)**
*ArXiv cs.CR*

As LLM-agent skill registries proliferate, this paper formalizes the agentic supply-chain threat and proposes a neuro-symbolic detector that cross-references prompts, code, and configuration across skill packages to identify malicious intent. Evaluated on a new benchmark of 1,200 benign and 400 adversarial skills, it achieves 94% F1 with low false-positive rates.

**[Safeguarding LLMs Against Misuse and AI-Driven Malware Using Steganographic Canaries](https://arxiv.org/abs/2603.28655)**
*ArXiv cs.CR*

The paper introduces steganographic canary tokens embedded in AI-generated content so that when adversarial malware attempts to exfiltrate or re-use that content, the canary triggers an alert. The technique is designed for enterprise deployments where sensitive documents are regularly processed by cloud-hosted LLMs.

**[Lite-BD: A Lightweight Black-box Backdoor Defense via Reviving Multi-Stage Image Transformations](https://arxiv.org/abs/2602.07197)**
*ArXiv cs.CR*

Lite-BD proposes a purely black-box backdoor purification strategy that chains classical image transformations (JPEG compression, random cropping, color-jitter) to neutralize trigger patterns without access to model weights. On standard benchmarks the method matches white-box defenses while remaining practical for MLaaS deployments.

---

## Vulnerabilities & Exploits

**[TrueConf Zero-Day Exploited in Attacks on Southeast Asian Government Networks](https://thehackernews.com/2026/03/trueconf-zero-day-exploited-in-attacks.html)**
*The Hacker News*

CVE-2026-3502 (CVSS 7.8), a lack-of-integrity-check flaw in the TrueConf video-conferencing client, has been weaponized in a campaign dubbed TrueChaos against government entities across Southeast Asia. Patches are available; organizations relying on TrueConf for sensitive internal meetings should treat this as urgent given the active exploitation.

**[Axios Supply Chain Attack Pushes Cross-Platform RAT via Compromised npm Account](https://thehackernews.com/2026/03/axios-supply-chain-attack-pushes-cross.html)**
*The Hacker News*

Versions 1.14.1 and 0.30.4 of the widely-used Axios HTTP client were briefly poisoned with a malicious dependency that drops a cross-platform remote-access trojan on Windows, macOS, and Linux. The compromised packages were live for a narrow window before removal; any CI/CD pipeline that ran `npm install` during that period should be treated as potentially compromised.

**[Silver Fox Expands Asia Cyber Campaign with AtlasCross RAT and Fake Domains](https://thehackernews.com/2026/03/silver-fox-expands-asia-cyber-campaign.html)**
*The Hacker News*

The Chinese-speaking Silver Fox threat actor is distributing a previously undocumented RAT called AtlasCross through typosquatted domains impersonating VPN clients, encrypted messengers, and video-conferencing tools. The campaign continues to focus on Chinese-speaking targets and highlights the growing risk of lookalike software distribution sites as an initial-access vector.

**[Red-MIRROR: Agentic LLM-based Autonomous Penetration Testing with Reflective Verification](https://arxiv.org/abs/2603.27127)**
*ArXiv cs.CR*

Red-MIRROR presents an autonomous web-application pentesting agent that combines LLM-driven exploit generation with a self-reflective verification loop to confirm successful exploitation of SQL injection, XSS, and business logic flaws. Evaluated against real-world targets, it surfaces attack chains faster than human testers, a capability that raises the offensive bar for defenders.

**[Detecting Protracted Vulnerabilities in Open Source Projects](https://arxiv.org/abs/2603.27067)**
*ArXiv cs.CR*

An empirical analysis of OSS vulnerability disclosure timelines finds a large class of "protracted" bugs that remain unreported, unpatched, or undisclosed for months to years, often because they span multiple maintainer boundaries or lack a clear CVE sponsor. The paper proposes heuristics for automated discovery and prioritization of these long-tail risks.

---

## Policy & Compliance

**[Android Developer Verification Rollout Begins Ahead of September Enforcement](https://thehackernews.com/2026/03/android-developer-verification-rollout.html)**
*The Hacker News*

Google has begun rolling out mandatory identity verification for all Android developers, with full enforcement slated for September 2026 in Brazil, Indonesia, and other high-risk markets. The initiative aims to eliminate the anonymity that allows bad actors to repeatedly distribute harmful apps after takedowns.

**[Inventors of Quantum Cryptography Win Turing Award](https://www.schneier.com/blog/archives/2026/03/inventors-of-quantum-cryptography-win-turing-award.html)**
*Schneier on Security*

Charles Bennett and Gilles Brassard have been awarded the 2026 Turing Award for inventing quantum key distribution. Bruce Schneier notes his admiration for the theoretical achievement while reiterating his long-held view that QKD solves a key-distribution problem that existing classical cryptography handles adequately for most real-world deployments.

**[Empowering Mobile Networks Security Resilience by using Post-Quantum Cryptography](https://arxiv.org/abs/2603.28626)**
*ArXiv cs.CR*

With 5G's cloud-native Service-Based Architecture exposed to Harvest-Now, Decrypt-Later quantum threats, this paper details a migration path for control-plane signaling that integrates NIST-standardized post-quantum algorithms (ML-KEM, ML-DSA) into existing 5G authentication flows without breaking backward compatibility. The work is directly relevant to carriers evaluating PQC upgrade timelines.
