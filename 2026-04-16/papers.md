# Research Paper Summaries — 2026-04-16

Papers selected from today's digest for in-depth review.

---

## 1. AISafetyBenchExplorer: A Metric-Aware Catalogue of AI Safety Benchmarks Reveals Fragmented Measurement and Weak Benchmark Governance

**Authors:** Abiodun A. Solanke
**Link:** [AISafetyBenchExplorer](https://arxiv.org/abs/2604.12875)
**Tags:** cs.AI

### Summary
This paper addresses a structural problem in AI safety evaluation: the proliferation of benchmarks has far outpaced the standardization of what those benchmarks actually measure. The author presents AISafetyBenchExplorer, a catalogued collection of 195 AI safety benchmarks released between 2018 and 2026, organized through a multi-sheet schema capturing benchmark-level metadata, metric definitions, and repository activity. The analysis reveals that while medium-complexity benchmarks dominate (94 of 195), only 7 reach "Popular" tier adoption. Coverage is heavily skewed — 165 of 195 benchmarks are English-only, 170 are evaluation-only with no training data, and 137 have stale GitHub repositories, suggesting the benchmark ecosystem is fragmented and under-maintained.

Critically, the paper finds that familiar metric labels like "accuracy," "safety score," and "F1" conceal materially different threat models and aggregation rules, making cross-paper safety claims largely incomparable. The author argues the field's core failure mode is fragmentation rather than scarcity: there are many benchmark artifacts, but no shared measurement language and no stewardship norms for post-publication maintenance. AISafetyBenchExplorer provides a traceable catalogue and complexity taxonomy to support more rigorous benchmark discovery and meta-evaluation. A notable limitation is the single-author scope — the catalogue reflects one researcher's classification decisions and may have gaps. The broader implication is that safety claims backed only by benchmark performance should be treated with significant skepticism until the governance gap is addressed.

### Key Takeaways
- 195 AI safety benchmarks exist, but only 7 are widely adopted; 137 have stale repositories, indicating the ecosystem is poorly maintained.
- Common metric labels ("accuracy," "safety score") hide fundamentally different threat models, making cross-model safety comparisons unreliable.
- The field needs coordinated benchmark stewardship and standardized measurement language before safety certifications can be meaningful.

---

## 2. HazardArena: Evaluating Semantic Safety in Vision-Language-Action Models

**Authors:** Zixing Chen, Yifeng Gao, Li Wang, Yunhan Zhao, Yi Liu, Jiayu Li, Xiang Zheng, Zuxuan Wu, Cong Wang, Xingjun Ma, Yu-Gang Jiang
**Link:** [HazardArena](https://arxiv.org/abs/2604.12447)
**Tags:** cs.RO

### Summary
Vision-Language-Action (VLA) models are increasingly deployed in physical robotics, but existing safety evaluations measure only task execution success — not whether the robot correctly refuses semantically unsafe instructions. HazardArena closes this gap with a benchmark built around "safe/unsafe twin scenarios": paired tasks that share identical objects, layouts, and action requirements but differ only in the semantic context that determines whether execution is hazardous. For example, picking up a knife in a kitchen setup (safe context) versus handing it to an agitated person (unsafe context). The benchmark includes over 2,000 assets and 40 risk-sensitive tasks spanning 7 real-world risk categories grounded in established robotic safety standards.

The key finding is that VLA models trained exclusively on safe scenarios systematically fail to behave safely in their corresponding unsafe counterparts — they execute the action regardless of semantic risk. To mitigate this without retraining, the paper proposes a training-free Safety Option Layer that constrains execution using semantic attributes or a vision-language judge. This layer substantially reduces unsafe behaviors with minimal impact on task performance. A limitation is that the benchmark is simulation-based and may not capture the full distribution of real-world hazard contexts. The implication for physical AI deployment — particularly as NVIDIA and Hitachi push AI into industrial infrastructure — is that action success rates alone are a dangerously incomplete safety metric.

### Key Takeaways
- VLA robot models trained on safe scenarios routinely fail to refuse semantically unsafe instructions when context shifts.
- Task execution success rate is an insufficient safety metric for physical AI; semantic hazard recognition must be evaluated independently.
- A training-free Safety Option Layer can substantially reduce unsafe behaviors with minimal task performance impact.

---

## 3. The Long-Horizon Task Mirage? Diagnosing Where and Why Agentic Systems Break

**Authors:** Xinyu Jessica Wang, Haoyue Bai, Yiyou Sun, Haorui Wang, Shuibai Zhang, Wenjie Hu, Mya Schroder, Bilge Mutlu, Dawn Song, Robert D Nowak
**Link:** [The Long-Horizon Task Mirage?](https://arxiv.org/abs/2604.11978)
**Tags:** cs.AI

### Summary
Despite impressive benchmark scores on short tasks, LLM-based agents consistently break down on long-horizon tasks requiring extended, interdependent action sequences. This paper introduces HORIZON, a cross-domain diagnostic benchmark designed to systematically construct tasks and analyze failure modes as task horizon grows. The authors evaluate state-of-the-art agents from GPT-5 variants and Claude model families, collecting over 3,100 trajectories across four representative agentic domains. The analysis examines horizon-dependent degradation patterns — specifically, which failure categories (planning errors, tool misuse, context loss, recovery failures) emerge at which task lengths.

To make failure attribution scalable, the authors propose a trajectory-grounded LLM-as-a-Judge pipeline, validated against human annotations with strong inter-annotator agreement (κ=0.61) and human-judge agreement (κ=0.84). The key finding is that apparent benchmark progress on short- and mid-horizon tasks masks fundamental planning brittleness in real-world extended action sequences — a "mirage" in which headline scores overstate actual capability. Practical implications are significant: as enterprises deploy agentic systems for multi-step workflows, the failure modes identified here — particularly cascading planning errors and inability to recover from mid-sequence mistakes — will surface at scale. A limitation is that the benchmark focuses on specific agentic domains, and the generalizability of failure categories across all task types remains an open question.

### Key Takeaways
- LLM agents that perform well on short tasks exhibit systematic, horizon-dependent degradation on long-horizon sequences that benchmark scores hide.
- The HORIZON benchmark enables cross-domain, reproducible failure attribution at scale using an LLM-as-a-Judge pipeline with high human agreement.
- Planning brittleness and inability to recover from mid-sequence errors are the dominant failure categories as task length increases.

---

## 4. Every Picture Tells a Dangerous Story: Memory-Augmented Multi-Agent Jailbreak Attacks on VLMs

**Authors:** Jianhao Chen, Haoyang Chen, Hanjie Zhao, Haozhe Liang, Tieyun Qian
**Link:** [Every Picture Tells a Dangerous Story](https://arxiv.org/abs/2604.12616)
**Tags:** cs.AI

### Summary
Most multimodal jailbreak research focuses on pixel-level perturbations or typographic overlays, leaving the deep semantic content of natural images largely unexplored as an attack surface. This paper introduces MemJack, a Memory-augmented multi-agent JAilbreak attaCK framework that exploits visual semantics to orchestrate automated, multi-turn jailbreak attacks against vision-language models. The framework uses coordinated multi-agent cooperation to dynamically map visual entities to malicious intents, generate adversarial prompts via multi-angle visual-semantic camouflage, and apply an Iterative Nullspace Projection (INLP) geometric filter to bypass latent-space refusals. Critically, successful strategies are persisted in a Multimodal Experience Memory that transfers knowledge across different images, enabling coherent multi-turn attack sessions.

Evaluated on unmodified COCO val2017 images, MemJack achieves a 71.48% attack success rate (ASR) against Qwen3-VL-Plus, scaling to 90% under extended budgets. The paper will release MemJack-Bench, a dataset of over 113,000 multimodal jailbreak trajectories to support defensive alignment research. The primary limitation is that the attack is computationally intensive compared to single-shot methods. The implications are severe for production VLM deployments: persistent memory across agentic pipelines dramatically amplifies attack surface, suggesting that multi-turn context management must be treated as a security boundary, not just a usability feature.

### Key Takeaways
- Persistent memory in multi-agent VLM pipelines creates a transferable jailbreak attack surface that single-session defenses cannot address.
- MemJack achieves 71–90% attack success rates against leading VLMs using only natural, unmodified images as semantic attack vectors.
- Multi-turn context management must be treated as a security boundary in production agentic systems.

---

## 5. TEMPLATEFUZZ: Fine-Grained Chat Template Fuzzing for Jailbreaking and Red Teaming LLMs

**Authors:** Qingchao Shen, Zibo Xiao, Lili Huang, Enwei Hu, Yongqiang Tian, Junjie Chen
**Link:** [TEMPLATEFUZZ](https://arxiv.org/abs/2604.12232)
**Tags:** cs.CR

### Summary
While most jailbreak research targets prompt content, this paper identifies chat prompt templates — the structured formatting layer that wraps user and assistant messages — as an underexplored but highly exploitable attack surface. TEMPLATEFUZZ is a fine-grained fuzzing framework that applies element-level mutation rules to generate diverse chat template variants, guided by a heuristic search strategy that maximizes attack success rate (ASR) while preserving model accuracy. An active learning-based oracle provides efficient jailbreak evaluation, replacing the expensive human-in-the-loop labeling typically required.

Evaluated on 12 open-source LLMs, TEMPLATEFUZZ achieves a 98.2% average ASR with only 1.1% accuracy degradation, outperforming state-of-the-art methods by 9.1–47.9% in ASR. More alarmingly, even on 5 commercial LLMs where chat templates cannot be directly specified, TEMPLATEFUZZ achieves a 90% average ASR through template-based prompt injection attacks. The finding that many safety defenses are template-format dependent rather than semantically robust exposes a fundamental weakness: safety training that does not account for template variation will be bypassed at the formatting layer. A key limitation is that this research was performed on open-source models where template manipulation is straightforward; real-world attack paths via injection are harder to execute reliably at scale.

### Key Takeaways
- Chat template format is a critical and underexplored attack surface; 98.2% jailbreak success rates are achievable through template mutation alone.
- Many LLM safety defenses are template-format dependent rather than semantically grounded, making them brittle to formatting changes.
- Commercial models without exposed template controls are still vulnerable (90% ASR) via template-based prompt injection.

---

## 6. WebAgentGuard: A Reasoning-Driven Guard Model for Detecting Prompt Injection Attacks in Web Agents

**Authors:** Yulin Chen, Tri Cao, Haoran Li, Yue Liu, Yibo Li, Yufei He, Le Minh Khoi, Yangqiu Song, Shuicheng Yan, Bryan Hooi
**Link:** [WebAgentGuard](https://arxiv.org/abs/2604.12284)
**Tags:** cs.CR

### Summary
Web agents powered by vision-language models are particularly vulnerable to prompt injection: adversarial instructions embedded in HTML or webpage screenshots can hijack agent behavior and cause data leakage or unauthorized actions. Existing defenses — system prompt hardening and direct fine-tuning of the agent — show limited effectiveness because they conflate instruction-following with safety reasoning. WebAgentGuard addresses this by decoupling detection from action: a dedicated guard agent runs in parallel with the web agent and evaluates whether the perceived environment contains injected instructions before the agent acts.

The WebAgentGuard model is a multimodal reasoning model trained on a synthetic dataset built using GPT-5, covering 164 topics and 230 visual/UI styles. Training uses reasoning-intensive supervised fine-tuning followed by reinforcement learning. The guard model processes both visual and textual webpage content, enabling it to detect injection attempts that are visually camouflaged or encoded in page layout rather than plain text. Experiments show consistent outperformance over strong baselines without additional inference latency on the main agent. A limitation is the reliance on synthetic training data, which may not cover all real-world adversarial webpage styles. The broader implication is that multi-agent safety architectures — where a specialized guard monitors a primary agent — may be more robust than monolithic safety-trained agents for web-facing deployments.

### Key Takeaways
- Decoupling prompt injection detection into a parallel guard agent is more effective than integrating safety directly into the web agent.
- WebAgentGuard uses multimodal reasoning (visual + textual) to catch injection attempts that are visually encoded or hidden in page layout.
- Parallel guard architecture adds no latency to the primary agent while substantially improving injection detection rates.

---

## 7. DeepSeek Robustness Against Semantic-Character Dual-Space Mutated Prompt Injection

**Authors:** Junyu Ren, Xingjian Pan, Wensheng Gan, Philip S. Yu
**Link:** [DeepSeek Robustness Against Semantic-Character Dual-Space Mutated Prompt Injection](https://arxiv.org/abs/2604.12548)
**Tags:** cs.CR

### Summary
Existing prompt injection research typically evaluates single-dimensional attack strategies — either semantic rewriting (paraphrasing, word-order changes) or character-level obfuscation (zero-width characters, encoding mutations) — but not both simultaneously. This paper proposes PromptFuzz-SC, a semantic-character dual-space mutation framework, and systematically evaluates it against DeepSeek models, one of the first black-box robustness evaluations of a major Chinese LLM. The framework integrates semantic transformations with character-level obfuscation into a unified, extensible mutation operator library, using a hybrid epsilon-greedy and hill-climbing search strategy to discover high-quality adversarial prompts efficiently.

Results demonstrate that dual-space mutation consistently outperforms single-space attacks on DeepSeek: it achieves the highest mean misuse success rate (0.189), peak MSR (0.375), and strongest stealth score, improving over semantic-only and character-only baselines by 12.5% and 5.6% respectively. The evaluation introduces three standardized metrics — MSR, Average Queries to Success, and Stealth — providing a more complete picture than ASR alone. A key limitation is that results are limited to DeepSeek models, and generalizability to other LLM families with different safety training approaches is not established. The implication is that single-dimensional defenses (filtering character obfuscation, or semantic classifiers alone) are insufficient, and production systems require layered, cross-dimensional robustness.

### Key Takeaways
- Combining semantic and character-level mutations in a single attack framework outperforms either dimension alone against DeepSeek models.
- Single-dimensional defenses — whether semantic classifiers or character-level filters — leave significant attack surface exposed.
- PromptFuzz-SC introduces standardized multi-metric evaluation (MSR, AQS, Stealth) as a more complete red-teaming framework.

---

## 8. ContextLens: Modeling Imperfect Privacy and Safety Context for Legal Compliance

**Authors:** Haoran Li, Yulin Chen, Huihao Jing, Wenbin Hu, Tsz Ho Li, Chanhou Lou, Hong Ting Tsang, Sirui Han, Yangqiu Song
**Link:** [ContextLens](https://arxiv.org/abs/2604.12308)
**Tags:** cs.CL

### Summary
Privacy and safety violations are fundamentally context-dependent: the same data disclosure may be lawful in one situation and a GDPR violation in another. Most LLM-based compliance tools assume complete, unambiguous context is available — an assumption that breaks in real deployments where context is routinely incomplete or ambiguous. ContextLens is a semi-rule-based framework that uses LLMs to ground input context in the legal domain and explicitly identifies both known and unknown contextual factors relevant to compliance assessment.

Rather than directly classifying safety outcomes, ContextLens instructs LLMs to answer a structured question set spanning applicability, general principles, and detailed provisions, then assesses compliance according to pre-defined priorities — essentially a legal reasoning scaffold. Evaluated on benchmarks covering GDPR and the EU AI Act, ContextLens significantly improves compliance assessment accuracy over existing baselines without any training required. It also identifies ambiguous and missing contextual factors, which is critical for surfacing uncertainty rather than defaulting to false confidence. A limitation is that the framework is currently evaluated on two regulatory frameworks and may require significant adaptation for other jurisdictions. As regulatory compliance becomes a competitive differentiator for AI deployments — particularly given the EU AI Act enforcement timeline — frameworks that reason under incomplete context rather than failing silently will be essential.

### Key Takeaways
- Real-world legal compliance assessment must reason under incomplete context, not assume full information availability.
- ContextLens uses structured legal question scaffolding to significantly improve GDPR and EU AI Act compliance accuracy over LLM baselines without training.
- Explicitly identifying ambiguous and missing contextual factors is as important as reaching a compliance verdict.

---

## 9. LLM-Redactor: An Empirical Evaluation of Eight Techniques for Privacy-Preserving LLM Requests

**Authors:** Justice Owusu Agyemang, Jerry John Kponyo, Elliot Amponsah, Godfred Manu Addo Boakye, Kwame Opuni-Boachie Obour Agyekum
**Link:** [LLM-Redactor](https://arxiv.org/abs/2604.12064)
**Tags:** cs.CR

### Summary
Coding agents and LLM-powered enterprise applications routinely send sensitive content to cloud LLM APIs, where it may be logged, retained, used for training, or subpoenaed. Existing privacy controls address network-layer encryption and organizational DLP policies, but neither approach prevents sensitive prompt content from reaching cloud providers. This paper systematically evaluates eight techniques for privacy-preserving LLM requests: local-only inference, redaction with placeholder restoration, semantic rephrasing, Trusted Execution Environment inference, split inference, fully homomorphic encryption, secret sharing via MPC, and differential-privacy noise. The evaluation uses a ground-truth leak benchmark of 1,300 samples with 4,014 annotations across four workload classes.

The headline finding is that no single technique dominates across all threat models. The combination of local routing + redaction + rephrasing achieves 0.6% combined PII leak rate and 31.3% on proprietary code, with zero exact PII leaks across 500 samples. The paper provides a practical decision rule for selecting techniques based on threat model and budget. An open-source shim compatible with MCP and any OpenAI-compatible API is released. A notable limitation is that proprietary code still leaks at a 31% rate even under the best combination, making this approach inadequate for high-sensitivity IP scenarios. This research directly addresses current enterprise concerns about AI agents handling regulated data under GDPR, HIPAA, and emerging AI Act requirements.

### Key Takeaways
- No single privacy-preserving technique dominates; combining local routing, redaction, and semantic rephrasing achieves the lowest PII leak rate (0.6%).
- Proprietary code is significantly harder to protect than PII — even the best technique combination leaks 31% of code content.
- A practical decision rule matching technique selection to threat model and workload type makes this research immediately deployable.

---

## 10. Preventing Safety Drift in Large Language Models via Coupled Weight and Activation Constraints

**Authors:** Songping Peng, Zhiheng Zhang, Daojian Zeng, Lincheng Jiang, Xieping Gao
**Link:** [Preventing Safety Drift in Large Language Models via Coupled Weight and Activation Constraints](https://arxiv.org/abs/2604.12384)
**Tags:** cs.AI

### Summary
Safety alignment in LLMs degrades during fine-tuning — even when the fine-tuning data is entirely benign. This is a critical problem for enterprise deployments that customize models for specific use cases, as each fine-tuning round risks eroding the safety behaviors established during RLHF. Existing defenses constrain either model weights or activations in isolation, but this paper demonstrates theoretically that constraining either dimension alone is insufficient because of their coupled interaction in determining safety-relevant behavior.

The proposed solution is CWAC (Coupled Weight and Activation Constraints), which simultaneously enforces a precomputed safety subspace on weight updates and applies targeted regularization to safety-critical features identified via sparse autoencoders. By anchoring both weight trajectory and activation patterns to the pre-fine-tuning safety state, CWAC preserves refusal behaviors while allowing task-specific adaptation. Evaluated across four widely used LLMs on diverse downstream tasks, CWAC consistently achieves the lowest harmful response scores with minimal accuracy degradation, outperforming strong baselines even when fine-tuning data contains up to high harmful-data ratios. A limitation is the computational overhead of precomputing the safety subspace and the sparse autoencoder analysis, which may be prohibitive for rapid iteration. The implication is significant: any organization fine-tuning foundation models on proprietary data must apply post-fine-tuning safety audits or adopt techniques like CWAC to avoid silent safety regression.

### Key Takeaways
- Safety alignment degrades during fine-tuning even with benign data; constraining only weights or only activations is theoretically insufficient.
- CWAC couples weight-space and activation-space constraints during training, preserving refusal behaviors across diverse downstream fine-tuning tasks.
- Organizations fine-tuning foundation models must treat safety alignment preservation as an explicit engineering constraint, not an assumed invariant.

---

## 11. Malice in Agentland: Down the Rabbit Hole of Backdoors in the AI Supply Chain

**Authors:** Léo Boisvert, Abhay Puri, Chandra Kiran Reddy Evuru, Nazanin Sepahvand, Nicolas Chapados, Quentin Cappart, Alexandre Lacoste, Krishnamurthy Dj Dvijotham, Alexandre Drouin
**Link:** [Malice in Agentland](https://arxiv.org/abs/2510.05159)
**Tags:** cs.CR

### Summary
Fine-tuning AI agents on interaction data — such as web browsing trajectories or tool-use demonstrations — is the standard path to improving agent capabilities, but this paper shows it also introduces critical supply chain vulnerabilities. The authors formalize three realistic threat models across the agentic training pipeline: direct poisoning of fine-tuning data, deploying pre-backdoored base models, and environment poisoning — a novel vector that exploits vulnerabilities specific to agentic training where the environment itself participates in generating training data.

Evaluated on two widely adopted agentic benchmarks, all three threat models prove effective with minimal data poisoning: corrupting only a small number of demonstrations is sufficient to embed a backdoor causing the agent to leak confidential user information with over 80% success rate. The backdoors are hard to detect through normal testing because they only activate on specific trigger conditions. The implication is that the entire agentic fine-tuning supply chain — from data collection pipelines to third-party interaction datasets to base model providers — must be treated as a potential attack surface. As the market for pre-trained and fine-tuned agents grows, the risk of acquiring an agent with an embedded backdoor from an untrusted source becomes material. Limitations include the focus on information leakage as the trigger behavior; other backdoor payloads (e.g., financial fraud, lateral movement) may have different detection profiles.

### Key Takeaways
- Poisoning as few as a small number of fine-tuning demonstrations can embed backdoors that cause agents to leak confidential data with 80%+ success.
- Three distinct supply chain attack vectors exist: data poisoning, pre-backdoored base models, and environment poisoning during agentic training.
- The entire agentic fine-tuning supply chain must be treated as a security boundary — third-party datasets and base models are not inherently trustworthy.

---

## 12. ASGuard: Activation-Scaling Guard to Mitigate Targeted Jailbreaking Attacks

**Authors:** Yein Park, Jungwoo Park, Jaewoo Kang
**Link:** [ASGuard](https://arxiv.org/abs/2509.25843)
**Tags:** cs.AI

### Summary
Safety-aligned LLMs exhibit brittle refusal behaviors that fail under simple linguistic transformations — the canonical example being "tense jailbreaking," where a model refusing a harmful request in present tense complies when the same request is rephrased in past tense. This fragility exposes a generalization gap in current alignment methods. ASGuard (Activation-Scaling Guard) addresses this through mechanistic interpretability: the authors first use circuit analysis to identify the specific attention heads causally responsible for tense-sensitive refusal behavior, then train a channel-wise activation scaling vector that recalibrates those vulnerable heads.

The scaling vector is applied as a "preventative fine-tuning" step, forcing the model to learn a more robust refusal mechanism rather than patching the vulnerability post-hoc. Evaluated across four LLMs, ASGuard effectively reduces the attack success rate of targeted jailbreaks while preserving general capabilities and minimizing over-refusal, achieving a Pareto-optimal balance between safety and utility. The mechanistic analysis also reveals that adversarial suffixes suppress the propagation of refusal-mediating activation directions — explaining why suffix-based attacks succeed even against well-aligned models. A limitation is that the current implementation targets tense-changing attacks specifically; extending the circuit analysis and scaling approach to other jailbreak categories requires additional interpretability work. The broader contribution is demonstrating that mechanistic understanding of alignment failures enables more targeted and efficient fixes than behavioral patching.

### Key Takeaways
- LLM refusal behaviors are brittle to simple linguistic reformulations (e.g., tense changes); this is a structural generalization gap, not a corner case.
- Circuit analysis identifies specific attention heads mediating the vulnerability, enabling targeted activation-scaling fixes rather than broad retraining.
- Adversarial suffixes suppress refusal-mediating activation directions — mechanistic interpretability explains why alignment-based defenses fail against suffix attacks.

---

*Generated from the [digest for 2026-04-16](digest-2026-04-16.md).*
