# Security Digest — 2026-03-20

Today's security landscape is dominated by expanding AI attack surfaces — multimodal jailbreaks, prompt injection defenses, and LLM-assisted vulnerability analysis — alongside real-world enforcement actions targeting large-scale IoT botnets exploiting millions of devices.

---

## AI Security Research

**[On Optimizing Multimodal Jailbreaks for Spoken Language Models](https://arxiv.org/abs/2603.19127)**
*arXiv cs.CR*
Spoken Language Models (SLMs) inherit LLM safety vulnerabilities and an expanded attack surface across speech and text modalities; this paper shows that existing unimodal jailbreaks fall short and optimizes cross-modal adversarial prompts that more effectively elicit harmful outputs from SLMs.

**[Systematic Scaling Analysis of Jailbreak Attacks in Large Language Models](https://arxiv.org/abs/2603.11149)**
*arXiv cs.CR*
Introduces a scaling-law framework for jailbreak attacks, treating each attack as a compute-bounded optimization procedure and measuring success rates across model families and harm categories — revealing systematic patterns in how attacker effort translates to jailbreak success.

**[AJAR: Adaptive Jailbreak Architecture for Red-teaming](https://arxiv.org/abs/2601.10971)**
*arXiv cs.CR*
Addresses the gap between adaptive multi-turn jailbreak algorithms and agentic runtimes by packaging attacks as composable, stateful agents, enabling more realistic red-teaming of LLMs with persistent state and tool access.

**[Prompt Control-Flow Integrity: A Priority-Aware Runtime Defense Against Prompt Injection in LLM Systems](https://arxiv.org/abs/2603.18433)**
*arXiv cs.CR*
Proposes treating prompts as structured control-flow rather than flat strings, using priority-aware runtime enforcement to prevent injected instructions from overriding system policies in RAG and API-backed LLM deployments.

**[Measuring and Exploiting Confirmation Bias in LLM-Assisted Security Code Review](https://arxiv.org/abs/2603.18740)**
*arXiv cs.CR*
Finds that LLM-based vulnerability detectors exhibit confirmation bias — favoring interpretations aligned with prior context — which can be exploited to suppress detection of real vulnerabilities in CI/CD security pipelines.

**[Who Tests the Testers? Systematic Enumeration and Coverage Audit of LLM Agent Tool Call Safety](https://arxiv.org/abs/2603.18245)**
*arXiv cs.CR*
Audits existing LLM agent safety benchmarks and finds significant gaps in coverage of unsafe tool-call workflows, identifying categories of risky agent actions that current test suites systematically miss.

**[Retrieval-Augmented LLMs for Security Incident Analysis](https://arxiv.org/abs/2603.18196)**
*arXiv cs.CR*
Presents a RAG-based system that helps analysts correlate evidence across IDS alerts, network traffic, and authentication logs during cybersecurity incident investigations, reducing manual triage workload.

**[CNT: Safety-oriented Function Reuse across LLMs via Cross-Model Neuron Transfer](https://arxiv.org/abs/2603.18449)**
*arXiv cs.CR*
Proposes transferring safety-relevant neuron groups from safer open-source models to less-aligned ones as a post-hoc adaptation strategy, avoiding full retraining while propagating desired safety behaviors.

**[MAED: Mathematical Activation Error Detection for Mitigating Physical Fault Attacks in DNN Inference](https://arxiv.org/abs/2603.18120)**
*arXiv cs.CR*
Introduces a lightweight mathematical detection scheme for fault-injection attacks on embedded DNN inference, catching activation anomalies without requiring hardware modification or costly redundancy.

**[A Model Consistency-Based Countermeasure to GAN-Based Data Poisoning Attack in Federated Learning](https://arxiv.org/abs/2405.11440)**
*arXiv cs.CR*
Defends federated learning against GAN-generated poisoning attacks by monitoring model consistency across rounds, detecting stealthy client-side data manipulation that degrades global model performance.

---

## Vulnerabilities & Exploits

**[Apple Warns Older iPhones Vulnerable to Coruna, DarkSword Exploit Kit Attacks](https://thehackernews.com/2026/03/apple-warns-older-iphones-vulnerable-to.html)**
*The Hacker News*
Apple is urging users on outdated iOS versions to update immediately, as the Coruna and DarkSword exploit kits are actively using malicious web content to trigger infection chains that steal sensitive data from unpatched devices.

**[Feds Disrupt IoT Botnets Behind Huge DDoS Attacks](https://krebsonsecurity.com/2026/03/feds-disrupt-iot-botnets-behind-huge-ddos-attacks/)**
*Krebs on Security*
U.S. DOJ, Canada, and Germany jointly dismantled infrastructure behind four botnets — Aisuru, Kimwolf, JackSkid, and Mossad — that compromised over three million routers and web cameras and were responsible for a series of record-breaking DDoS attacks.

**[Weaver: Fuzzing JavaScript Engines at the JavaScript-WebAssembly Boundary](https://arxiv.org/abs/2603.18789)**
*arXiv cs.CR*
Targets the novel attack surface created by WebAssembly integration into JS engines, using boundary-aware fuzzing to discover type-confusion and memory-safety bugs at the JS-Wasm interaction layer that conventional fuzzers miss.

**[Cross-Ecosystem Vulnerability Analysis for Python Applications](https://arxiv.org/abs/2603.18693)**
*arXiv cs.CR*
Addresses the challenge of tracking vulnerabilities in native libraries vendored inside Python packages across both PyPI and OS package ecosystems, presenting a cross-ecosystem analysis pipeline to close supply chain blind spots.

**[Quantifying Memory Cells Vulnerability for DRAM Security](https://arxiv.org/abs/2603.18549)**
*arXiv cs.CR*
Characterizes DRAM cell susceptibility to rowhammer, rowpress, and retention-failure attacks with a quantitative model, enabling more precise threat assessment for memory integrity and confidentiality in modern systems.

**[Pushan: Trace-Free Deobfuscation of Virtualization-Obfuscated Binaries](https://arxiv.org/abs/2603.18355)**
*arXiv cs.CR*
Introduces a static deobfuscation approach for VM-protected malware that works without dynamic execution traces, enabling security analysts to recover readable code from binaries protected by virtualization-based obfuscation.

**[Cyber-Resilient Digital Twins: Discriminating Attacks for Safe Critical Infrastructure Control](https://arxiv.org/abs/2603.18613)**
*arXiv cs.CR*
Proposes i-SDT, a digital twin framework for Industrial Cyber-Physical Systems that not only detects anomalies but distinguishes attack types — enabling targeted response rather than costly full-system shutdowns.

**[Implicit Patterns in LLM-Based Binary Analysis](https://arxiv.org/abs/2603.19138)**
*arXiv cs.CR*
Analyzes how LLM agents organize multi-pass binary vulnerability analysis over hundreds of reasoning steps, revealing implicit token-level exploration patterns that affect coverage and analysis quality in automated security tools.

---

## Policy & Compliance

**[On The Effectiveness of the UK NIS Regulations as a Mandatory Cybersecurity Reporting Regime](https://arxiv.org/abs/2603.19084)**
*arXiv cs.CR*
Analyzes UK-wide 2024 incident data reported under the Network and Information Systems Regulations — which mandate disclosure of significant disruptions to essential services — providing rare empirical evidence on cyberattack prevalence and impact on Critical National Infrastructure.
