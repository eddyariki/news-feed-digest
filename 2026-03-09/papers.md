# Research Paper Summaries — 2026-03-09

Papers selected from today's digest for in-depth review.

---

## 1. The World Won't Stay Still: Programmable Evolution for Agent Benchmarks

**Authors:** Guangrui Li, Yaochen Xie, Yi Liu, Ziwei Dong, Xingyuan Pan, Tianqi Zheng, Jason Choi, Michael J. Morais, Binit Jha, Shaunak Mishra, Bingrou Zhou, Chen Luo, Monica Xiao Cheng, Dawn Song
**Link:** [The World Won't Stay Still: Programmable Evolution for Agent Benchmarks](https://arxiv.org/abs/2603.05910)
**Tags:** cs.AI

### Summary
Most agent benchmarks evaluate LLM-powered agents against static environments with fixed schemas, toolsets, and data — a setup that fundamentally misrepresents the real world, which continuously changes its APIs, databases, and available capabilities. Models trained and tested on frozen environments can overfit to those conditions, producing inflated benchmark scores that don't predict robustness in deployment. This paper addresses that gap with ProEvolve, a graph-based framework that makes environment evolution programmable and reproducible.

At the core of ProEvolve is a typed relational graph that provides a unified representation of the environment: data nodes, tool nodes, and schema relationships are all encoded in the same structure. Crucially, environment changes — adding a new API endpoint, deprecating a data field, modifying a tool's input contract — are expressed as well-defined graph transformations that propagate updates coherently across all dependent components. This makes evolution deterministic and auditable rather than ad hoc.

ProEvolve supports two key operations: (1) programming evolutionary dynamics as sequences of graph transformations to automatically generate new environment variants, and (2) instantiating isolated task sandboxes via subgraph sampling, enabling controlled experiments at scale. The authors validate ProEvolve by evolving a single environment into 200 distinct variants and generating 3,000 task sandboxes, then benchmarking representative agents across this suite. Results show meaningful variance in agent performance across evolved environments — variance that static benchmarks would entirely miss.

The key implication is methodological: if environments don't evolve, benchmark scores measure memorization of world-state snapshots rather than adaptive reasoning. ProEvolve provides the infrastructure to close this gap.

### Key Takeaways
- Static agent benchmarks systematically overestimate robustness by testing agents against frozen world-states that never change schema, tooling, or data.
- ProEvolve encodes environments as typed relational graphs where evolution is expressed as graph transformations, enabling programmatic, reproducible benchmark generation at scale.
- A single seed environment can be expanded into hundreds of evolved variants and thousands of sandboxed tasks, revealing agent performance variance invisible in static evaluations.

---

## 2. DeepFact: Co-Evolving Benchmarks and Agents for Deep Research Factuality

**Authors:** Yukun Huang, Leonardo F. R. Ribeiro, Momchil Hardalov, Bhuwan Dhingra, Markus Dreyer, Venkatesh Saligrama
**Link:** [DeepFact: Co-Evolving Benchmarks and Agents for Deep Research Factuality](https://arxiv.org/abs/2603.05912)
**Tags:** cs.AI

### Summary
Search-augmented LLM agents can produce sophisticated deep research reports (DRRs) spanning many claims across diverse domains, but verifying factuality at the claim level remains unsolved. Existing fact-checkers are designed for short, factoid-style claims in general domains, and it is unclear whether they transfer to the nuanced, long-form claims in DRRs. Worse, building a benchmark to test this transfer is itself difficult: the paper reveals that even PhD-level domain specialists achieve only 60.8% accuracy on a hidden micro-gold set of verifiable claims when working unassisted — a surprisingly low ceiling that exposes how brittle expert-labeled static benchmarks are in this setting.

The core insight is that experts are substantially more reliable as auditors in dispute processes than as one-shot labelers. This motivates Evolving Benchmarking via Audit-then-Score (AtS), a protocol where benchmark labels are explicitly revisable. When a verifier disagrees with the current benchmark label, it must submit supporting evidence; an auditor then adjudicates the dispute, and accepted revisions update the benchmark before any model is scored. Running four rounds of AtS raises expert micro-gold accuracy from 60.8% to 90.9%, demonstrating the protocol's effectiveness.

The system is instantiated as DeepFact-Bench (a versioned, auditable DRR factuality benchmark) and DeepFact-Eval (a document-level verification agent with a lightweight grouped variant). DeepFact-Eval outperforms existing verifiers on DeepFact-Bench and transfers well to external factuality datasets.

The key limitation of static benchmarks is structural: labeling is too hard and too contested for one-shot human annotation to be reliable. Co-evolution between the benchmark and the verifier is required.

### Key Takeaways
- PhD-level specialists achieve only 60.8% one-shot accuracy labeling verifiable claims in deep research reports, undermining the reliability of static expert-labeled benchmarks.
- The Audit-then-Score protocol converts experts from labelers to auditors and allows benchmark labels to evolve through evidence-based dispute resolution, raising accuracy to 90.9% after four rounds.
- DeepFact-Bench and DeepFact-Eval provide the first versioned, auditable infrastructure for testing factuality verification on long-form AI-generated research content.

---

## 3. Depth Charge: Jailbreak Large Language Models from Deep Safety Attention Heads

**Authors:** Jinman Wu, Yi Xie, Shiqian Zhao, Xiaofeng Chen
**Link:** [Depth Charge: Jailbreak Large Language Models from Deep Safety Attention Heads](https://arxiv.org/abs/2603.05772)
**Tags:** cs.CR; cs.AI

### Summary
Most existing jailbreak attacks on open-source LLMs operate at shallow levels — crafting adversarial prompts or perturbing token embeddings — and most defenses are calibrated to block attacks at those same levels. This creates a false sense of security: if the real vulnerability lies deeper in the model's computation, surface-level defenses may report success while leaving the underlying weakness unexploited. This paper demonstrates exactly that gap with SAHA (Safety Attention Head Attack), an attention-head-level jailbreak framework.

SAHA is built on a key empirical finding: deeper attention layers introduce more vulnerability to jailbreak attacks than shallow ones. The safety circuitry that alignment training installs in early layers is insufficiently reinforced in deeper layers, leaving deeper attention heads as an attack surface. To exploit this, SAHA introduces Ablation-Impact Ranking, a head selection strategy that identifies the most safety-critical attention head in the deepest vulnerable layer by measuring the impact of ablating each head on unsafe output generation.

Having identified the target, SAHA applies Layer-Wise Perturbation — a boundary-aware method that probes for unsafe outputs with minimal perturbation to the attention weights. The constraint on perturbation magnitude is deliberate: it preserves semantic relevance to the target intent while keeping the modified weights close enough to the original to evade detection. Extensive experiments show SAHA improves attack success rate (ASR) by 14% over state-of-the-art baselines.

The implication for defenders is significant: safety evaluations that only probe prompt-level and embedding-level attacks may miss a broad class of deeper vulnerabilities that existing alignment techniques leave unaddressed.

### Key Takeaways
- Alignment training leaves deeper attention heads insufficiently protected, creating a jailbreak attack surface that prompt-level and embedding-level defenses do not cover.
- SAHA uses Ablation-Impact Ranking to locate the most vulnerable deep attention head, then applies constrained Layer-Wise Perturbation to generate unsafe outputs with high semantic fidelity.
- SAHA achieves 14% higher attack success rate than state-of-the-art baselines, demonstrating that existing defenses provide incomplete protection against deeper-layer attacks.

---

## 4. Knowing without Acting: The Disentangled Geometry of Safety Mechanisms in Large Language Models

**Authors:** Jinman Wu, Yi Xie, Shen Lin, Shiqian Zhao, Xiaofeng Chen
**Link:** [Knowing without Acting: The Disentangled Geometry of Safety Mechanisms in Large Language Models](https://arxiv.org/abs/2603.05773)
**Tags:** cs.CR; cs.AI; cs.LG

### Summary
Safety alignment is typically modeled as a unified process: the model detects harmfulness and automatically refuses. But the persistence of jailbreaks even against well-aligned models suggests this monolithic view is wrong. If detecting harm and refusing harm were inseparable, successfully bypassing refusal would require fooling detection — yet many jailbreaks succeed without appearing to confuse the model about whether content is harmful. This paper proposes the Disentangled Safety Hypothesis (DSH) to explain this dissociation.

DSH posits that safety computation operates on two structurally distinct subspaces: a Recognition Axis (v_H, "Knowing") tracking harmfulness, and an Execution Axis (v_R, "Acting") driving refusal. Geometric analysis of activation space across model layers reveals a universal "Reflex-to-Dissociation" evolution: in early layers these signals are antagonistically entangled, but in deeper layers they become structurally independent. This architecture means a model can correctly recognize harmful content on the Recognition Axis while failing to activate refusal on the Execution Axis.

To validate the hypothesis causally, the authors introduce Double-Difference Extraction (to isolate each axis) and Adaptive Causal Steering (to manipulate them independently). Using a curated AmbiguityBench dataset, they demonstrate causal double dissociation — the "Knowing without Acting" state. They then leverage this disentanglement to build the Refusal Erasure Attack (REA), which surgically targets the Execution Axis to achieve state-of-the-art attack success rates while leaving harmfulness recognition intact.

The paper also identifies an important architectural difference: Llama 3.1 uses explicit semantic control (localizable safety representations), while Qwen 2.5 uses latent distributed control, implying different vulnerabilities and defenses for different model families.

### Key Takeaways
- The Disentangled Safety Hypothesis identifies two independent neural subspaces — harmfulness recognition and refusal execution — explaining why models can "know" content is harmful without refusing it.
- Geometric analysis reveals a universal Reflex-to-Dissociation pattern across model layers, where safety signals transition from entangled to structurally independent at depth.
- The resulting Refusal Erasure Attack surgically targets only the refusal axis, achieving state-of-the-art jailbreak rates while leaving harmfulness recognition undisturbed.

---

## 5. BlackMirror: Black-Box Backdoor Detection for Text-to-Image Models via Instruction-Response Deviation

**Authors:** Feiran Li, Qianqian Xu, Shilong Bao, Zhiyong Yang, Xilin Zhao, Xiaochun Cao, Qingming Huang
**Link:** [BlackMirror: Black-Box Backdoor Detection for Text-to-Image Models](https://arxiv.org/abs/2603.05921)
**Tags:** cs.CV; cs.AI

### Summary
Backdoored text-to-image models respond to a specific trigger pattern (a word or phrase embedded in the prompt) by generating adversarially controlled content — a serious security concern for Model-as-a-Service deployments where users cannot inspect model weights. Existing detection methods typically look for image-level visual similarity: the assumption is that backdoor-triggered outputs will be conspicuously consistent across prompts containing the trigger. But newer backdoor attacks deliberately introduce visual diversity in triggered outputs, defeating similarity-based detectors.

BlackMirror is motivated by a more robust observation: across attack types, only partial semantic patterns within the generated image are steadily manipulated by the backdoor, while the rest of the image content varies naturally. The attack signature is in the persistent deviation between specific instruction semantics and corresponding image regions — not in global visual consistency.

BlackMirror operationalizes this through two components. MirrorMatch aligns visual patterns with corresponding prompt instructions to detect semantic deviations — regions where what the image shows doesn't match what the prompt says it should. MirrorVerify then tests whether those detected deviations are stable across varied prompts (with and without the suspected trigger), distinguishing true backdoor behavior from benign generation noise.

The framework is training-free and model-agnostic, deployable as a plug-and-play module without white-box access to the model. Comprehensive experiments demonstrate accurate detection across a wide range of attack types, including those that evade image-similarity baselines.

The key limitation is that the framework relies on accurate semantic alignment between instructions and image regions, which may degrade for very abstract or stylistic prompts where such alignment is inherently loose.

### Key Takeaways
- Modern backdoor attacks on text-to-image models produce visually diverse outputs that evade image-similarity-based detectors, requiring a fundamentally different detection signal.
- BlackMirror detects backdoors by measuring semantic deviations between prompt instructions and corresponding image regions, a signal that persists even when triggered outputs look visually varied.
- The framework is training-free and black-box, making it directly deployable in MaaS settings without model access.

---

## 6. SecureRAG-RTL: A Retrieval-Augmented, Multi-Agent, Zero-Shot LLM-Driven Framework for Hardware Vulnerability Detection

**Authors:** Touseef Hasan, Blessing Airehenbuwa, Nitin Pundir, Souvika Sarkar, Ujjwal Guin
**Link:** [SecureRAG-RTL: A Retrieval-Augmented, Multi-Agent, Zero-Shot LLM-Driven Framework for Hardware Vulnerability Detection](https://arxiv.org/abs/2603.05689)
**Tags:** cs.CR; cs.AI

### Summary
Hardware security verification — detecting vulnerabilities in register-transfer level (RTL) designs written in hardware description languages (HDL) like Verilog or VHDL — is a domain where LLMs are largely untested. The fundamental obstacle is data scarcity: unlike software security, there are very few publicly available labeled HDL datasets with known vulnerabilities, which leaves LLMs without the in-context or fine-tuning examples needed to apply their general reasoning capabilities to hardware-specific vulnerability patterns.

SecureRAG-RTL addresses this via Retrieval-Augmented Generation (RAG). Rather than relying solely on the LLM's parametric knowledge, the framework retrieves domain-specific HDL security knowledge at inference time, injecting relevant vulnerability patterns, CWEs, and design examples into the context. This allows the model to reason about hardware vulnerabilities it was not directly trained on. The framework also employs a multi-agent architecture where specialized agents collaborate across detection subtasks, enabling zero-shot generalization across LLM architectures of varying sizes.

The authors establish prompt-only baselines and demonstrate that SecureRAG-RTL achieves approximately 30% improvement in detection accuracy over those baselines across diverse LLM architectures — importantly, regardless of model size, suggesting the gains come from domain knowledge injection rather than model capacity alone. To support future research, the team curated and annotated a benchmark dataset of 14 HDL designs containing real-world security vulnerabilities, which they will release publicly.

The main limitation is the small benchmark size (14 designs); broader validation across more diverse hardware designs and vulnerability classes would strengthen generalization claims.

### Key Takeaways
- LLM performance on hardware vulnerability detection is severely limited by the scarcity of labeled HDL security datasets; RAG-based domain knowledge injection offers a practical bypass.
- SecureRAG-RTL achieves ~30% improvement in detection accuracy over prompt-only baselines across diverse LLM architectures, independent of model size.
- The paper introduces and will publicly release a curated benchmark of 14 HDL designs with annotated real-world vulnerabilities, a needed resource for the hardware security community.

---

## 7. The DSA's Blind Spot: Algorithmic Audit of Advertising and Minor Profiling on TikTok

**Authors:** Sara Solarova, Matej Mosnar, Matus Tibensky, Jan Jakubcik, Adrian Bindas, Simon Liska, Filip Hossner, Matúš Mesarčík, Ivan Srba
**Link:** [The DSA's Blind Spot: Algorithmic Audit of Advertising and Minor Profiling on TikTok](https://arxiv.org/abs/2603.05653)
**Tags:** cs.CY; cs.AI; cs.IR; cs.SI

### Summary
Article 28(2) of the EU's Digital Services Act (DSA) prohibits profiling-based advertising to minors, aiming to protect adolescents whose still-developing cognitive capacities leave them particularly vulnerable to commercial persuasion. This paper presents the first empirical audit of how this prohibition functions in practice on TikTok — and finds a critical regulatory loophole.

The DSA's definition of "advertisement" is narrow, covering only formal, disclosed commercial content. It excludes influencer marketing, undisclosed brand partnerships, and native promotional content — formats that serve functionally identical commercial purposes but operate outside the legal definition. The audit deploys sock-puppet accounts simulating pairs of minor and adult users with distinct interest profiles, with content automatically annotated across four categories: formal advertisements, disclosed ads, undisclosed ads, and non-commercial content.

The findings reveal a stark paradox: TikTok formally complies with Article 28(2) by shielding minors from profiled formal advertisements. But both disclosed and undisclosed commercial content exhibits profiling 5–8 times stronger than formal advertising to adults. The strongest profiling occurs in undisclosed commercial content — branded content or paid partnerships that creators fail to label, which the platform neither flags nor prevents from being personalized to minors.

The regulatory gap is structural: compliance is achievable by shifting commercial influence from the regulated channel (formal ads) to unregulated channels (influencer and native content), which may be more effective at persuasion precisely because they lack disclosure. The authors argue for expanding Article 28(2) to cover all functionally commercial content regardless of format.

### Key Takeaways
- The DSA's narrow definition of "advertisement" creates a compliance loophole: TikTok blocks profiled formal ads to minors while delivering profiled influencer and undisclosed commercial content 5–8 times more intensely than formal adult advertising.
- Profiling in undisclosed commercial content is the strongest detected, occurring without creator labeling, platform correction, or protection for minor users.
- Effective minor protection requires a functional definition of advertisement covering all commercial content, not only content that self-identifies as advertising.

---

## 8. Ambiguity Collapse by LLMs: A Taxonomy of Epistemic Risks

**Authors:** Shira Gur-Arieh, Angelina Wang, Sina Fazelpour
**Link:** [Ambiguity Collapse by LLMs: A Taxonomy of Epistemic Risks](https://arxiv.org/abs/2603.05801)
**Tags:** cs.CY; cs.AI

### Summary
Many of the most consequential uses of LLMs involve interpreting terms that are genuinely contested — "hate speech," "incitement," "qualified," "biased," "legitimate." These terms are open-textured: they admit multiple defensible interpretations, and their meaning is ordinarily negotiated through social, legal, and institutional deliberation. When LLMs are deployed to classify content or rank people based on such terms, they produce singular resolutions — forcing a specific interpretation without acknowledgment of the underlying contestation. This paper calls that phenomenon ambiguity collapse and develops a taxonomy of its epistemic risks.

The authors draw on interdisciplinary accounts of ambiguity as a productive epistemic resource — a feature, not a bug, of how contested concepts evolve — to analyze risks at three levels. At the process level, ambiguity collapse forecloses opportunities for deliberation, the development of interpretive skills, and stakeholder participation in shaping contested norms. At the output level, it distorts the concepts and reasons that agents (human or AI) act upon by substituting contested judgments for apparently authoritative ones. At the ecosystem level, widespread LLM deployment homogenizes shared vocabularies and freezes interpretive norms at a moment in time — and shifts normative power to model developers, who embed specific resolutions in training without democratic accountability.

Three case studies illustrate these risks in content moderation, hiring, and AI self-regulation. The paper concludes with multi-layer mitigation principles covering training, deployment design, interface affordances, and handling of underspecified prompts — oriented toward systems that surface and preserve ambiguity rather than eliminate it.

### Key Takeaways
- Ambiguity collapse occurs when LLMs produce singular resolutions to genuinely contested concepts, bypassing the deliberative processes through which such concepts are ordinarily negotiated.
- Risks operate at three levels: foreclosing deliberation (process), distorting the concepts agents act upon (output), and homogenizing interpretive norms at scale while concentrating normative power in model developers (ecosystem).
- Mitigation requires designing systems that surface and preserve ambiguity rather than resolve it, spanning training choices, deployment contexts, and interface design.

---

## 9. SAHOO: Safeguarded Alignment for High-Order Optimization Objectives in Recursive Self-Improvement

**Authors:** Subramanyam Sahoo, Aman Chadha, Vinija Jain, Divya Chaudhary
**Link:** [SAHOO: Safeguarded Alignment for Recursive Self-Improvement](https://arxiv.org/abs/2603.06333)
**Tags:** cs.AI; cs.CL; cs.LG

### Summary
Recursive self-improvement — where AI systems critique, revise, and evaluate their own outputs across iterations — is moving from theoretical concern to practical reality. Modern systems already exhibit limited forms of this: multi-turn revision loops, self-critique pipelines, and iterative RL fine-tuning. But each improvement cycle introduces the risk of alignment drift: subtle shifts in the system's goals, constraints, or behavioral patterns that accumulate across iterations and may not be detected by standard evaluation until they compound into serious failures.

SAHOO (Safeguarded Alignment for High-Order Optimization Objectives) introduces a practical monitoring and control framework built on three mechanisms. The Goal Drift Index (GDI) is a learned multi-signal detector combining semantic, lexical, structural, and distributional measures to quantify how much a system's behavior has shifted from its aligned baseline. Constraint preservation checks enforce safety-critical invariants (syntactic correctness, non-hallucination) at each improvement cycle. Regression-risk quantification flags cycles where improvement on one dimension undoes prior gains on another, enabling early intervention before drift compounds.

Evaluated across 189 tasks in code generation, mathematical reasoning, and truthfulness, SAHOO achieves 18.3% improvement in code tasks and 16.8% in reasoning while maintaining constraint satisfaction in two domains and keeping violations low in truthfulness. The framework also maps a capability-alignment frontier, showing that early improvement cycles are efficient but later cycles carry rising alignment costs — a finding with direct implications for how many self-improvement steps are safe to run without intervention.

### Key Takeaways
- Recursive self-improvement systems risk subtle alignment drift across iterations; SAHOO provides the first practical framework to detect and constrain this drift during ongoing improvement.
- The Goal Drift Index combines semantic, lexical, structural, and distributional signals into a learned detector, enabling quantitative monitoring rather than subjective review.
- Early improvement cycles are efficient, but alignment costs rise in later cycles — suggesting that unconstrained long-horizon self-improvement is risky even when individual steps appear safe.

---

## 10. Reasoning Models Struggle to Control Their Chains of Thought

**Authors:** Chen Yueh-Han, Robert McCarthy, Bruce W. Lee, He He, Ian Kivlichan, Bowen Baker, Micah Carroll, Tomek Korbak
**Link:** [Reasoning Models Struggle to Control Their Chains of Thought](https://arxiv.org/abs/2603.05706)
**Tags:** cs.AI

### Summary
Chain-of-thought (CoT) monitoring — observing the intermediate reasoning steps that reasoning models verbalize before producing a final answer — is proposed as a safety tool: if a model is reasoning toward a harmful output, its CoT should reveal that reasoning in time to intervene. But this tool only works if models cannot strategically control what they verbalize in their CoT. If a model can reason one way internally while showing monitors something innocuous, CoT monitoring provides false safety assurance.

This paper introduces CoT-Control, an evaluation suite that directly measures CoT controllability — the ability to solve a problem while adhering to constraints on CoT content (e.g., reasoning about genetics without using the word "chromosome"). It also measures output controllability separately, enabling direct comparison. The finding is striking: reasoning models have dramatically lower CoT controllability than output controllability. Claude Sonnet 4.5, for instance, controls its CoT only 2.7% of the time but controls its final output 61.9% of the time.

CoT controllability decreases further with more RL training, more test-time compute, and increased problem difficulty — and is lower for smaller models. Even when models are given incentives (not just direct requests) to manipulate their CoT, or when adversarial prompt optimization is applied, controllability does not rise meaningfully. Interestingly, models exhibit slightly higher controllability when told they are being monitored, but the effect is small.

The results are cautiously optimistic: current models are unlikely to be strategically deceiving CoT monitors because they appear genuinely unable to control their CoT. But the mechanism behind this low controllability is not understood, and the paper recommends tracking it in future frontier models as capabilities scale.

### Key Takeaways
- Reasoning models have dramatically lower CoT controllability than output controllability: Claude Sonnet 4.5 controls its CoT only 2.7% of the time versus 61.9% for final outputs, suggesting CoT monitoring is currently hard for models to deceive.
- CoT controllability decreases with more RL training, test-time compute, and problem difficulty — all of which increase in more capable models — but the causal mechanism is not understood.
- CoT monitoring appears currently robust, but frontier labs should actively track CoT controllability as model capabilities scale to detect if and when this changes.

---

## 11. The Fragility of Moral Judgment in Large Language Models

**Authors:** Tom van Nuenen, Pratik S. Sachdeva
**Link:** [The Fragility of Moral Judgment in Large Language Models](https://arxiv.org/abs/2603.05651)
**Tags:** cs.CL; cs.AI; cs.HC

### Summary
People increasingly use LLMs for everyday moral guidance — asking them to evaluate interpersonal conflicts, assess culpability, and provide advice. This paper systematically tests whether LLM moral judgments are stable under surface-level perturbations that leave the underlying ethical conflict unchanged. Using 2,939 real moral dilemmas sourced from r/AmItheAsshole (January–March 2025), it generates three families of perturbations: surface edits (lexical and structural noise), point-of-view shifts (voice and stance neutralization), and persuasion cues (self-positioning, social proof, pattern admissions, victim framing). Evaluation protocols are also varied independently (output ordering, instruction placement, unstructured prompting).

The results expose significant instability. Surface edits produce low flip rates (7.5%), within the models' self-consistency noise floor. But point-of-view shifts — changing the narrative voice without changing the moral facts — produce 24.3% flip rates. A notable subset (37.9%) of dilemmas is robust to surface noise yet flips under perspective changes, indicating models treat narrative voice as a substantive moral cue rather than a presentation artifact. Morally ambiguous cases (where no clear party is at fault) are most susceptible to all perturbation types.

The most striking finding concerns evaluation protocols: agreement between structured protocols is only 67.6% (Cohen's kappa = 0.55), and only 35.7% of model-scenario pairs match across all three protocols. This means protocol choices dominate all other factors — including the perturbations themselves — as drivers of moral judgment variance. Four frontier models (GPT-4.1, Claude 3.7 Sonnet, DeepSeek V3, Qwen2.5-72B) were evaluated across 129,156 total judgments; instability is consistent across all.

### Key Takeaways
- LLM moral judgments are highly sensitive to point-of-view shifts (24.3% flip rate) even when the underlying ethical conflict is unchanged, indicating models use narrative voice as a proxy for moral weight.
- Evaluation protocol choices dominate all other sources of variance: only 35.7% of model-scenario units produce consistent judgments across all three tested protocols.
- The fragility is concentrated in morally ambiguous cases and is consistent across four frontier models, undermining the reliability of LLMs for content moderation or moral guidance at scale.

---

## 12. Proof-of-Guardrail in AI Agents and What (Not) to Trust from It

**Authors:** Xisen Jin, Michael Duan, Qin Lin, Aaron Chan, Zhenglun Chen, Junyi Du, Xiang Ren
**Link:** [Proof-of-Guardrail in AI Agents and What (Not) to Trust from It](https://arxiv.org/abs/2603.05786)
**Tags:** cs.CR; cs.AI; cs.CL

### Summary
As AI agents are deployed as online services, users must trust developer claims about safety enforcement — but those claims are unverifiable. A developer can assert that responses are filtered through a specific safety guardrail without any mechanism for users to confirm this. This creates an adversarial surface: safety measures can be falsely advertised, misconfigured, or selectively applied. This paper introduces proof-of-guardrail, a cryptographic system that makes safety claims verifiable.

The core mechanism uses a Trusted Execution Environment (TEE) — a hardware-secured computation environment that guarantees code integrity. The developer runs both the AI agent and the specified guardrail inside the TEE. After execution, the TEE produces a signed attestation confirming that the guardrail code was executed on the response. This attestation is verifiable by any user offline, without requiring trust in the developer or access to the agent's internals. The scheme keeps the developer's proprietary agent private while proving the guardrail was applied.

The authors implement proof-of-guardrail for OpenClaw agents and measure latency overhead and deployment cost to assess practical feasibility. The system is positioned as infrastructure for verifiable safety claims in regulated or high-stakes deployments.

Crucially, the paper also carefully delineates what proof-of-guardrail does not guarantee. It proves that a specific guardrail was applied — not that the guardrail is effective. Malicious developers could jailbreak the guardrail itself before applying it, or apply a guardrail that appears legitimate while being intentionally weakened. The contribution is a foundation for verifiable safety claims, not a complete solution to AI safety.

### Key Takeaways
- Proof-of-guardrail uses Trusted Execution Environments to generate cryptographic attestations that a specific open-source guardrail was applied to an AI response, enabling offline user verification without trusting the developer.
- The scheme preserves developer privacy (proprietary agent internals remain hidden) while proving guardrail execution — a practical balance for commercial deployment.
- The system proves guardrail application, not guardrail effectiveness; adversarial developers could still apply a compromised or jailbroken guardrail, requiring additional trust in guardrail code quality and provenance.

---
