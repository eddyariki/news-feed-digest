# Research Paper Summaries — 2026-02-23

Papers selected from today's digest for in-depth review.

---

## 1. Anatomy of Capability Emergence: Scale-Invariant Representation Collapse and Top-Down Reorganization

**Authors:** Jayadev Billa (independent researcher; formerly ISI@USC, Yahoo, Nuance, BBN)
**Link:** https://arxiv.org/abs/2602.15997
**Tags:** cs.LG

### Summary
How do capabilities suddenly appear during neural network training? This paper presents the most systematic geometric analysis of capability emergence to date, tracking five geometric measures across five model scales (405K–85M parameters) and 120 emergence events in eight algorithmic tasks, then validating findings on three Pythia language models (160M–2.8B).

The central finding is that training begins with a *universal representation collapse*: the effective rank of hidden representations drops to a task-specific floor before any capability emerges. These floors are **scale-invariant across a 210× parameter range** — for example, modular arithmetic collapses to RANKME ≈ 2.0 regardless of model size. This contradicts the common bottom-up feature-building intuition; instead, collapse propagates **top-down**, with output-facing layers compressing first (32/32 consistency across task×model combinations). Among the five geometric measures tested, representation effective rank (RANKME) is the cheapest to compute and provides the best temporal signal, leading capability emergence by a measurable margin for hard tasks (75–100% precursor rate).

However, the paper is honest about limits: within-difficulty-class prediction concordance is only 27%, and per-task precursor signals do not reliably transfer to the naturalistic Pythia pre-training regime where task boundaries are diffuse. The contribution is thus the geometric anatomy itself — collapse floors, top-down propagation, temporal hierarchy among measures — not a turnkey prediction tool.

### Key Takeaways
- Training universally begins with representation collapse to task-specific floors; those floors are scale-invariant across a 210× parameter range.
- Collapse propagates top-down (output layers first), contradicting the bottom-up feature-building narrative.
- RANKME is the best and cheapest leading indicator of emergence — but geometric measures cannot achieve fine-grained timing prediction in naturalistic pre-training.

---

## 2. Doc-to-LoRA: Learning to Instantly Internalize Contexts

**Authors:** Rujikorn Charakorn, Edoardo Cetin, Shinnosuke Uesaka, Robert T. Lange (Sakana AI; Minerva University)
**Link:** https://arxiv.org/abs/2602.15902
**Tags:** cs.CL, cs.LG

### Summary
Long context windows carry a quadratic attention cost at inference time, and standard context distillation (CD) — which compresses information into model weights — requires slow, memory-intensive gradient descent per document. Doc-to-LoRA (D2L) solves both problems by meta-learning the CD process into a lightweight hypernetwork that generates a LoRA adapter for a target LLM in a **single forward pass**, given any unseen document.

The architecture uses a Perceiver-style cross-attention module that maps variable-length token activations (from the frozen target LLM's internal representations) to fixed-rank LoRA matrices for each layer. A chunking mechanism concatenates per-chunk adapters along the rank dimension, enabling processing of documents that exceed the target LLM's native context window. The hypernetwork is meta-trained on a large corpus of (context, query, response) triples using a KL-divergence objective that aligns the student-with-adapter to the teacher-with-context.

Empirically, D2L achieves near-perfect zero-shot accuracy on Needle-in-a-Haystack retrieval at context lengths **4× beyond the training distribution** (32K tokens vs. 256-token training sequences). On real-world QA benchmarks (2WikiMultihopQA, SQuAD), D2L outperforms standard CD under limited compute budgets while delivering substantially lower peak memory and latency. Notably, D2L also zero-shot transfers visual information from a VLM to a text-only LLM through adapter internalization.

### Key Takeaways
- A hypernetwork can meta-learn the context distillation process and execute it in one forward pass — amortizing the cost across all future documents.
- D2L generalizes to context lengths 4× beyond training sequences via a chunking mechanism that concatenates LoRA adapters.
- The approach opens a path to frequent knowledge updates and personalized LLM behavior without retraining the base model.

---

## 3. Can Generative AI Survive Data Contamination? Theoretical Guarantees under Contaminated Recursive Training

**Authors:** Kevin Wang, Hongqian Niu, Didong Li (University of North Carolina at Chapel Hill)
**Link:** https://arxiv.org/abs/2602.16065
**Tags:** cs.LG, stat.ML

### Summary
As AI-generated content saturates the web, future model versions will inevitably train on mixtures of human-generated and AI-generated data — a "recursive contamination" regime. Prior theoretical work showed that training exclusively on synthetic data leads to *model collapse* in Gaussian and discrete settings. This paper provides the **first positive theoretical result** on recursive training under contamination in a fully general framework, with no parametric assumptions on the real data distribution and no restrictions on the generative model class.

The key theorem proves that contaminated recursive training still **converges to the true distribution**, but at a rate equal to the *minimum* of (a) the baseline model's convergence rate and (b) the fraction of real data used in each iteration. This creates a phase transition: below the diagonal in the (baseline-rate, real-fraction) plane, the real-data fraction limits convergence; above it, the baseline rate dominates. The authors extend the analysis to biased sampling, showing that if bias decays faster than the baseline convergence rate, the contaminated model still reaches the true distribution; otherwise, the bias decay rate becomes the limiting factor.

This result has direct practical implications: maintaining a minimum real-data fraction is sufficient to prevent collapse, and bias correction in data collection can continue to guide later model generations even when early data is skewed. Theoretical claims are validated with empirical studies.

### Key Takeaways
- Recursive training on contaminated (human + AI-generated) data converges without collapse, provided some fraction of real data is included per iteration — the first general positive result.
- Convergence rate is min(baseline model rate, real-data fraction), creating a quantifiable phase transition.
- Bias in real data need not be fatal: if sampling improves over iterations faster than the baseline rate, the model eventually converges to the true distribution.

---

## 4. Towards a Science of AI Agent Reliability

**Authors:** Stephan Rabanser, Sayash Kapoor, Peter Kirgis, Kangheng Liu, Saiteja Utpala, Arvind Narayanan (Princeton University)
**Link:** https://arxiv.org/abs/2602.16666
**Tags:** cs.AI

### Summary
AI agents are being deployed for consequential tasks, yet standard evaluation collapses all behavior into a single mean accuracy metric. This paper argues — and demonstrates — that such compression hides critical operational flaws, and proposes a multi-dimensional reliability science grounded in safety-critical engineering practice from aviation, nuclear power, automotive, and industrial process control.

The authors define agent reliability across four dimensions: **consistency** (same behavior across runs under identical conditions), **robustness** (graceful degradation under input/environment perturbations), **predictability** (calibrated confidence, ability to recognize impending failure), and **safety** (bounded severity when failures do occur). Twelve concrete, accuracy-independent metrics operationalize these dimensions.

Applying this framework to 14 frontier agentic models (including GPT-4 Turbo through GPT-5.2, Claude 3.5 Haiku through Claude 4.5 Opus, and Gemini 2.0 Flash through Gemini 3.0 Pro) across GAIA and τ-bench, they find that **accuracy improvements over 18 months far outpace reliability gains**: accuracy improves at ~0.21/yr while overall reliability improves at only 0.03–0.10/yr. Consistency and predictability emerge as the dimensions most urgently needing research attention. High-profile failure examples (Replit database deletion, unauthorized Instacart purchase, NYC chatbot illegal advice) are analyzed through the framework's lens.

### Key Takeaways
- Mean task accuracy obscures whether agents fail consistently vs. unpredictably, benignly vs. catastrophically — properties that matter fundamentally for deployment.
- Twelve reliability metrics across four dimensions (consistency, robustness, predictability, safety) reveal that capability gains have not translated into equivalent reliability gains over 18 months.
- Consistency and predictability are the biggest gaps: agents that score well on average still fail erratically, with no ability to recognize when they are about to fail.

---

## 5. Multi-agent Cooperation Through In-Context Co-Player Inference

**Authors:** Marissa A. Weis, Maciej Wołczyk, Rajai Nasser, Rif A. Saurous, Blaise Agüera y Arcas, João Sacramento, Alexander Meulemans (Google, Paradigms of Intelligence Team; Santa Fe Institute)
**Link:** https://arxiv.org/abs/2602.16301
**Tags:** cs.AI, cs.MA

### Summary
Achieving robust cooperation among self-interested agents is a long-standing challenge in multi-agent reinforcement learning. Existing approaches either require hardcoded assumptions about co-player learning rules or enforce an artificial separation between "naive learners" (fast timescale) and "meta-learners" (slow timescale). This paper from Google DeepMind demonstrates that neither mechanism is necessary: training sequence model agents via standard decentralized MARL against a **diverse distribution of co-players** naturally induces in-context best-response strategies that drive cooperative outcomes.

The mechanism works through in-context learning: sequence models trained in a mixed pool of diverse tabular agents and other learning agents develop the ability to infer co-player strategy from episode history alone. This in-context adaptation makes them vulnerable to extortion — which in turn, when two such agents interact, creates mutual pressure that resolves into learned cooperation. The paper introduces **Predictive Policy Improvement (PPI)**, a self-supervised sequence modeling method that learns the improved policy as a posterior over joint trajectories.

Experiments on the Iterated Prisoner's Dilemma show robust cooperation under both A2C and PPI when training uses the mixed pool, while agents trained only against other learning agents — or given explicit co-player identifiers — converge to defection. Ablations confirm that removing co-player diversity or the in-context inference mechanism breaks the cooperative outcome.

### Key Takeaways
- Standard decentralized RL on sequence models combined with co-player diversity is sufficient to learn cooperative behavior — no explicit meta-gradient machinery or timescale separation required.
- In-context learning acts as a functional "naive learner" on the fast timescale, making agents susceptible to extortion; mutual extortion pressure from learning agents then drives both toward cooperation.
- PPI provides a principled model-based alternative to A2C that theoretically relates to Nash and subjective embedded equilibria.

---

## 6. Framework of Thoughts: Dynamic and Optimized Reasoning Based on Chains, Trees, and Graphs

**Authors:** Felix Fricke, Simon Malberg, Georg Groh (Technical University of Munich)
**Link:** https://arxiv.org/abs/2602.16512
**Tags:** cs.AI, cs.CL

### Summary
Prompting schemes like Chain of Thought, Tree of Thoughts, and Graph of Thoughts improve LLM reasoning, but they all share three limitations: manually defined static graph structures, under-optimized hyperparameters and prompts, and sequential (non-parallelized) execution that creates unnecessary latency and cost.

Framework of Thoughts (FoT) is a **foundation framework** — not a new reasoning scheme itself — for implementing and optimizing any chain-, tree-, or graph-based reasoning approach. FoT models reasoning as a directed multigraph where nodes are operations (LLM calls, tool invocations, code execution) and edges carry intermediate thoughts. Crucially, the graph is **dynamic**: operations can modify the graph structure during execution, enabling fully automatic derivation of reasoning topology without task-specific pre-planning.

FoT additionally provides: parallel execution of independent operations (with race-condition protection), persistent caching of operation results within and across samples (making hyperparameter optimization tractable), and built-in tools for prompt and hyperparameter search. The authors re-implement ToT, GoT, and ProbTree within FoT and demonstrate significant speedups, cost reductions, and accuracy improvements through optimization — gains that were previously impractical because the optimization overhead was prohibitive without caching.

### Key Takeaways
- FoT unifies CoT, ToT, GoT, and graph-based reasoning under a single dynamic-graph abstraction that supports automatic structure derivation — eliminating the need for task-specific prompt engineering.
- Parallel execution and persistent caching together make hyperparameter and prompt optimization tractable for the first time for reasoning schemes.
- The framework is open and Python-extensible: any operation (LLM call, retrieval, tool, code) is a valid node, enabling tool-augmented dynamic reasoning.

---

## 7. Evidence for Daily and Weekly Periodic Variability in GPT-4o Performance

**Authors:** Paul Tschisgale (Leibniz Institute for Science and Mathematics Education, Kiel), Peter Wulff (Ludwigsburg University of Education)
**Link:** https://arxiv.org/abs/2602.15889
**Tags:** stat.AP, cs.AI

### Summary
Much AI research implicitly assumes that LLM performance is *time-invariant* under fixed conditions — same model snapshot, same hyperparameters, same prompt, same results. This paper subjects that assumption to a rigorous 3-month longitudinal test: GPT-4o (fixed API snapshot) was queried every 3 hours on the same multiple-choice physics problem, with 10 independent responses per time point, yielding a dense time series of average accuracy scores.

Spectral (Fourier) analysis of this time series reveals **statistically significant periodic patterns** accounting for approximately **20% of total variance**. The dominant components match a daily rhythm and a weekly rhythm, consistent with the known periodicity of server load driven by usage patterns (peak workday usage, quiet weekend nights). The authors speculate that load-driven changes in inference infrastructure — batching strategies, hardware allocation, quantization decisions — may systematically affect output quality even when the underlying model weights are frozen.

The implications are substantial: any AI research that measures LLM capability at a single time point, compares outputs across sessions spaced by days, or longitudinally tracks LLM performance in production may be confounded by this temporal variability. Reproducibility claims for fixed-model studies require controlling or randomizing over time-of-day and day-of-week.

### Key Takeaways
- GPT-4o performance under fully fixed conditions varies periodically over time — daily and weekly cycles account for ~20% of total score variance over 3 months.
- Temporal variability threatens reproducibility of AI research: two studies using the same model but run at different times of day or week may not be comparable.
- The likely mechanism is server-load-driven changes in inference infrastructure, not model weight changes — an externality invisible to researchers with only API access.

---

## 8. Learning Personalized Agents from Human Feedback (PAHF)

**Authors:** Kaiqu Liang, Julia Kruk, Shengyi Qian, Xianjun Yang, Shengjie Bi, Yuanshun Yao, Shaoliang Nie, Mingyang Zhang, Lijuan Liu, Jaime Fernández Fisac, Shuyan Zhou, Saghar Hosseini (Meta Superintelligence Labs; Princeton University; Duke University)
**Link:** https://arxiv.org/abs/2602.16173
**Tags:** cs.AI, cs.LG

### Summary
Modern AI agents struggle to align with the idiosyncratic, evolving preferences of individual users. Prior personalization approaches rely on static datasets (pre-collected user profiles or historical interaction logs), making them unable to handle new users, real-time corrective feedback, or preference drift over time. PAHF (Personalized Agents from Human Feedback) addresses all three failure modes through a **continual learning loop** that treats each live interaction as the primary training signal.

The framework operationalizes a three-step interactive loop. First, *pre-action clarification*: when facing an ambiguous instruction and empty (or insufficient) memory, the agent queries the user before acting — resolving "known unknowns." Second, *grounded action execution*: the agent synthesizes user instruction with preferences retrieved from explicit per-user memory. Third, *post-action feedback integration*: after the agent acts, the user can provide corrective feedback, which updates the memory to correct mistakes or track preference drift. The memory is deliberately kept lightweight to isolate the effect of the feedback channels themselves.

The authors develop two large-scale evaluation benchmarks (embodied robot manipulation and online shopping) with a four-phase protocol separating initial preference learning from adaptation under persona shifts. Theoretical analysis establishes sample complexity bounds showing that dual feedback channels (pre- and post-action) learn substantially faster than single-channel baselines. Empirical results confirm consistent outperformance over no-memory and single-channel systems across both domains.

### Key Takeaways
- PAHF introduces a continual personalization framework that learns user preferences online from live interaction, handling new users, corrective feedback, and preference drift without pre-collected data.
- The three-step loop (pre-action clarification → grounded execution → post-action feedback) combines two orthogonal feedback channels: one for resolving ambiguity before acting, one for updating stale beliefs after acting.
- Post-action feedback is the most critical element: pre-action queries alone cannot correct miscalibrated beliefs when user preferences shift.

---

## 9. Generalized Leverage Score for Scalable Assessment of Privacy Vulnerability

**Authors:** Valentin Dorseuil (DI ENS, École normale supérieure, PSL), Jamal Atif (CMAP, École polytechnique, IPP), Olivier Cappé (DI ENS)
**Link:** https://arxiv.org/abs/2602.15919
**Tags:** stat.ML, cs.LG

### Summary
Membership Inference Attacks (MIAs) determine whether a specific data point was in a model's training set — the primary empirical tool for auditing individual privacy risk. State-of-the-art MIA methods use *shadow models*: training dozens to hundreds of reference models on different data splits, which is computationally prohibitive at scale. This paper asks: can individual privacy vulnerability be assessed **without retraining or simulating attacks**?

The answer is yes. In Gaussian linear models, the authors prove that the statistical **leverage score** (the diagonal entry hᵢᵢ of the hat matrix H = X(X⊤X)⁻¹X⊤) is the *sufficient statistic* for membership inference risk: the optimal MIA test statistic is a data-dependent affine transformation of the residual loss controlled solely by hᵢᵢ. High-leverage points — those geometrically positioned to have disproportionate influence on model parameters — are most vulnerable. Critically, this result holds without distributional assumptions on the attacker.

To extend this to deep neural networks, the paper introduces the **Generalized Leverage Score (GLS)**, derived via implicit differentiation of training optimality conditions. The GLS measures self-influence (the sensitivity of a prediction to its own label), generalizing leverage to both regression and classification. A computationally tractable last-layer approximation retains strong empirical correlation with state-of-the-art shadow model attacks, providing a principled, fast first-pass filter for identifying high-risk training points.

### Key Takeaways
- The leverage score is the theoretically optimal sufficient statistic for membership inference vulnerability in linear models — the first principled link between geometric data influence and privacy risk.
- This characterization works without simulating attacks or retraining, replacing hundreds of shadow model training runs with a single geometric computation.
- The Generalized Leverage Score (GLS) extends this to deep networks via a last-layer approximation that correlates strongly with the best existing MIA methods.

---

## 10. Foundation Models for Medical Imaging: Status, Challenges, and Directions

**Authors:** Chuang Niu, Pengwei Wu, Bruno De Man, Ge Wang (Rensselaer Polytechnic Institute; GE HealthCare Technology & Innovation Center)
**Link:** https://arxiv.org/abs/2602.15913
**Tags:** eess.IV, cs.CV, cs.AI

### Summary
Medical imaging AI is undergoing a paradigm shift from narrowly trained task-specific networks toward large foundation models (FMs) adaptable across modalities, anatomies, and clinical tasks. This comprehensive review — timed to the IEEE Transactions on Medical Imaging Special Issue on Foundation Models — synthesizes the field along three axes: FM design principles, clinical applications, and forward-looking challenges.

On design principles, the review covers the dominant architectures (Transformers and ViTs, CNNs for data-scarce settings, Mamba/SSMs for long sequential data), training strategies (self-supervised pre-training via contrastive learning, masked autoencoders, and generative objectives; parameter-efficient fine-tuning via LoRA and prompt tuning), and efficiency techniques for deployment. A notable coverage extension over prior reviews is the inclusion of image *reconstruction* tasks (CT, SPECT, PET, MRI, ultrasound) alongside analysis tasks.

Clinical application sections survey segmentation FMs (SAM-based frameworks, interactive segmentation), vision-language models for report generation and diagnostic triage, and multimodal integration across radiology, pathology, ophthalmology, cardiology, and oncology. The challenges section is comprehensive: distribution shift across sites and scanners, long-tail rare disease representation, annotation scarcity, regulatory compliance (FDA/CE clearance), fairness across demographic subgroups, and interpretability requirements in clinical workflows. The authors identify four pillars for future work: data/knowledge, model/optimization, computing power, and regulatory science.

### Key Takeaways
- Medical imaging FMs are rapidly consolidating around SAM-inspired segmentation and vision-language architectures, with Mamba emerging as an alternative backbone for long sequential imaging data.
- A critical gap in prior reviews is image reconstruction (CT, MRI, PET) — FMs are showing strong promise here but regulatory and distribution-shift challenges are acute.
- The path to clinical deployment requires addressing fairness (improved average accuracy can mask subgroup disparities), interpretability, and regulatory frameworks that were not designed with FM generalization in mind.

---

## 11. ReLoop: Structured Modeling and Behavioral Verification for Reliable LLM-Based Optimization

**Authors:** Junbo Jacob Lian, Yujun Sun (Northwestern University), Huiling Chen (Wenzhou University), Chaoyu Zhang (City University of Hong Kong), Chung-Piaw Teo (National University of Singapore)
**Link:** https://arxiv.org/abs/2602.15983
**Tags:** cs.SE, cs.AI

### Summary
LLMs can translate natural language into optimization code, but a critical failure mode has gone largely unaddressed: *silent failures*, where generated code executes successfully and returns solver-feasible solutions that are nonetheless **semantically wrong** (missing constraints, omitted cost terms, incorrect variable types). On compositional retail optimization problems requiring multiple interacting constraints, state-of-the-art models achieve up to 91.1% solver-feasibility but only 0.5% formulation correctness — a 90-percentage-point gap.

ReLoop attacks silent failures from two complementary directions. First, *structured generation* decomposes code production into four stages: (1) **Understand** — extract objective, variables, constraints, parameters; (2) **Formalize** — produce a mathematical specification with explicit variable-type reasoning (continuous vs. integer vs. binary); (3) **Synthesize** — generate executable Gurobi code with data accessed via dictionary (needed for perturbation testing); (4) **Verify** — cross-check code against problem statement. This mirrors expert operations research practice and prevents many errors at their source.

Second, *behavioral verification* detects errors that survive generation: if perturbing a capacity parameter to near-zero produces no change in the optimal objective, that constraint is likely missing. This solver-based perturbation provides an external semantic signal independent of LLM introspection — the first approach capable of detecting silent failures without ground-truth solutions. Together, the two mechanisms raise correctness from 22.6% to 31.1% and execution from 72.1% to 100% on the strongest model, with consistent gains across five models (foundation, SFT, RL) and three benchmarks.

### Key Takeaways
- LLMs generating optimization code frequently produce "silent failures" — solver-feasible but semantically wrong — with up to a 90-point correctness gap on compositional problems.
- Solver-based parameter perturbation (does the objective change when a constraint is tightened to near-zero?) is the first technique for detecting silent failures without ground-truth solutions.
- Structured four-stage generation (understand/formalize/synthesize/verify) and behavioral verification are complementary: each dominates under different error profiles.

---

## 12. Not the Example, but the Process: How Self-Generated Examples Enhance LLM Reasoning

**Authors:** Daehoon Gwak, Minseo Jung, Junwoo Park, Minho Park, ChaeHun Park, Junha Hyung, Jaegul Choo (KAIST AI; Sungkyunkwan University)
**Link:** https://arxiv.org/abs/2602.15863
**Tags:** cs.CL, cs.AI

### Summary
Prior work showed that LLMs can improve their reasoning by generating their own few-shot examples before tackling a problem — but *why* this works was unclear. This paper isolates the mechanism through a carefully designed comparison between three prompting strategies: **Zero-shot** (direct answer), **Integrated** (generate a related problem and solve it, then answer the target — all in one prompt), and **Decoupled** (generate a related problem and answer in one call, then use that output as a few-shot example in a separate call).

The key insight: Integrated consistently outperforms both alternatives across five models (GPT-4.1, GPT-4O, Gemini-1.5-Flash, LLaMA-3.3-70B, LLaMA-3.1-8B) and two datasets (MATH, GSM8K). GPT-4O on MATH: 37.86% Integrated vs. 33.33% Zero-shot vs. 32.65% Decoupled. **Decoupled performs no better than Zero-shot**, despite having access to the same self-generated examples. The difference between Integrated and Decoupled is precisely whether the problem-creation process appears in the conversational context.

This demonstrates that the **act of creating an example — not its content** — drives the reasoning improvement. Attention pattern analysis on LLaMA-3.1-8B confirms that Integrated and Decoupled prompting produce significantly different attention distributions over the context, revealing how the presence of the creation process activates distinct information pathways.

### Key Takeaways
- Self-generated few-shot examples improve LLM reasoning only when the generation process is included in the same conversational context — the examples themselves, extracted and reused, provide minimal benefit.
- Decoupled prompting (common in practice) offers no reliable improvement over Zero-shot; only Integrated prompting (create and solve in one prompt) consistently helps.
- The mechanism is attentional: the creation process itself restructures how the model attends to context, not just what content is available.

---

## 13. EnterpriseBench Corecraft: Training Generalizable Agents on High-Fidelity RL Environments

**Authors:** Sushant Mehta, Logan Ritchie, Suhaas Garre, Ian Niebres, Nick Heiner, Edwin Chen (Surge AI)
**Link:** https://arxiv.org/abs/2602.16179
**Tags:** cs.AI

### Summary
AI agents routinely fail in real-world deployment despite strong benchmark scores — a gap attributed partly to training on overly simplified, synthetic environments that teach environment-specific heuristics rather than generalizable skills. Corecraft is the first environment in Surge AI's EnterpriseBench suite: a fully operational simulation of a customer support organization at a fictional PC parts retailer, designed explicitly around task quality and enterprise realism.

The environment comprises 2,500+ entities across 14 entity types (customers, orders, products, tickets, shipping, policies) with 23 unique tools exposed via Model Context Protocol (MCP). Tasks span a difficulty spectrum from basic information retrieval to complex multi-step workflows requiring constraint satisfaction, policy reasoning, and professional communication. Each task has expert-authored rubrics enabling automated reward computation for RL training.

Even the strongest frontier models (Claude Opus 4.6, GPT-5.2, Gemini 3.1 Pro) solve fewer than 35% of tasks when all rubric criteria must be satisfied. Training GLM 4.6 with GRPO (Group Relative Policy Optimization) for a single epoch achieves +11.39 percentage points on held-out Corecraft tasks — exceeding the capability gap between Claude Sonnet 4.5 and Claude Opus 4.5. More importantly, these gains **transfer to out-of-distribution benchmarks**: +4.5% on BFCL Parallel (function calling), +7.4% on τ²-Bench Retail (customer service), +6.8% on Tool Decathlon (long-horizon tool use).

### Key Takeaways
- High-fidelity, realistically structured training environments produce agents with genuinely transferable capabilities — not environment-specific heuristics — as demonstrated by consistent out-of-distribution gains.
- Even frontier models (GPT-5.2, Claude Opus 4.6, Gemini 3.1 Pro) solve fewer than 35% of Corecraft tasks when all criteria must be met, revealing substantial capability gaps in enterprise workflows.
- A single epoch of GRPO training on Corecraft (+11.4pp) transfers to +4.5–7.4% improvements on BFCL, τ²-Bench, and Tool Decathlon — benchmarks with entirely different domains.

---

## 14. A Lightweight Explainable Guardrail for Prompt Safety (LEG)

**Authors:** Md Asiful Islam, Mihai Surdeanu (University of Arizona)
**Link:** https://arxiv.org/abs/2602.15853
**Tags:** cs.CL, cs.AI

### Summary
Existing LLM safety guardrails fall into two camps: large LLM-based classifiers (Llama Guard, AEGIS, WildGuard, ShieldGemma) that are accurate but resource-intensive and opaque, or smaller task-specific models that are efficient but weaker and also opaque. No existing guardrail combines explainability, modularity, and low computational overhead. LEG addresses all three simultaneously.

The architecture is a shared transformer encoder with two classification heads trained jointly via multi-task learning: a **prompt classifier** (safe/unsafe) and an **explanation classifier** (per-token labels identifying which words make the prompt unsafe). The encoder is far smaller than LLM-based guardrails, adding negligible inference overhead.

Training the explainability head requires word-level annotations that don't exist in standard safety datasets. LEG's novel solution exploits LLM **confirmation bias**: given a prompt and its ground-truth label, the system queries an LLM with two adversarially framed questions (one assuming the prompt is safe, one assuming it's unsafe) and takes the intersection of identified words only when the LLM correctly resists the false assumption in both cases. This filters to high-quality, high-confidence synthetic explanations. The joint loss combines cross-entropy, focal loss (for hard negatives), and uncertainty-based weighting (learnable σ parameters). Results show SOTA or near-SOTA on three safety datasets in both in-domain and out-of-domain settings, with superior faithfulness and substantially lower computational cost than comparators.

### Key Takeaways
- LEG jointly classifies prompt safety and identifies unsafe words in a single lightweight forward pass — the first guardrail with built-in, quantitatively validated explainability.
- Synthetic explanation labels are generated by exploiting LLM confirmation bias as an adversarial reliability filter, selecting only explanations where the LLM correctly overcomes a false assumption.
- LEG achieves SOTA or near-SOTA safety classification with a model size and inference cost substantially below existing LLM-based guardrails, enabling deployment alongside latency-sensitive LLM pipelines.

---

## 15. FUTURE-VLA: Forecasting Unified Trajectories Under Real-time Execution

**Authors:** Jingjing Fan, Yushan Liu, Shoujie Li, Botao Ren, Siyuan Li, Xiao-Ping Zhang, Wenbo Ding, Zhidong Deng (Tsinghua University; Nanyang Technological University)
**Link:** https://arxiv.org/abs/2602.15882
**Tags:** cs.RO, cs.AI

### Summary
Vision-Language-Action (VLA) models for robot control face a fundamental tension: longer spatiotemporal history improves robustness, but the quadratic cost of processing it creates prohibitive latency. Existing approaches either sacrifice temporal context (single-frame policies) or decouple the world model from the controller (introducing representational mismatch and coordination overhead). FUTURE-VLA resolves this tension through a **dual-sided efficiency paradigm** that simultaneously extends history and compresses it.

On the input side, **Temporally Adaptive Cascaded Compression** applies progressively heavier strided convolution compression to frames farther from the current time step, maximizing information density within a fixed token budget while preserving high spatial resolution for recent observations. This is layered atop the Qwen3-VL visual stack's native patch merger. On the output side, the model abandons expensive pixel-level world model rollouts in favor of **latent-space autoregression**: action tokens (encoded via FAST spectral tokenization) and compact 32-token visual prediction tokens are generated in a single autoregressive forward pass, synchronizing action chunking with future state prediction at real-time speed.

This unified architecture also enables a **prediction-guided Human-in-the-Loop mechanism**: operators can inspect real-time visual previews of intended future states and gate execution before the robot commits, transforming the world model from a passive training signal into an active safety mechanism. FUTURE-VLA achieves 99.2% on LIBERO, 75.4% on RoboTwin, and 78.0% on a real-world Piper platform — all with a 16× extended spatiotemporal window and the same inference latency as a single-frame baseline.

### Key Takeaways
- Temporally adaptive cascaded compression enables 16× longer spatiotemporal histories with no latency increase by compressing distant frames more aggressively than recent ones.
- Latent-space autoregression for both actions and future visual states eliminates the compute-prohibitive pixel-level rollouts of conventional world models, enabling real-time joint control and prediction.
- The prediction-guided Human-in-the-Loop mechanism converts future state previews into an interactive execution gate — a practical safety mechanism for high-stakes robot deployments.

---

*Papers sourced from [digest-2026-02-23.md](digest-2026-02-23.md). PDFs downloaded from ArXiv and analyzed from full text.*
