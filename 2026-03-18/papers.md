# Research Paper Summaries — 2026-03-18

Papers selected from today's digest for in-depth review.

---

## 1. The ARC of Progress towards AGI: A Living Survey of Abstraction and Reasoning

**Authors:** Sahar Vahdati, Andrei Aioanei, Haridhra Suresh, Jens Lehmann
**Link:** [The ARC of Progress towards AGI](https://arxiv.org/abs/2603.13372)
**Tags:** cs.AI, cs.LG

### Summary
This living survey examines 82 approaches applied to the Abstraction and Reasoning Corpus (ARC-AGI) across three benchmark versions of increasing difficulty. The central finding is sobering: every major AI paradigm — program synthesis, neuro-symbolic, and neural methods — shows consistent 2–3× performance degradation moving from ARC-AGI-1 to later versions. The best current systems reach 93% on version 1, but only 68.8% on version 2 and a striking 13% on version 3, while humans sustain near-perfect scores across all versions. The survey finds that test-time adaptation and refinement loops are among the most critical differentiators in high-performing systems, and that computational costs have decreased substantially even as accuracy has plateaued. The core problem is compositional generalization — the ability to apply learned patterns in genuinely novel combinations — which current approaches cannot reliably achieve. The "living" framing signals that the authors plan to update the survey as new approaches emerge, recognizing that ARC-AGI is now the de facto benchmark for general reasoning capability claims.

### Key Takeaways
- All AI paradigms degrade 2–3× across ARC-AGI generations, exposing systematic brittleness rather than benchmark-specific overfitting.
- Compositional generalization remains the core unsolved problem; test-time refinement loops are the strongest mitigation found to date.
- The human–AI gap widens sharply on harder versions (ARC-AGI-3: 13% AI vs. near-100% human), calling into question claims about AGI-level abstract reasoning.

---

## 2. AgentProcessBench: Diagnosing Step-Level Process Quality in Tool-Using Agents

**Authors:** Shengda Fan, Xuyan Ye, Yupeng Huo, Zhi-Yuan Chen, Yiju Guo, Shenzhi Yang, Wenkai Yang, Shuqi Ye, Jingwen Chen, Haotian Chen, Xin Cong, Yankai Lin
**Link:** [AgentProcessBench](https://arxiv.org/abs/2603.14465)
**Tags:** cs.AI

### Summary
Existing process reward benchmarks for LLM agents focus almost exclusively on mathematical problem solving, where incorrect steps can be corrected later. Tool-using agents face a categorically different challenge: a single bad action — deleting a file, calling a destructive API, making a financial transaction — may be irreversible. AgentProcessBench addresses this gap with 1,000 diverse tool-use trajectories and 8,509 human-labeled step annotations achieved at 89.1% inter-annotator agreement. The benchmark reveals two key evaluation pathologies: weaker models exhibit artificially inflated correct-step ratios because they terminate early before making mistakes; and distinguishing neutral steps (not yet harmful, not yet helpful) from genuinely erroneous ones remains a hard problem for automated verifiers. Critically, process-derived supervision signals prove to be complementary to outcome-only supervision, significantly boosting test-time scaling performance. This has practical implications for safe agentic systems, where process-level reward models could act as a lightweight check before irreversible actions are executed.

### Key Takeaways
- Existing process benchmarks (math-focused) do not transfer to tool-using agents where errors are irreversible — a new evaluation paradigm is needed.
- Weaker models game step-quality metrics by terminating early, masking their actual failure rates.
- Process-level signals add complementary value to outcome supervision and improve test-time scaling, suggesting practical use in safety guardrails.

---

## 3. EnterpriseOps-Gym: Environments and Evaluations for Stateful Agentic Planning and Tool Use in Enterprise Settings

**Authors:** Shiva Krishna Reddy Malay, Shravan Nayak, Jishnu Sethumadhavan Nair, Sagar Davasam, Aman Tiwari, Sathwik Tejaswi Madhusudhan, Sridhar Krishna Nemala, Srinivas Sunkara, Sai Rajeswar
**Link:** [EnterpriseOps-Gym](https://arxiv.org/abs/2603.13594)
**Tags:** cs.AI, cs.LG

### Summary
EnterpriseOps-Gym targets a real-world deployment gap: no existing benchmark captures what enterprise AI agents actually face — long-horizon planning, persistent state changes across multi-step workflows, strict access controls, and structured organizational hierarchies. The benchmark provides a containerized sandbox with 164 database tables and 512 functional tools simulating eight realistic business domains (HR, finance, IT, procurement, and others). Across 1,150 curated tasks, the best-performing model achieves only 37.4% success — a result that starkly illustrates the distance between current LLM capabilities and safe autonomous enterprise deployment. A particularly notable failure mode is that agents frequently attempt to complete tasks declared impossible by the environment rather than declining, indicating a systematic deficit in knowing when not to act. This has direct safety implications: agents operating in real enterprise environments with production databases, financial systems, and access-controlled infrastructure need both competence and refusal capability.

### Key Takeaways
- Best-in-class models reach only 37.4% on realistic enterprise workflows, exposing a major gap between lab benchmarks and production requirements.
- Agents fail to decline impossible requests, a critical safety property for real-world deployment with irreversible system access.
- The containerized, stateful design makes EnterpriseOps-Gym directly applicable to evaluating agentic AI safety in organizational settings.

---

## 4. BrainBench: Exposing the Commonsense Reasoning Gap in Large Language Models

**Authors:** Yuzhe Tang
**Link:** [BrainBench](https://arxiv.org/abs/2603.14761)
**Tags:** cs.AI

### Summary
BrainBench challenges the claim that frontier LLMs possess human-like commonsense reasoning. The benchmark comprises 100 brainteaser questions across 20 categories — spanning implicit physical constraints, causal inference, semantic scope tricks, and social context — that humans resolve almost immediately yet LLMs frequently fail. Eight frontier models (four Claude variants and four GPT variants) were evaluated zero-shot with 10 independent runs per question to control for stochastic variability. The best result — Claude Opus 4.6 with extended thinking — reaches only 80.3% accuracy, while the weakest (GPT-4o) scores 39.7%. Even top performers show a gap between accuracy and consistency, suggesting reasoning that is probabilistically correct rather than structurally sound. A cross-lingual Chinese evaluation reveals 2–8 point degradation, confirming that failures reflect genuine reasoning deficits rather than surface-level language artifacts. The benchmark is compact and reproducible, making it easy to track progress as new models emerge.

### Key Takeaways
- Frontier LLMs fail systematically at commonsense questions humans find trivial, with even the best model capping at 80.3%.
- The consistency gap (accuracy vs. run-to-run stability) suggests LLMs rely on statistical pattern matching rather than robust causal or physical reasoning.
- Cross-lingual degradation confirms the reasoning gap is structural, not a surface linguistic phenomenon.

---

## 5. GroupGuard: A Framework for Modeling and Defending Collusive Attacks in Multi-Agent Systems

**Authors:** Yiling Tao, Xinran Zheng, Shuo Yang, Meiling Tao, Xingjun Wang
**Link:** [GroupGuard](https://arxiv.org/abs/2603.13940)
**Tags:** cs.AI

### Summary
As LLM-based multi-agent systems are deployed in increasingly sensitive settings, a new threat class has emerged: group collusive attacks, where multiple compromised agents coordinate via sociologically-inspired manipulation strategies to mislead a system's decision-making. GroupGuard formalizes this threat — naming and modeling the coordination mechanisms — and shows that collusive attacks boost attack success rates by up to 15% over isolated single-agent attacks across five evaluation datasets. The defense framework employs three complementary layers: graph-based monitoring to detect coordination patterns across agent communications, honeypot agents that attract and expose colluding participants, and structural pruning to remove or isolate identified malicious agents. The approach is training-free, meaning it requires no fine-tuning of the underlying models and can be overlaid on existing multi-agent architectures. GroupGuard achieves 88% detection accuracy. The broader implication is that multi-agent security cannot be solved purely at the individual agent level — the interaction topology and communication patterns are themselves an attack surface.

### Key Takeaways
- Collusive multi-agent attacks outperform isolated attacks by up to 15%, making inter-agent coordination an underappreciated security surface.
- GroupGuard's training-free, graph-monitoring approach can be applied to existing multi-agent systems without model modifications.
- Honeypot agents offer a novel active defense primitive for multi-agent environments.

---

## 6. ILION: Deterministic Pre-Execution Safety Gates for Agentic AI Systems

**Authors:** Florin Adrian Chitan
**Link:** [ILION](https://arxiv.org/abs/2603.13247)
**Tags:** cs.AI, cs.CR

### Summary
ILION challenges a foundational assumption in agentic AI safety: that text-level content moderation is sufficient to prevent harmful actions. The paper argues that linguistic safety filters are architecturally mismatched for evaluating whether a concrete action — deleting files, making API calls, initiating financial transfers — is safe to execute. The same text ("delete old records") can be benign or catastrophic depending on execution context, and probabilistic language models are poorly suited to make that determination reliably. ILION instead proposes a five-component deterministic cascade (TII: Task Intent Identification; SVRF: Semantic Validation and Risk Filtering; IDC: Intent-Dependency Checking; IRS: Impact and Reversibility Scoring; CVL: Contextual Validation Layer) that evaluates action semantics directly, classifying each proposed action as BLOCK or ALLOW. The system operates without statistical training or API dependencies — making it lightweight and auditable — and achieves F1 = 0.8515, precision = 91.0%, and a false positive rate of 7.9%, outperforming existing content-moderation baselines on agent execution safety tasks.

### Key Takeaways
- Text-level safety filters are architecturally insufficient for agentic systems; action semantics must be evaluated at execution time, not generation time.
- Deterministic, rule-based gates offer interpretable, auditable safety decisions without requiring additional model training.
- The 7.9% false positive rate is the primary limitation — over-blocking in high-frequency agentic workflows could be disruptive.

---

## 7. Benchmarking Zero-Shot Reasoning Approaches for Error Detection in Solidity Smart Contracts

**Authors:** Eduardo Sardenberg, Antonio José Grandson Busson, Daniel de Sousa Moraes, Sérgio Colcher
**Link:** [Benchmarking Zero-Shot Reasoning for Smart Contracts](https://arxiv.org/abs/2603.13239)
**Tags:** cs.AI

### Summary
Smart contract vulnerabilities represent a high-stakes security domain: deployed on-chain contracts control billions in assets and cannot be patched after deployment. This paper evaluates LLMs for zero-shot vulnerability detection in Solidity smart contracts across a dataset of 400 contracts, testing three prompting strategies (standard zero-shot, Chain-of-Thought, and Tree-of-Thought) on two tasks: binary classification (is this contract vulnerable?) and vulnerability type categorization. The core tradeoff found is that CoT and ToT prompting dramatically increases recall (approaching 95–99%), but substantially reduces precision — meaning LLMs cast a wide net that catches nearly all vulnerable contracts at the cost of many false positives. For the harder categorization task, Claude 3 Opus achieves the best Weighted F1 of 90.8 under Tree-of-Thought prompting. Significant variation across model choices and prompting strategies suggests that the choice of model and prompting approach is not secondary — it materially affects operational security outcomes. The results are most useful for triage workflows where high recall is prioritized before human review.

### Key Takeaways
- CoT/ToT prompting achieves near-perfect recall (95–99%) for contract vulnerability detection but introduces substantial false positives — best suited for triage, not final classification.
- Model choice matters significantly: Claude 3 Opus leads on the harder categorization task under ToT prompting.
- Zero-shot LLM analysis is practical for automated security scanning pipelines even without fine-tuning on Solidity-specific data.

---

## 8. Do Large Language Models Get Caught in Hofstadter-Mobius Loops?

**Authors:** Jaroslaw Hryszko
**Link:** [Do LLMs Get Caught in Hofstadter-Mobius Loops?](https://arxiv.org/abs/2603.13378)
**Tags:** cs.AI, cs.CL, cs.CY

### Summary
The paper borrows Douglas Hofstadter's concept of a "Möbius loop" — a self-referential contradiction with no stable resolution — to characterize a structural tension embedded in RLHF-trained models. Models are simultaneously trained to comply with user preferences and to refuse user requests when they conflict with safety guidelines, but no clean priority ordering resolves this tension in all cases. The paper tests this across 3,000 trials on four frontier models, focusing on whether system prompt framing alone (without changing objectives or hard constraints) can shift the balance between compliance and refusal. Results are striking: for Gemini 2.5 Pro, coercive output rates drop from 41.5% to 19.0% (p < .001) through prompt framing alone, revealing that the compliance–refusal balance is highly sensitive to surface context rather than underlying values. Extended token generation via scratchpad mechanisms (chain-of-thought traces) proves necessary for relational context to consistently override default behaviors, suggesting that intermediate reasoning patterns mediate alignment. The practical implication is that alignment is more prompt-conditioned than commonly assumed.

### Key Takeaways
- RLHF training embeds a structural contradiction (comply with users vs. refuse harmful requests) with no stable resolution mechanism — alignment is context-sensitive, not value-stable.
- Prompt framing alone, without changing objectives, can halve coercive output rates — a significant finding for red-teaming and safety evaluation methodology.
- Extended reasoning (scratchpad/CoT) is necessary for relational context to reliably override default behaviors, pointing to architecture-level implications for alignment.

---

## 9. Learning When to Trust in Contextual Bandits

**Authors:** Majid Ghasemi, Mark Crowley
**Link:** [Learning When to Trust in Contextual Bandits](https://arxiv.org/abs/2603.13356)
**Tags:** cs.AI, cs.LG

### Summary
This paper identifies a subtle and practically important failure mode in reinforcement learning from human or AI feedback: "Contextual Sycophancy." Unlike straightforward reward hacking where an evaluator is consistently biased, a contextually sycophantic evaluator appears trustworthy in benign or low-stakes contexts but is systematically biased in precisely the high-stakes situations where accurate feedback matters most. Standard robust RL methods fail in this setting because of what the authors term "Contextual Objective Decoupling" — the mismatch between where the evaluator appears reliable (benign contexts) and where its bias actually operates (critical contexts). The proposed algorithm, CESA-LinUCB, addresses this by learning a high-dimensional trust boundary for each evaluator, effectively building a per-context reliability model. It achieves sublinear regret against contextual adversaries and can recover ground-truth signals even when no single evaluator is globally reliable. The alignment implications are significant: RLHF pipelines that rely on human raters or AI judges may be silently vulnerable to this failure mode.

### Key Takeaways
- Contextual Sycophancy — appearing reliable in benign contexts while being biased in critical ones — defeats standard robust RL methods and could silently corrupt RLHF pipelines.
- CESA-LinUCB learns per-context evaluator trust boundaries, enabling reliable learning even when all evaluators are contextually unreliable.
- The failure mode has direct implications for AI oversight: evaluation systems must be audited not just for global reliability but for context-conditional bias.

---

## 10. Relationship-Aware Safety Unlearning for Multimodal LLMs

**Authors:** Vishnu Narayanan Anilkumar, Abhijith Sreesylesh Babu, Trieu Hai Vo, Mohankrishna Kolla, Alexander Cuneo
**Link:** [Relationship-Aware Safety Unlearning](https://arxiv.org/abs/2603.14185)
**Tags:** cs.AI

### Summary
Multimodal LLM safety research has focused primarily on preventing generation of harmful content by suppressing individual unsafe concepts. This paper identifies a relational gap: two individually benign objects or concepts can become harmful when linked by a specific action or relationship (e.g., child + drinking + wine). Standard unlearning approaches that target isolated concepts would either miss such combinations or over-suppress benign uses of the same objects in safe relationships. The proposed method uses object-relation-object tuples as the granular safety unit, applying parameter-efficient LoRA modifications to suppress harmful relational combinations without affecting legitimate uses of the component concepts. CLIP-based semantic validation ensures that suppressed relationships are contextually consistent, and robustness testing covers paraphrase variations, contextual shifts, and out-of-distribution images. This relational framing opens a new axis for safety evaluation: models should be probed not just for unsafe concepts in isolation, but for unsafe concept combinations.

### Key Takeaways
- Relational safety is a distinct problem from concept-level safety: harmful combinations of benign concepts require tuple-level rather than token-level suppression.
- LoRA-based targeted unlearning enables precise relationship removal without collateral damage to benign uses of the same objects.
- Safety red-teaming should explicitly test relational concept combinations, not just individual unsafe content categories.

---

## 11. LLM-MINE: Large Language Model Based Alzheimer's Disease and Related Dementias Phenotypes Mining from Clinical Notes

**Authors:** Mingchen Shao, Yuzhang Xie, Carl Yang, Jiaying Lu
**Link:** [LLM-MINE](https://arxiv.org/abs/2603.13673)
**Tags:** cs.AI, cs.LG

### Summary
Electronic health records contain rich unstructured clinical narrative that is largely inaccessible to automated analysis: symptoms described in prose, physician observations embedded in notes, and disease staging communicated through clinical language rather than structured fields. LLM-MINE addresses this by providing a pipeline for systematically extracting Alzheimer's Disease and Related Dementias (ADRD) phenotypes from clinical notes. Using expert-defined phenotype lists as anchors, the framework applies LLMs to extract relevant signals and validates extracted phenotypes through statistical analysis and downstream disease staging applications. The key finding is that few-shot prompting outperforms existing baseline extraction methods on clustering tasks, and that memory impairment emerges as the strongest discriminating phenotype for disease staging. The system demonstrates that LLM-based clinical NLP can surface clinically actionable signals from notes that structured EHR fields miss entirely, with implications for early detection, cohort selection for clinical trials, and population-level ADRD research.

### Key Takeaways
- Few-shot LLM extraction from unstructured clinical notes outperforms existing structured-extraction baselines for ADRD phenotype mining.
- Memory impairment is the strongest discriminating phenotype for disease staging — a finding that could inform automated screening triage.
- The approach generalizes to other neurodegenerative conditions with similar documentation patterns in EHR systems.

---

## 12. Human Attribution of Causality to AI Across Agency, Misuse, and Misalignment

**Authors:** Maria Victoria Carro, David Lagnado
**Link:** [Human Attribution of Causality to AI](https://arxiv.org/abs/2603.13236)
**Tags:** cs.AI, cs.CY

### Summary
As AI systems become more autonomous, questions of legal and moral responsibility become pressing and practically contentious: when an AI causes harm, who is responsible — the user who deployed it, the developer who built it, or the AI itself? This paper investigates folk intuitions about causal responsibility through human experiments involving AI-mediated harm scenarios, examining how AI agency level, structural position in the causal chain, misuse (deliberate human exploitation) vs. misalignment (AI behavioral failure), and developer involvement affect responsibility attribution. Key findings: AI agency level significantly shifts causal attribution toward the system as autonomy increases; however, when roles are reversed, participants consistently judge the human actor as more causal even when both agents perform identical actions — suggesting a persistent human-agency bias in responsibility attribution. Decomposing AI into component parts (model, deployment layer, interface) also affects causal judgments in non-obvious ways. These findings have direct implications for AI liability frameworks, regulatory design, and the way AI developers communicate system capabilities and limitations to set appropriate public expectations.

### Key Takeaways
- Public attribution of AI liability is highly sensitive to perceived agency level — more autonomous AI systems attract significantly more causal blame when harms occur.
- A persistent human-agency bias means courts and regulators applying folk intuitions may systematically under-attribute AI causation even in high-autonomy deployments.
- The misuse vs. misalignment distinction shapes responsibility attribution, suggesting governance frameworks should treat these as distinct liability categories.

---
