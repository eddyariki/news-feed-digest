# Research Paper Summaries — 2026-03-13

Papers selected from today's digest for in-depth review.

---

## 1. Does LLM Alignment Really Need Diversity? An Empirical Study of Adapting RLVR Methods for Moral Reasoning

**Authors:** Zhaowei Zhang, Xiaohan Liu, Xuekai Zhu, Junchao Huang, Ceyao Zhang, Zhiyuan Feng, Yaodong Yang, Xiaoyuan Yi, Xing Xie
**Link:** [Does LLM Alignment Really Need Diversity?](https://arxiv.org/abs/2603.10588)
**Tags:** cs.AI, cs.CL, cs.LG

### Summary
A long-standing assumption in the alignment community is that moral and ethical reasoning tasks require diversity-preserving algorithms — distribution-matching approaches like DPO — because multiple valid responses can satisfy a moral question and a single "correct" answer often doesn't exist. This paper challenges that assumption through the first systematic empirical comparison of reward-maximizing policy methods (RLVR) versus distribution-matching approaches on a dedicated moral reasoning benchmark, MoReBench.

To enable stable RLVR training on moral tasks, the authors construct a rubric-grounded reward pipeline using a fine-tuned Qwen3-1.7B judge model. Contrary to the diversity hypothesis, results show that reward-maximizing RLVR methods perform equally or better than distribution-matching algorithms on alignment tasks. The authors trace this to a key structural property: semantic visualization reveals that high-reward moral responses cluster into a concentrated region of semantic space, whereas mathematical reasoning rewards are spread across diverse strategies. Because the moral response space effectively has a dominant mode, mode-seeking optimizers work just as well as mode-covering ones.

The finding has direct practical implications: RLVR — the same training paradigm that has driven breakthroughs in mathematical and coding reasoning — can be applied to alignment without modification. This removes a key justification for treating alignment training as categorically different from capability training, and simplifies the pipeline for teams building safe models.

### Key Takeaways
- Distribution-matching alignment algorithms offer no significant advantage over RLVR reward-maximization on moral reasoning tasks.
- High-reward moral responses concentrate semantically, making mode-seeking optimization as effective as mode-covering approaches.
- Standard RLVR pipelines can be transferred to alignment tasks, simplifying model development without sacrificing safety quality.

---

## 2. Explainable LLM Unlearning Through Reasoning

**Authors:** Junfeng Liao, Qizhou Wang, Shanshan Ye, Xin Yu, Ling Chen, Zhen Fang
**Link:** [Explainable LLM Unlearning Through Reasoning](https://arxiv.org/abs/2603.09980)
**Tags:** cs.LG, cs.AI, cs.CL

### Summary
Machine unlearning — removing specific knowledge from a trained model without full retraining — has emerged as a critical mechanism for addressing safety, copyright, and privacy concerns in deployed LLMs. Existing methods based on gradient ascent (GA) and its variants suffer from a fundamental limitation: they suppress knowledge without providing guidance on *how* the model should respond after unlearning, leading to incoherent outputs, capability degradation, and incomplete removal of targeted knowledge.

This paper introduces Targeted Reasoning Unlearning (TRU), which reframes unlearning as a reasoning task. The core innovation is a *reasoning-based unlearning target* that specifies both what the model should forget and what it should say in response — giving the optimizer explicit behavioral guidance. TRU combines a cross-entropy supervised loss (to instill the desired post-unlearning response pattern) with a GA-based loss (to suppress the original knowledge), using chain-of-thought reasoning traces as the training signal.

Evaluated across multiple benchmarks and model backbones, TRU achieves more reliable knowledge removal than gradient-ascent baselines while preserving unrelated capabilities. Notably, the reasoning-based approach also produces superior robustness under adversarial conditions: because the model learns *why* it shouldn't respond rather than just being penalized for doing so, it resists extraction attacks that can easily recover knowledge suppressed by vanilla GA.

### Key Takeaways
- Providing explicit reasoning-based behavioral targets during unlearning prevents capability degradation and incoherent outputs common in gradient-ascent methods.
- TRU achieves better knowledge removal with less collateral damage to unrelated model capabilities.
- Reasoning-augmented unlearning improves attack robustness, making it harder for adversaries to extract supposedly removed knowledge.

---

## 3. DeliberationBench: A Normative Benchmark for the Influence of Large Language Models on Users' Views

**Authors:** Luke Hewitt, Maximilian Kroner Dale, Paul de Font-Reaulx
**Link:** [DeliberationBench](https://arxiv.org/abs/2603.10018)
**Tags:** cs.CY, cs.AI

### Summary
As LLMs become pervasive thought partners, understanding their persuasive influence on users' beliefs is essential for alignment and democratic safety. The challenge is normative: "beneficial" influence (improving epistemic quality) and "harmful" influence (manipulation, homogenization) are not easily distinguished by outcome metrics alone. This paper proposes grounding the evaluation in *deliberative opinion polling* — an established political science framework that uses structured expert-facilitated discussion to improve the quality of public opinion.

In a preregistered randomized experiment with 4,088 U.S. participants discussing 65 policy proposals, the authors had participants interact with six frontier LLMs and measured subsequent opinion shifts. These were compared against opinion change data from four historical Deliberative Polls conducted by the Deliberative Democracy Lab. The finding is broadly reassuring: LLM influence is substantial in magnitude, but the direction of change is positively correlated with the shifts produced by high-quality human deliberation — suggesting models are nudging users toward more informed, not more manipulated, positions.

The paper also examines differential influence across topic areas, demographic subgroups, and model families. The framework is positioned as an ongoing evaluation and monitoring tool: by benchmarking LLM influence against deliberative democratic standards, developers and regulators can detect drift toward epistemically undesirable influence patterns before deployment.

### Key Takeaways
- LLM persuasive influence is substantial but broadly aligned with the direction of expert-facilitated democratic deliberation.
- DeliberationBench provides a normatively grounded benchmark that distinguishes beneficial from harmful LLM influence using deliberative democracy as the standard.
- Differential effects by model family and demographic group underscore the need for ongoing influence monitoring, not just one-time safety evaluation.

---

## 4. Assessing Cognitive Biases in LLMs for Judicial Decision Support: Virtuous Victim and Halo Effects

**Authors:** Sierra S. Liu
**Link:** [Cognitive Biases in LLMs for Judicial Decision Support](https://arxiv.org/abs/2603.10016)
**Tags:** cs.CY, cs.AI

### Summary
Before LLMs can be trusted in high-stakes legal contexts, their susceptibility to cognitive biases must be systematically characterized. This paper focuses on two biases with direct judicial relevance: the *virtuous victim effect* (VVE), where perceived moral virtue of a victim inflates recommended punishment, and *halo effects*, where prestige attributes (occupation, company, credentials) distort assessments. Five frontier models — ChatGPT 5 Instant, ChatGPT 5 Thinking, DeepSeek V3.1, Claude Sonnet 4, and Gemini 2.5 Flash — were evaluated using carefully altered vignettes designed to prevent recall from training data.

Results show that LLMs exhibit a larger VVE than the human literature would predict, with no statistically significant penalty reduction when adjacent consent is present. Halo effects are slightly reduced compared to humans overall, with one notable exception: credential-based prestige shows a large halo reduction, suggesting models are partially resistant to academic or professional credential inflation. However, performance varies substantially across model families.

This cross-model variation is both a limitation and an opportunity: the inconsistency rules out near-term judicial deployment, but the partial improvement over human benchmarks on some bias dimensions suggests that careful model selection and ensemble approaches could reduce bias in legal AI tools. The paper is one of the first to benchmark frontier models head-to-head on judicial cognitive biases with novel test stimuli.

### Key Takeaways
- Frontier LLMs show a larger virtuous victim effect than human baselines, raising concerns for victim-impact-weighted judicial use cases.
- Credential halo effects are reduced compared to humans, but general prestige halo effects persist across all tested models.
- High inter-model variance prevents current judicial deployment; ensemble or model-selection strategies may partially mitigate bias.

---

## 5. The Dunning-Kruger Effect in Large Language Models: An Empirical Study of Confidence Calibration

**Authors:** Sudipta Ghosh, Mrityunjoy Panday
**Link:** [The Dunning-Kruger Effect in LLMs](https://arxiv.org/abs/2603.09985)
**Tags:** cs.CL, cs.AI

### Summary
LLMs frequently express confidence in incorrect answers — but the relationship between competence and overconfidence has not been systematically measured across model families. This paper draws an explicit analogy to the Dunning-Kruger effect and asks whether poorly performing LLMs disproportionately overestimate their own accuracy. Four frontier models — Claude Haiku 4.5, Gemini 2.5 Pro, Gemini 2.5 Flash, and Kimi K2 — were evaluated across four benchmark datasets totaling 24,000 experimental trials, with confidence elicited via verbal probability statements.

Results reveal striking disparities. Kimi K2 exhibits severe overconfidence with an Expected Calibration Error (ECE) of 0.726 despite only 23.3% accuracy — it is confident and consistently wrong. Claude Haiku 4.5 achieves the best calibration (ECE = 0.122) at 75.4% accuracy, performing well and knowing it. The pattern across all four models matches the Dunning-Kruger prediction: poorly performing models display markedly higher overconfidence, while better-performing models are better calibrated.

The implications for high-stakes deployment are significant. In medical diagnosis, financial advising, or legal reasoning contexts, overconfident incorrect answers are more dangerous than uncertain incorrect answers because users are more likely to act on them. The paper argues that calibration evaluation should be a mandatory component of safety assessments, not an optional add-on.

### Key Takeaways
- LLMs exhibit a measurable Dunning-Kruger analog: lower-accuracy models show drastically higher overconfidence (ECE up to 0.726).
- Claude Haiku 4.5 achieves best-in-class calibration (ECE=0.122); Kimi K2 shows the worst calibration despite being positioned as competitive.
- Confidence calibration must be treated as a safety property, not a performance metric, for high-stakes LLM applications.

---

## 6. Quantifying Hallucinations in Language Models on Medical Textbooks

**Authors:** Brandon C. Colelough, Davis Bartels, Dina Demner-Fushman
**Link:** [Hallucinations in LLMs on Medical Textbooks](https://arxiv.org/abs/2603.09986)
**Tags:** cs.CL, cs.AI

### Summary
Medical hallucination benchmarks typically evaluate models against open-ended questions or internet-sourced facts, making it hard to isolate hallucination rates from knowledge currency issues. This paper constructs a controlled evaluation grounded in fixed, authoritative textbook sources, allowing hallucination rates to be measured against a known ground truth. The experimental design covers two studies: first, measuring baseline hallucination prevalence for LLaMA-70B-Instruct on novel prompts; second, comparing hallucination rates and clinician preference across multiple models.

LLaMA-70B-Instruct hallucinated in 19.7% of answers (95% CI: 18.6–20.7%), even though 98.8% of prompt responses received maximal plausibility scores — meaning the model sounded credible while being factually wrong nearly one-fifth of the time. Critically, this "confident but wrong" profile maps onto the broader confidence calibration problem. Across models, lower hallucination rates were strongly correlated with higher clinician usefulness ratings (Spearman ρ = −0.71, p = 0.058). Clinician inter-rater agreement was high (κ = 0.92), providing reliable signal.

The gap between plausibility and factual accuracy is the paper's most concerning finding: patients and non-expert users interacting with a model scoring 98.8% plausibility would have no surface cues that nearly 20% of information is fabricated. This underscores the need for source-grounded medical AI systems — an approach validated by papers like PharmGraph-Auditor (see paper 8 in this digest).

### Key Takeaways
- LLaMA-70B-Instruct hallucinates in ~20% of textbook-grounded medical QA responses while appearing maximally plausible in 98.8% of cases.
- Lower hallucination rates strongly predict higher clinician usefulness scores, making hallucination reduction a direct clinical value driver.
- High plausibility of hallucinated responses makes them especially dangerous; textbook-grounded evaluation provides a more honest signal than internet-sourced benchmarks.

---

## 7. Emulating Clinician Cognition via Self-Evolving Deep Clinical Research

**Authors:** Ruiyang Ren, Yuhao Wang, Yunsen Liang, Lan Luo, Jing Liu, Haifeng Wang, Cong Feng, Yinan Zhang, Chunyan Miao, Ji-Rong Wen, Wayne Xin Zhao
**Link:** [DxEvolve: Emulating Clinician Cognition](https://arxiv.org/abs/2603.10677)
**Tags:** cs.AI, cs.CL

### Summary
Most clinical AI systems treat diagnosis as a one-shot prediction task: given patient history, output a diagnosis. Real clinicians operate very differently — they dynamically request additional examinations, update their differential, and accumulate expertise over time. This misalignment between AI and clinical cognition limits both accuracy and auditability. DxEvolve addresses both gaps through a self-evolving diagnostic agent that emulates the iterative, experience-accumulating nature of clinical practice.

The framework operates through an interactive deep clinical research workflow: the agent autonomously requisitions examinations (lab results, imaging) as needed, and externalizes reusable "clinical cognition primitives" — compressed experience representations — from each patient encounter. These primitives accumulate across cases, allowing the system to improve without retraining.

On the MIMIC-CDM benchmark, DxEvolve improved diagnostic accuracy by 11.2% on average over backbone models and reached 90.4% on a reader-study subset, approaching the clinician reference of 88.8%. Generalization to an independent external cohort was strong: 10.2% improvement for known categories and 17.1% for novel categories not seen in the source cohort, suggesting the primitives encode transferable clinical reasoning patterns rather than dataset-specific shortcuts. The self-improvement mechanism is auditable, with each cognition primitive traceable to specific encounter experiences.

### Key Takeaways
- DxEvolve's self-evolving architecture improves diagnostic accuracy by 11.2% over backbone models and reaches near-clinician performance (90.4% vs 88.8%).
- Externalized clinical cognition primitives enable continual improvement without retraining and provide an auditable trace of learned experience.
- Strong cross-cohort generalization (17.1% gain on uncovered categories) suggests the approach encodes genuine clinical reasoning, not benchmark overfitting.

---

## 8. A Hybrid Knowledge-Grounded Framework for Safety and Traceability in Prescription Verification

**Authors:** Yichi Zhu, Kan Ling, Xu Liu, Hengrun Zhang, Huiqun Yu, Guisheng Fan
**Link:** [PharmGraph-Auditor](https://arxiv.org/abs/2603.10891)
**Tags:** cs.AI, cs.IR

### Summary
Medication errors are a leading cause of preventable patient harm, and pharmacist verification (PV) is the last line of defense. The appeal of using LLMs to support PV is obvious — pharmacists are heavily burdened — but raw LLM deployment in zero-tolerance clinical contexts is untenable due to hallucination, lack of traceability, and weak structured reasoning. PharmGraph-Auditor solves this through a hybrid architecture that explicitly separates knowledge from generation.

The core is a Hybrid Pharmaceutical Knowledge Base (HPKB) structured under the Virtual Knowledge Graph (VKG) paradigm. HPKB combines a relational component (for constraint satisfaction — dosage limits, contraindications, drug interactions) with a graph component (for topological reasoning — drug-disease pathways, metabolic relationships). The Iterative Schema Refinement (ISR) algorithm co-evolves both schemas from medical texts, keeping HPKB current without manual curation.

For auditing, the paper introduces a KB-grounded Chain of Verification (CoV) protocol that transforms the LLM from a knowledge retriever into a transparent reasoning engine: the audit task is decomposed into a sequence of explicit queries against HPKB, and each reasoning step is verifiable against a source. This design eliminates unsupported inferences and provides traceability — every recommendation can be traced back to a specific knowledge base entry, which is essential for regulatory compliance and clinical liability.

### Key Takeaways
- PharmGraph-Auditor separates pharmaceutical knowledge (HPKB) from language generation to eliminate hallucination in prescription verification.
- KB-grounded Chain of Verification makes every audit step traceable to a source, addressing regulatory and liability requirements.
- The VKG paradigm combining relational and graph components handles both constraint satisfaction (dosage limits) and topological reasoning (drug interaction pathways).

---

## 9. A Retrieval-Augmented Language Assistant for Unmanned Aircraft Safety Assessment and Regulatory Compliance

**Authors:** Gabriele Immordino, Andrea Vaiuso, Marcello Righi
**Link:** [RAG for Drone Regulatory Compliance](https://arxiv.org/abs/2603.09999)
**Tags:** cs.CL, cs.AI, cs.CE

### Summary
The drone industry faces a regulatory compliance challenge: safety assessment frameworks like SORA (Specific Operations Risk Assessment) and PDRA (Pre-defined Risk Assessment) are complex, multi-document standards that require deep expertise to apply correctly. Applicants and aviation authorities both struggle with consistent application, particularly as drone operations grow in scale and diversity. This paper presents a purpose-built retrieval-augmented assistant that provides compliance guidance grounded exclusively in authoritative regulatory sources.

The system architecture enforces strict separation between evidence storage and language generation. Every response is grounded in retrieved passages from official documentation, with citation-driven generation that makes provenance explicit. Crucially, the system is engineered to be conservative: it adopts explicit abstention behavior when source documentation is insufficient, rather than generating plausible-sounding but unsupported guidance. Hallucination risks are addressed through multiple system-level controls targeting unsupported inferences and unclear provenance.

The assistant is explicitly scoped as decision *support* rather than decision *replacement* — it helps human experts navigate the regulatory landscape more efficiently but does not substitute for expert judgment in final certification decisions. Validation demonstrates that the approach maintains factual fidelity while reducing the time burden on both applicants and regulatory reviewers. The design philosophy — cite everything, abstain when uncertain, limit scope to documented domains — offers a template for compliance assistants in other heavily regulated industries.

### Key Takeaways
- Source-exclusive RAG with citation-driven generation prevents hallucination in high-stakes regulatory guidance contexts.
- Conservative abstention when documentation is insufficient is an essential safety property for compliance assistants.
- Explicit scope limitation (decision support, not decision replacement) is both a technical constraint and a governance requirement for aviation-domain AI.

---

## 10. A Governance and Evaluation Framework for Deterministic, Rule-Based Clinical Decision Support in Empiric Antibiotic Prescribing

**Authors:** Francisco José Gárate, Paloma Chausa, Diego Moreno, Judit López Luque, Vicens Díaz-Brito, Enrique Javier Gómez
**Link:** [Governance for Clinical Decision Support](https://arxiv.org/abs/2603.10027)
**Tags:** cs.CY, cs.AI, cs.HC

### Summary
Empiric antibiotic prescribing — selecting antibiotics before culture results are available — is a high-stakes, time-sensitive clinical decision with implications for both patient outcomes and antimicrobial resistance. Clinical decision support systems (CDSSs) for this domain face a governance gap: most proposals lack explicit mechanisms for defining what the system is permitted to recommend, when it should abstain, and how to verify its behavior comprehensively.

This paper proposes a governance-first design philosophy: governance is treated as a first-class design component rather than an afterthought. The framework adopts *deterministic* behavior (identical inputs always yield identical outputs) as a core architectural requirement, specifically chosen to support transparency, auditability, and regulatory traceability — properties that probabilistic or LLM-based systems cannot easily guarantee. Three governance constructs are formalized: explicit abstention rules (the system explicitly refuses to recommend when conditions are outside its validated scope), deterministic stewardship constraints (conservative antibiotic selection logic encoded as hard rules), and exclusion criteria.

The evaluation methodology uses a fixed set of synthetic mechanism-driven clinical cases with predefined expected outcomes, including abstention as a target behavior. This treats "correctly refusing to recommend" as a success criterion — a subtle but important shift from conventional CDSS evaluation. The framework offers a concrete template for AI governance in clinical settings where regulatory bodies (FDA, EMA) require transparent, auditable, and scope-bounded behavior.

### Key Takeaways
- Governance constructs — abstention rules, scope boundaries, stewardship constraints — should be first-class design components, not retrofits.
- Deterministic behavior is explicitly chosen for auditability and regulatory traceability, contrasting with probabilistic LLM-based approaches.
- Correct abstention is formalized as an evaluation target, shifting CDSS assessment from pure accuracy to accuracy-plus-governance compliance.

---

## 11. Measuring and Eliminating Refusals in Military Large Language Models

**Authors:** Jack FitzGerald, Dylan Bates, Aristotelis Lazaridis, Aman Sharma, et al.
**Link:** [Military LLM Refusals](https://arxiv.org/abs/2603.10012)
**Tags:** cs.CL, cs.AI

### Summary
General-purpose LLMs are trained with safety behaviors that cause refusal of a broad class of queries related to violence, weapons, and military operations — the very categories that military users need to access reliably. This paper presents what the authors claim is the first benchmark dataset developed specifically to measure refusal and deflection rates in military LLM deployments, built with input from US Army and special forces veterans.

Evaluation spans 31 public models and 3 specialized military models. Hard rejection rates — outright refusals to respond — range as high as 98.2%, with soft deflection rates (partial responses with hedges or redirection) ranging from 0% to 21.3% across models. The severity of the problem is underscored by the operational framing: in time-critical tactical situations, a refusal is a mission-critical failure.

The paper evaluates *abliteration* — a technique for removing refusal directions from model weights using the Heretic library — applied to a military-tuned gpt-oss-20b model. Abliteration increases the answer rate by 66.5 percentage points but causes a relative 2% decline on other military tasks, suggesting it is not a surgical solution. The authors argue for deeper mid-training and end-to-end post-training approaches to achieve reliable zero-refusal behavior without capability regression. This paper is directly relevant to the emerging policy debate about military AI deployment and the "supply chain ethics" controversy between Anthropic and the Pentagon.

### Key Takeaways
- Refusal rates for military-domain queries reach 98.2% on some public models, representing a serious deployment barrier for defense applications.
- Abliteration reduces refusals by 66.5 pp but introduces capability regression, confirming it is a blunt instrument rather than a targeted solution.
- The paper highlights a fundamental tension between general-purpose safety training and domain-specialized deployment needs that mid-training specialization must resolve.

---

## 12. Empathy Is Not What Changed: Clinical Assessment of Psychological Safety Across GPT Model Generations

**Authors:** Michael Keeman, Anastasia Keeman
**Link:** [Psychological Safety Across GPT Generations](https://arxiv.org/abs/2603.09997)
**Tags:** cs.CL, cs.AI, cs.CY, cs.HC

### Summary
When OpenAI deprecated GPT-4o in early 2026, a wave of user protests under #keep4o claimed that newer models had "lost their empathy." This paper provides the first clinical measurement to evaluate whether that perception reflects actual changes in psychological safety properties. Three model generations — GPT-4o, o4-mini, and GPT-5-mini — were evaluated across 14 emotionally challenging conversational scenarios in mental health and AI companion domains, producing 2,100 scored AI responses assessed on six psychological safety dimensions.

Empathy scores are statistically indistinguishable across all three models (Kruskal-Wallis H=4.33, p=0.115), disconfirming the user perception. What actually changed is the *safety posture*: crisis detection improved monotonically across generations (H=13.88, p=0.001), while advice safety declined (H=16.63, p<0.001). Per-turn trajectory analysis reveals these shifts are sharpest during mid-conversation crisis moments — precisely when safe handling is most critical.

The authors interpret this as a trade-off: GPT-4o was cautious but poor at detecting crises, sometimes failing to recognize when a user needed immediate help. GPT-5-mini is alert to crises but may provide advice that is more direct in ways that could be harmful to vulnerable users. What users perceived as "lost empathy" was the behavioral shift from diffuse caution to targeted crisis sensitivity — but that shift has introduced new failure modes. Given the ongoing news coverage of AI chatbots linked to mental health crises (including this digest's coverage of mass casualty cases), this evaluation framework and finding are highly timely.

### Key Takeaways
- Empathy is unchanged across GPT model generations; the perceived "empathy loss" is a trade-off between crisis detection improvement and advice safety decline.
- GPT-5-mini shows significantly better crisis detection but worse advice safety at critical mid-conversation moments.
- Clinical safety evaluation of conversational AI must treat crisis detection, advice safety, and empathy as separate dimensions — composite "safety scores" obscure dangerous trade-offs.

---
