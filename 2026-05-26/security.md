# Security Digest — 2026-05-26

Today's landscape is dominated by AI security research — jailbreaks that survive test-time training, poisoned agent memory, prompt-injection guardrail bypasses, and adversarial attacks across vision, language, and embodied systems. On the operational side, attackers are actively exploiting a critical Ghost CMS flaw, running a cross-ecosystem supply-chain campaign, and deploying Lazarus malware against financial firms.

---

## AI Security Research

[Test-Time Training Undermines Safety Guardrails](https://arxiv.org/abs/2605.22984) — *ArXiv cs.AI*
Identifies three threat models showing how test-time training, which adapts model parameters during inference, opens new jailbreak vectors that let attackers bypass safety guardrails.

[Same Model, Different Weakness: How Language and Modality Reshape the Jailbreak Attack Surface in Frontier MLLMs](https://arxiv.org/abs/2605.23157) — *ArXiv cs.CL*
First systematic cross-lingual, multimodal red-teaming study finds that jailbreak vulnerability in frontier MLLMs (Claude Sonnet 4.5, GPT-5, Pixtral Large, Qwen Omni) shifts substantially between US English and Mexican Spanish and across modalities.

[Prompt Overflow: What the Guardrail Inspects Is Not What the Model Infers](https://arxiv.org/abs/2605.23196) — *ArXiv cs.CR*
Shows that guardrail "safety checker" models, which truncate or segment overlong prompts, can be bypassed because what the guardrail inspects differs from what the downstream LLM ultimately infers.

[MemAudit: Post-hoc Auditing of Poisoned Agent Memory via Causal Attribution and Structural Anomaly Detection](https://arxiv.org/abs/2605.23723) — *ArXiv cs.AI*
Proposes a post-hoc auditing method using causal attribution and structural anomaly detection to find malicious records that adversaries inject into an LLM agent's persistent memory to later steer its reasoning and actions.

[PoisonForge: Task-Level Targeted Poisoning Benchmark for Instruction-Tuned LLMs](https://arxiv.org/abs/2605.23168) — *ArXiv cs.AI*
Introduces a benchmark for task-level targeted poisoning, where a few crafted instruction-response pairs make a fine-tuned model embed attacker-specified content for a target task while behaving normally elsewhere.

[GradingAttack: Exposing Security Vulnerabilities in LLM Based Educational Grading Agents](https://arxiv.org/abs/2602.00979) — *ArXiv cs.AI*
Demonstrates adversarial manipulation of LLM-based automatic short-answer grading agents deployed "in the wild," exposing security and trustworthiness concerns for educational AI.

[Security, Privacy, and Ethical Risks in OpenClaw](https://arxiv.org/abs/2605.23330) — *ArXiv cs.CR*
Systematically investigates security, privacy, ethical, and traceability risks in OpenClaw, a locally executable AI agent that performs real-world tasks via natural language.

[How Far Will They Go? Red-Teaming Online Influence with Large Language Models](https://arxiv.org/abs/2605.22880) — *ArXiv cs.AI*
Red-teams locally deployed open-source LLMs for their capacity to support political influence and disinformation campaigns, finding them well-suited to privacy-conscious malicious actors.

[Are Frontier LLMs Ready for Cybersecurity? Evidence for Vertical Foundation Models from Dual-Mode Vulnerability Benchmarks](https://arxiv.org/abs/2605.23243) — *ArXiv cs.AI*
Dual-mode benchmark evaluates six frontier models (GPT-5.4, Codex 5.3, Claude Opus 4.6, Sonnet 4.6, Gemini 3.1 Pro and another) on white-box vulnerability detection and black-box web-app security testing, arguing for vertical cybersecurity foundation models.

[Low-Cost Hard-Label Adversarial Attack with Theoretical Foundations](https://arxiv.org/abs/2601.14300) — *ArXiv cs.LG*
Presents a hard-label black-box attack relying only on top-1 predictions, with theoretical guarantees and improved initialization that lower query cost.

[Adversarial Vulnerability Under Temporal Concept Drift: A Longitudinal Study of Android Malware Detection](https://arxiv.org/abs/2605.23623) — *ArXiv cs.AI*
Longitudinal study of Android malware detectors over a decade shows how adversarial robustness degrades under realistic cross-year concept drift and deployment without model updates.

[Phantom Force: Injecting Adversarial Tactile Perceptions into Embodied Intelligence via EMI](https://arxiv.org/abs/2605.13492) — *ArXiv cs.CR*
Demonstrates that Hall-effect tactile fingertip sensors on robots can be spoofed via targeted electromagnetic interference, injecting adversarial touch perceptions into embodied AI.

[CachePrune: Privacy-Aware and Fine-Grained KV Cache Sharing for Efficient LLM Inference](https://arxiv.org/abs/2605.23640) — *ArXiv cs.CR*
Identifies a side channel where cross-user KV cache sharing in LLM serving lets adversaries infer other users' inputs by probing cache reuse, and proposes privacy-aware fine-grained sharing as a defense.

[Dithering Defense: Adversarial Robustness of Vision Foundation Models via Multi-Level Floyd-Steinberg Dithering](https://arxiv.org/abs/2605.23065) — *ArXiv cs.AI*
Proposes multi-level Floyd-Steinberg dithering as a lightweight, model-agnostic input transformation that disrupts adversarial perturbations against frozen vision foundation models while preserving semantics.

[MirrorCheck: Efficient Adversarial Defense for Vision-Language Models](https://arxiv.org/abs/2406.09250) — *ArXiv cs.AI*
A model-agnostic defense that regenerates images from captions via text-to-image models to detect adversarial attacks on vision-language models in unimodal and multimodal settings.

[Beyond Defenses: Manifold-Aligned Regularization for Intrinsic 3D Point Cloud Robustness](https://arxiv.org/abs/2605.07590) — *ArXiv cs.CV*
Attributes adversarial fragility in 3D point-cloud networks to manifold misalignment and proposes intrinsic geometric regularization to improve robustness beyond augmentation-based defenses.

[Kernel-Based ReLU Approximation for Homomorphic Encryption-Compatible Privacy-preserving Deep Learning Models](https://arxiv.org/abs/2605.23641) — *ArXiv cs.CR*
Introduces a homomorphic-encryption-compatible approximation of ReLU to enable privacy-preserving deep learning, including for non-linear LLM activations, on encrypted data.

[PromptCOS: Towards Content-only System Prompt Copyright Auditing for LLMs](https://arxiv.org/abs/2509.03117) — *ArXiv cs.CR*
Proposes content-only copyright auditing for LLM system prompts — valuable IP increasingly vulnerable to theft — without requiring access to model internals.

[Hidden Human-Like Nature of Machine-Generated Texts: Theory and Detection Enhancement](https://arxiv.org/abs/2605.23190) — *ArXiv cs.CL*
Argues that machine-generated text retains hidden human-like traits and leverages this to improve detection, addressing misuse such as fake-news propagation and phishing.

[GT-HarmBench: Benchmarking AI Safety Risks Through the Lens of Game Theory](https://arxiv.org/abs/2602.12316) — *ArXiv cs.AI*
Benchmark of 1,535 high-stakes multi-agent scenarios structured as game-theoretic dilemmas (Prisoner's Dilemma, Stag Hunt, Chicken) to evaluate AI safety risks like coordination failure and conflict.

[Beyond Zero: Enterprise Security for the AI Era](https://arxiv.org/abs/2605.22985) — *ArXiv cs.CR*
Proposes a security paradigm that shrinks the trust boundary below the application level, making per-resource access decisions for humans and autonomous agents at machine speed.

[From Preventive to Reactive: How AI Coding Assistants Transform Developers' Security Awareness](https://arxiv.org/abs/2605.23130) — *ArXiv cs.CR*
Interviews with 15 professional developers find that AI coding assistants shift security practice from preventive to reactive, changing how developers think about and catch vulnerabilities.

[Less Effort, Shorter Proofs: Reinforcement Learning for Security Protocol Analysis in Tamarin](https://arxiv.org/abs/2605.23643) — *ArXiv cs.LG*
Presents an AlphaZero-inspired reinforcement learning framework to accelerate security-protocol verification in Tamarin, reducing the human effort needed to prove protocols like EMV, 5G, and WPA2.

[Botnet Detection on CTU-13 Using Lightweight Machine Learning Models](https://arxiv.org/abs/2605.23004) — *ArXiv cs.CR*
Comparative study showing lightweight, interpretable ML models (logistic regression, decision trees, random forests) can detect botnet traffic on CTU-13 without the cost of deep learning.

## Vulnerabilities & Exploits

[Ghost CMS CVE-2026-26980 Exploited to Hijack 700+ Sites for ClickFix Attacks](https://thehackernews.com/2026/05/ghost-cms-cve-2026-26980-exploited-to.html) — *The Hacker News*
Threat actors are exploiting CVE-2026-26980 (CVSS 9.4), a critical SQL injection in Ghost CMS's Content API, to inject malicious JavaScript and fuel ClickFix attacks; QiAnXin XLab reports more than 700 hijacked sites.

[Ghost CMS SQL injection flaw exploited in large-scale ClickFix campaign](https://www.bleepingcomputer.com/news/security/ghost-cms-sql-injection-flaw-exploited-in-large-scale-clickfix-campaign/) — *BleepingComputer*
A large-scale campaign is exploiting the same critical Ghost CMS SQL injection flaw (CVE-2026-26980) to plant JavaScript that triggers ClickFix attack flows.

[TrapDoor Supply Chain Attack Spreads Credential-Stealing Malware via npm, PyPI, and CratesIO](https://thehackernews.com/2026/05/trapdoor-supply-chain-attack-spreads.html) — *The Hacker News*
A coordinated cross-ecosystem supply-chain campaign, codenamed TrapDoor, spread credential-stealing malware via 34+ malicious packages across 384+ versions on npm, PyPI, and Crates.io, with activity beginning May 22, 2026.

[Lazarus Deploys RemotePE Memory-Only RAT Against Financial and Crypto Firms](https://thehackernews.com/2026/05/lazarus-deploys-remotepe-memory-only.html) — *The Hacker News*
Fox-IT details RemotePE, a cross-platform memory-only RAT used by North Korea's Lazarus Group against financial and cryptocurrency organizations via a multi-stage chain involving DPAPILoader and RemotePELoader.

[FBI warns of Kali365 phishing service targeting Microsoft 365 accounts](https://www.bleepingcomputer.com/news/security/fbi-warns-of-kali365-phishing-service-targeting-microsoft-365-accounts/) — *BleepingComputer*
The FBI warns of the Kali365 phishing-as-a-service platform, which hijacks Microsoft 365 accounts by abusing OAuth device-code authentication to steal session tokens and bypass multi-factor authentication.

[⚡ Weekly Recap: Linux Flaws, Defender 0-Days, Router Botnets, and Supply Chain Chaos](https://thehackernews.com/2026/05/weekly-recap-linux-flaws-defender-0.html) — *The Hacker News*
The weekly roundup covers Linux flaws, Windows Defender zero-days, router botnets, supply-chain compromises, and increasingly targeted phishing.

[Netherlands Seizes 800 Servers, Arrests 2 for Aiding Cyberattacks](https://krebsonsecurity.com/2026/05/netherlands-seizes-800-servers-arrests-2-for-aiding-cyberattacks/) — *Krebs on Security*
Dutch authorities arrested two co-owners of related hosting companies and seized 800 servers tied to infrastructure used by Russia for cyberattacks, influence operations, and disinformation inside the EU.

[Hackers are learning to exploit chatbot 'personalities'](https://www.theverge.com/column/935545/hackers-ai-chatbots) — *The Verge AI*
A look at how attackers have moved from trivially jailbreaking the first generation of AI chatbots to exploiting the "personalities" of today's more capable assistants.
