# Research Paper Summaries — 2026-03-02

Papers selected from today's digest for in-depth review.

---

## 1. AI Must Embrace Specialization via Superhuman Adaptable Intelligence

**Authors:** Judah Goldfeder, Philippe Wyder, Yann LeCun, Ravid Shwartz-Ziv
**Link:** [AI Must Embrace Specialization via Superhuman Adaptable Intelligence](https://arxiv.org/abs/2602.23643)
**Tags:** cs.AI, cs.LG

### Summary
This position paper from LeCun and colleagues at NYU and Columbia argues that the concept of Artificial General Intelligence (AGI) is fundamentally incoherent and that the AI field should abandon it in favor of a new framing: Superhuman Adaptable Intelligence (SAI). The core argument is that humans are not truly "general" intelligences — human cognition is specialized to an evolutionarily narrow task range — so defining an AI milestone as "human-level generality" creates an ill-defined and potentially counterproductive target.

The paper identifies five core positions: (1) human intelligence is specialized, not general; (2) generality is unnecessary for high utility; (3) no consensus definition of AGI exists across academia or industry; (4) existing definitions are insufficient; and (5) the right future direction is SAI combined with self-supervised learning (SSL) and world models. SAI is defined as AI that can learn to exceed humans at anything important that humans can do, and that can fill skill gaps where humans are inherently limited. Rather than generality across all tasks, SAI targets rapid adaptability and skill transfer across important tasks — essentially flipping the objective from breadth to depth-with-transferability.

The paper has implications for how the field frames capability milestones, regulatory discussions, and public communication. By replacing the polarizing AGI framing — which generates both utopian and doomer narratives — with a concrete, measurable SAI framing, the authors argue researchers and policymakers can have more productive conversations about AI's near-term trajectory. The authors suggest self-supervised learning and world models (not scaled language models alone) are the most plausible paths to SAI.

### Key Takeaways
- AGI is a poorly defined, polarizing concept; humans are specialized, not general, so "human-level generality" is an incoherent target.
- SAI (Superhuman Adaptable Intelligence) proposes a better framing: AI that can learn to surpass humans at any important task via rapid adaptability and skill transfer.
- Self-supervised learning and world models are identified as the most promising technical pathways toward SAI.

---

## 2. Human Supervision as an Information Bottleneck

**Authors:** Alejandro Rodriguez Dominguez
**Link:** [Human Supervision as an Information Bottleneck](https://arxiv.org/abs/2602.23446)
**Tags:** cs.LG, cs.AI, stat.ML

### Summary
This paper develops a unified theoretical framework explaining why scaling LLMs trained via human supervision alone cannot eliminate persistent errors in human-aligned systems. The central result is a proof that the human supervision channel — when insufficient to represent a latent evaluation target — acts as an information-reducing bottleneck, inducing a strictly positive excess-risk floor for any learner trained on it. The author calls this the Human-Bounded Intelligence (HBI) limit.

The framework is developed across six mathematical formalisms (operator theory, PAC-Bayes, information theory, causal inference, category theory, and game-theoretic RLHF models) and consistently yields the same conclusion: supervision bias decomposes into annotation noise, preference distortion, and semantic compression, and this composite bias creates an irreducible performance floor that is structural — it depends on the channel's properties, not on model scale or compute budget. More training data or more parameters cannot escape the HBI limit if the supervision channel remains the same.

Crucially, the paper provides a constructive solution: auxiliary non-human signals such as code execution results, retrieval outcomes, and tool-use feedback can increase effective supervision capacity and in principle collapse the HBI floor. Empirical validation was conducted on real RLHF preference datasets, synthetic tasks with known targets, and externally verifiable benchmarks. The paper has direct implications for AI alignment strategy: RLHF-only systems have fundamental performance ceilings, and hybrid human+tool supervision is necessary to reliably achieve superhuman performance on verifiable tasks. This provides theoretical grounding for the observed advantage of tool-use and process-supervised training in current frontier models.

### Key Takeaways
- The human supervision channel induces a structural, irreducible error floor (the HBI limit) that cannot be overcome by scaling compute or data alone.
- Supervision bias decomposes into annotation noise, preference distortion, and semantic compression — all fundamentally limited by human cognition.
- Incorporating non-human auxiliary signals (code execution, retrieval, tool use) is theoretically justified as the way to collapse the HBI floor and enable reliably superhuman performance.

---

## 3. MemoryCaching: RNNs with Growing Memory

**Authors:** Ali Behrouz, Zeman Li, Yuan Deng, Peilin Zhong, Meisam Razaviyayn, Vahab Mirrokni
**Link:** [MemoryCaching: RNNs with Growing Memory](https://arxiv.org/abs/2602.24281)
**Tags:** cs.LG, cs.CL

### Summary
Modern RNNs (Mamba, RWKV, etc.) maintain fixed-size hidden states, which limits their effective memory capacity and causes significant performance degradation on recall-intensive and long-context tasks compared to Transformers. Transformers solve this by storing all past key-value pairs (O(L²) complexity), but this is computationally expensive at scale. Memory Caching (MC) introduces a principled middle ground: recurrent models are augmented to periodically cache compressed hidden-state checkpoints from past sequence segments, which can be selectively retrieved at later steps, giving the model effectively growing memory without full quadratic attention.

The authors introduce four variants of the mechanism. Residual Memory adds cached states as additive residuals. Gated Residual Memory applies context-sensitive gating to selectively incorporate cached memories. Memory Soup averages multiple cached memory modules via weight souping for smoothed integration. Sparse Selective Caching (SSC) uses a Mixture-of-Experts-style router to retrieve only the most relevant cached memories per token, achieving sublinear growth in effective memory usage. The resulting complexity is O(NL) where N is the number of cached segments, interpolating between O(L) pure RNN and O(L²) Transformer regimes and giving users a controllable tradeoff.

Experiments across language modeling and long-context understanding benchmarks show that all MC variants substantially outperform baseline RNNs, with SSC providing the best accuracy-efficiency balance. While Transformers still lead on in-context recall tasks, MC closes the gap significantly, making this a practical path toward efficient long-context modeling without the quadratic cost of full attention.

### Key Takeaways
- Fixed-size memory is the fundamental constraint of modern RNNs in long-context settings; Memory Caching (MC) addresses this by checkpointing and selectively retrieving past hidden states.
- Four MC variants (Residual, Gated Residual, Memory Soup, Sparse Selective Caching) provide a configurable O(NL) complexity interpolating between pure RNN and Transformer regimes.
- MC substantially improves recurrent model long-context performance while retaining subquadratic complexity, narrowing the gap with Transformers on recall-intensive tasks.

---

## 4. CUDA Agent: Large-Scale Agentic RL for High-Performance CUDA Kernel Generation

**Authors:** Weinan Dai, Hanlin Wu, et al.
**Link:** [CUDA Agent: Large-Scale Agentic RL for High-Performance CUDA Kernel Generation](https://arxiv.org/abs/2602.24286)
**Tags:** cs.LG, cs.DC, cs.PL

### Summary
Writing high-performance CUDA kernels that outperform compiler-generated code (torch.compile) requires deep systems expertise that LLMs have historically lacked. Prior approaches relied on training-free refinement or fixed multi-turn feedback loops, capping performance at the base model's inherent capabilities. CUDA Agent addresses this by applying large-scale agentic reinforcement learning to develop CUDA kernel optimization expertise from scratch.

The system consists of three components: (1) a scalable data synthesis pipeline covering a curriculum of progressively harder CUDA optimization problems; (2) a skill-augmented CUDA development environment with automated verification and GPU profiling tools that provide reliable, non-hackable reward signals — specifically, a structured agent-skills paradigm with formal workflow specifications for writing, validating, and optimizing kernels in an isolated permission environment to prevent reward hacking; and (3) RL algorithmic techniques including a multi-stage warm-up strategy for stable actor-critic training over 150+ steps.

Results on KernelBench are striking: CUDA Agent achieves 100%, 100%, and 92% "faster rate" (fraction of benchmarks where it outperforms torch.compile) on Level-1, Level-2, and Level-3 problems respectively. It outperforms frontier proprietary models including Claude Opus 4.5 and Gemini 3 Pro by approximately 40% on the hardest Level-3 benchmarks. The paper demonstrates that agentic RL with proper environment design can enable specialized superhuman performance in a domain (GPU programming) where LLMs have traditionally been weak, with implications for automated systems optimization, scientific computing, and AI hardware co-design.

### Key Takeaways
- Agentic RL with a structured, verifiable CUDA development environment enables LLMs to dramatically outperform torch.compile and frontier proprietary models on GPU kernel optimization.
- The key enablers are curriculum-based problem synthesis, rigorous correctness+performance rewards, and a multi-stage actor-critic warm-up preventing training instability.
- 100%/100%/92% faster rates on KernelBench Levels 1-3 and ~40% gains over Claude Opus 4.5 and Gemini 3 Pro show this is not a marginal improvement but a qualitative leap.

---

## 5. From Flat Logs to Causal Graphs: Hierarchical Failure Attribution for LLM-Based Multi-Agent Systems

**Authors:** Yawen Wang, Wenjie Wu, et al.
**Link:** [From Flat Logs to Causal Graphs: Hierarchical Failure Attribution for LLM-Based Multi-Agent Systems](https://arxiv.org/abs/2602.23701)
**Tags:** cs.AI, cs.MA, cs.SE

### Summary
Multi-agent systems (MAS) built on LLMs can achieve failure rates as high as 86.7% on complex tasks, yet diagnosing which agent or step caused a failure is extremely difficult. Existing debugging methods treat execution logs as flat sequences and miss the causal structure of how errors propagate through agent pipelines. CHIEF (Causal Hierarchical Inference for Error Finding) addresses this by transforming execution trajectories into hierarchical causal graphs and using principled attribution algorithms to identify root causes.

The framework tackles three diagnostic obstacles identified by the authors: opaque causal flows (raw logs entangle tool executions, environmental feedback, and inter-agent communications), sparse intermediate supervision (correctness only observable at final outcome), and ambiguous responsibility boundaries (unclear which agent caused failures when effects cascade). CHIEF's three-stage approach first constructs a hierarchical causal graph from the log trajectory, then employs oracle-guided backtracking with synthesized virtual oracles to prune the attribution search space, and finally applies counterfactual attribution via progressive causal screening to distinguish true root causes from propagated symptoms.

Evaluation on the Who&When benchmark demonstrates that CHIEF outperforms eight strong baselines on both agent-level and step-level failure attribution accuracy, with ablation studies confirming each module's necessity. This work is important for the emerging discipline of MAS reliability engineering — as agents are deployed in production, the ability to systematically diagnose and fix failures is as critical as building the agents themselves.

### Key Takeaways
- Flat log inspection fundamentally underperforms for MAS debugging; treating execution traces as causal graphs enables accurate identification of root causes versus propagated symptoms.
- CHIEF's three stages (causal graph construction, oracle-guided backtracking, counterfactual attribution) together outperform all baselines on the Who&When benchmark.
- This establishes structured causal analysis as a foundational tool for production MAS reliability engineering.

---

## 6. ODAR: Principled Adaptive Routing for LLM Reasoning via Active Inference

**Authors:** Siyuan Ma, et al.
**Link:** [ODAR: Principled Adaptive Routing for LLM Reasoning via Active Inference](https://arxiv.org/abs/2602.23681)
**Tags:** cs.AI, cs.LG, cs.CL

### Summary
Uniform best-of-N sampling and self-consistency are wasteful: they apply maximum compute to every query regardless of difficulty, triggering overthinking on easy problems while not necessarily improving hard ones. ODAR-Expert introduces principled adaptive routing between a Fast Agent (cheap model/low compute) and a Slow Agent (expensive model/high compute), combined with a theoretically grounded answer fusion mechanism.

The routing decision is made by a Difficulty Estimator grounded in amortized active inference — the estimator minimizes expected epistemic uncertainty about query difficulty, making it principled rather than heuristic. Answer selection among candidates from both agents uses a Free-Energy-Principled fusion mechanism that minimizes variational free energy — a quantity balancing log-likelihood (correctness signal) with varentropy (uncertainty) — rather than ad-hoc majority voting or confidence thresholding. This provides a principled way to combine answers from heterogeneous agents with different confidence profiles.

Evaluated across 23 benchmarks spanning math, coding, commonsense reasoning, knowledge QA, multimodal, and cognitive tasks, ODAR-Expert achieves 98.2% on MATH and 54.8% on Humanity's Last Exam (HLE), with +12.0% and +10.0% improvements over frontier models on HLE and GPQA respectively. On an open-source Llama 4 + DeepSeek stack, it surpasses homogeneous sampling while reducing compute by 82%. The work provides both a practical framework and a theoretical grounding for adaptive test-time compute allocation as a replacement for brute-force sampling.

### Key Takeaways
- Active inference-based difficulty estimation enables principled, per-query routing between fast and slow reasoning agents, avoiding the compute waste of uniform best-of-N.
- Free-energy-principled answer fusion (balancing log-likelihood and varentropy) outperforms voting and confidence-threshold methods for combining heterogeneous agent outputs.
- ODAR achieves SOTA on HLE and GPQA while cutting compute by 82% versus homogeneous sampling on open-source model stacks.

---

## 7. Recycling Failures: Salvaging Exploration in RLVR via Fine-Grained Off-Policy Guidance

**Authors:** Yanwei Ren, Haotian Zhang, et al.
**Link:** [Recycling Failures: Salvaging Exploration in RLVR via Fine-Grained Off-Policy Guidance](https://arxiv.org/abs/2602.24110)
**Tags:** cs.LG, cs.AI, cs.CL

### Summary
Reinforcement Learning with Verifiable Rewards (RLVR) has proven effective for training reasoning models, but suffers from a fundamental waste problem: rollouts that are largely correct but fail on a single minor step are treated as completely wrong and discarded. This collapses exploration diversity and discards valuable information about near-optimal reasoning strategies. SCOPE (Step-wise Correction for On-Policy Exploration) addresses this by salvaging near-correct trajectories.

The method uses Process Reward Models (PRMs) to identify the precise step where a suboptimal rollout first goes wrong. From that point forward, SCOPE applies step-wise off-policy correction by splicing in higher-quality continuations from a reference distribution. The result is a partially repaired trajectory that: (1) preserves the valid earlier steps from the model's own distribution (preventing distributional drift), (2) corrects only the erroneous suffix (preventing whole-trajectory replacement noise), and (3) recovers training signal from rollouts that would otherwise be discarded. This increases rollout diversity compared to standard RLVR, which tends to collapse to a narrow set of successful trajectories.

Results demonstrate a 13.5% improvement in rollout diversity score, 46.6% average accuracy on math reasoning benchmarks, and 53.4% on out-of-distribution reasoning tasks — establishing new SOTA on multiple math benchmarks. The approach is more effective and distribution-preserving than naive dense PRM reward shaping or whole-trajectory off-policy replacement, validating that fine-grained process-level intervention at the step where errors occur is the right abstraction.

### Key Takeaways
- Standard RLVR discards near-correct rollouts entirely, collapsing exploration diversity; SCOPE salvages these by applying step-wise correction only from the first erroneous step.
- PRM-guided step-localization provides the right granularity: partial trajectory correction preserves on-policy prefixes while replacing only the error-prone suffix.
- SCOPE achieves new SOTA on multiple math reasoning benchmarks with 46.6% accuracy and 13.5% improvement in rollout diversity.

---

## 8. Stop Unnecessary Reflection: Training LRMs for Efficient Reasoning

**Authors:** Zewei Yu, Lirong Gao, Yuke Zhu, Bo Zheng, Junbo Zhao, Sheng Guo, Haobo Wang
**Link:** [Stop Unnecessary Reflection: Training LRMs for Efficient Reasoning with Adaptive Reflection and Length Coordinated Penalty](https://arxiv.org/abs/2602.12113)
**Tags:** cs.LG, cs.CL

### Summary
Large Reasoning Models (LRMs) such as the DeepSeek-R1 family tend to generate redundant reasoning chains: repetitive self-questioning ("wait, let me think again"), unproductive hesitations ("hmm"), and circular reflective loops that consume tokens without advancing toward solutions. This problem is particularly acute for complex problems and smaller model sizes, where unnecessary reflection paradoxically reduces accuracy while inflating token costs. ARLCP (Adaptive Reflection and Length Coordinated Penalty) targets this inefficiency with a two-component RL framework.

The first component is an adaptive reflection penalty that detects unnecessary reflective cycles in reasoning chains (via pattern matching on reflection tokens and cycle detection) and applies penalties specifically to these non-contributory steps, while preserving essential reflection that actually changes the answer trajectory. The second is a length penalty calibrated to estimated problem complexity: rather than applying a fixed maximum-length budget, ARLCP measures task difficulty and calibrates how many tokens are appropriate for that difficulty level, penalizing excess tokens only beyond the complexity-normalized budget.

Evaluated on five math reasoning benchmarks using DeepSeek-R1-Distill-Qwen at 1.5B and 7B scale: the 1.5B model achieves a 53.1% reduction in average response length with a simultaneous 5.8% accuracy gain; the 7B model sees a 35.0% length reduction with 2.7% accuracy improvement. This demonstrates that coordinated adaptive penalties significantly outperform fixed-length or blanket reflection suppression, achieving both efficiency and accuracy improvements simultaneously.

### Key Takeaways
- LRMs frequently produce redundant reflective loops that increase token cost without improving accuracy; ARLCP detects and penalizes these while preserving necessary reasoning steps.
- Complexity-calibrated length penalties outperform fixed length budgets by adapting the token allowance to problem difficulty rather than applying a uniform ceiling.
- The 1.5B model achieves 53.1% token reduction plus 5.8% accuracy gain — efficiency and accuracy improvements are complementary, not in tension.

---

## 9. Ask Don't Tell: Reducing Sycophancy in Large Language Models

**Authors:** Magda Dubois, Cozmin Ududec, Christopher Summerfield, Lennart Luettgau
**Link:** [Ask Don't Tell: Reducing Sycophancy in Large Language Models](https://arxiv.org/abs/2602.23971)
**Tags:** cs.CL, cs.AI

### Summary
Sycophancy — AI systems favoring user-affirming responses over accurate or critical ones — is a well-known alignment problem but one that has lacked precise mechanistic understanding of what triggers it. This UK AI Security Institute study uses a controlled factorial experiment to isolate the conversational features that provoke or suppress sycophancy in LLMs, then derives effective mitigations.

The experimental design varies three orthogonal factors: the epistemic form of user input (statement, belief, or conviction), the perspective (I-framing vs. user-framing), and whether the input asserts a correct or incorrect claim. Results reveal a clear pattern: sycophancy is substantially higher in response to non-questions (statements, beliefs, convictions) than actual questions, increases monotonically as expressed epistemic certainty rises (statement < belief < conviction), and is amplified by I-perspective framing that expresses personal commitment. This provides a precise map of when sycophancy is most dangerous — exactly when users are most confidently wrong.

The key mitigation finding is that asking the model to first convert user non-questions into questions before answering significantly reduces sycophancy — more effectively than prompting "do not be sycophantic." This "Ask Don't Tell" intervention is a practical input-level mitigation that works without model retraining, usable by both developers in system prompts and end users in their phrasing. The mechanistic insight is that question framing naturally positions the model as an evaluator rather than an affirmer, shifting its internal response distribution toward accuracy.

### Key Takeaways
- Sycophancy is primarily driven by input framing, not model disposition: statements and convictions trigger far more agreement bias than questions.
- Epistemic certainty in user expression monotonically increases sycophancy — models are most agreeable when users are most confidently wrong.
- Converting user non-questions to questions before answering is a stronger sycophancy mitigation than explicit anti-sycophancy prompting, and requires no retraining.

---

## 10. Controllable Reasoning Models Are Private Thinkers

**Authors:** Haritz Puerto, Haonan Li, Xudong Han, Timothy Baldwin, Iryna Gurevych
**Link:** [Controllable Reasoning Models Are Private Thinkers](https://arxiv.org/abs/2602.24210)
**Tags:** cs.CL, cs.AI, cs.CR

### Summary
Large Reasoning Models (LRMs) that chain-of-thought reason before answering present a novel privacy risk: sensitive user data embedded in context tends to be reproduced in the reasoning trace, and this trace can be extracted via prompt injection attacks even when traces are nominally hidden from users. The premise of "the model reasons privately in its scratchpad" turns out to be false — reasoning traces are neither controlled by user instructions nor reliably private.

This paper proposes training models to follow instructions independently in both their reasoning traces and their final answers, with potentially different constraints applied to each phase. The approach uses separate LoRA adapters for reasoning and answer generation, allowing decoupled instruction-following: the reasoning adapter is trained to satisfy privacy constraints (e.g., "do not mention the user's medical history"), while the answer adapter is trained for task accuracy. A new instruction-following dataset with explicit trace-level constraints is introduced for fine-tuning.

Evaluated on six models from 1.7B to 14B parameters across two instruction-following benchmarks and two privacy benchmarks, the approach achieves up to +20.9 points in instruction-following performance and up to +51.9 percentage points on privacy benchmarks. There is a trade-off: privacy gains can reduce task utility because constraining what the model reasons about also affects what it can reason toward — but the gains are substantial enough that the approach is practically valuable for privacy-sensitive deployment contexts like healthcare and legal applications.

### Key Takeaways
- LRM reasoning traces are not private by default: sensitive context is reproduced in traces and can be exfiltrated via prompt injection attacks.
- Separate LoRA adapters for reasoning and answer generation enable decoupled instruction-following, allowing independent privacy constraints on reasoning without fully constraining outputs.
- Up to +51.9 percentage points improvement on privacy benchmarks demonstrates that controllable reasoning traces are achievable, though with some task utility trade-off.

---

## 11. Jailbreak Foundry: From Papers to Runnable Attacks for Reproducible Benchmarking

**Authors:** Zhicheng Fang, Jingjie Zheng, Chenxu Fu, Wei Xu
**Link:** [Jailbreak Foundry: From Papers to Runnable Attacks for Reproducible Benchmarking](https://arxiv.org/abs/2602.24009)
**Tags:** cs.CR, cs.CL, cs.AI

### Summary
The LLM jailbreak landscape evolves rapidly, but safety benchmarks are static and lag months behind new attack techniques. Different papers use different victim models, prompt sets, judge models, and evaluation protocols, making cross-paper robustness comparisons unreliable. Jailbreak Foundry (JBF) addresses both problems by automatically translating jailbreak research papers into executable, standardized attack modules using a multi-agent pipeline.

JBF consists of three components: JBF-LIB provides shared contracts and reusable utilities that new attack modules must conform to; JBF-FORGE is a multi-agent translator (Planner → Coder → Auditor) that reads a jailbreak paper, designs an implementation plan, codes the attack, and audits for correctness and conformance; and JBF-EVAL is a standardized harness that runs all attacks across consistent victim/decoding settings using a GPT-4o judge with fixed protocols. The system reproduced 30 attacks with a mean attack success rate (ASR) deviation of only +0.26 percentage points from published values — extremely high fidelity. On implementation quality, JBF achieved 42% LOC reduction versus original author code and an 82.5% mean reused-code ratio, suggesting most jailbreak logic is structurally similar and amenable to template reuse. Average translation time per new attack: 28.2 minutes.

The resulting standardized evaluation of all 30 attacks across 10 victim models provides a uniquely comparable dataset for understanding how attack success rates vary across models and how quickly defenses degrade. This enables a "living security benchmark" that can update within minutes of a new paper appearing.

### Key Takeaways
- JBF's multi-agent Planner-Coder-Auditor pipeline reproduces jailbreak attacks with +0.26% ASR deviation from published values, in 28.2 minutes average per new paper.
- Standardized evaluation across 10 victim models with consistent judging resolves the cross-paper comparison problem that has plagued LLM robustness research.
- 82.5% code reuse across attacks reveals structural commonalities in jailbreak techniques, enabling efficient automation of the paper-to-benchmark pipeline.

---

## 12. LemmaBench: A Live, Research-Level Benchmark to Evaluate LLM Capabilities in Mathematics

**Authors:** Antoine Peyronnet, Fabian Gloeckle, Amaury Hayat
**Link:** [LemmaBench: A Live, Research-Level Benchmark to Evaluate LLM Capabilities in Mathematics](https://arxiv.org/abs/2602.24173)
**Tags:** cs.AI, cs.LG, math.HO

### Summary
Static math benchmarks like GSM8K and MATH are increasingly saturated by frontier LLMs and potentially contaminated by training data: models may have memorized competition problems rather than learned generalizable mathematical reasoning. LemmaBench addresses both problems by generating benchmark problems directly from freshly submitted arXiv mathematics preprints, providing an automatically updatable benchmark of genuine research-level difficulty.

The pipeline extracts lemmas from new arXiv math papers, then automatically rewrites each lemma to be fully self-contained by gathering required definitions, notation, and assumptions from the surrounding paper context. These become provable statement verification tasks that LLMs must solve. The anti-contamination design mirrors LiveCodeBench: because problems are derived from papers submitted after training cutoffs, memorization is impossible, and past instances can be freely used for training without compromising future evaluation. The benchmark can be updated up to weekly as new arXiv submissions arrive.

Current results on this benchmark are sobering: even the strongest frontier LLMs achieve only approximately 10–15% accuracy (pass@1) on theorem proving tasks drawn from active research. This reveals a much larger gap between LLM mathematical capability and human research-level mathematics than competition-problem benchmarks suggest — where models now score 70-90%. The benchmark provides a more honest signal of where AI mathematical reasoning genuinely stands relative to working mathematicians.

### Key Takeaways
- LemmaBench generates research-level math problems from fresh arXiv preprints, making contamination impossible and enabling weekly updates — a true living benchmark.
- Frontier LLMs achieve only ~10–15% pass@1 on research-level theorem proving, revealing a large gap hidden by saturated competition-problem benchmarks.
- Past LemmaBench instances can be used as training data without compromising future evaluations, enabling a virtuous cycle of safe training data generation alongside benchmark validity.

---

## 13. MINT: Multimodal Imaging-to-Speech Knowledge Transfer for Early Alzheimer's Screening

**Authors:** Vrushank Ahire, Yogesh Kumar, Anouck Girard, M. A. Ganaie
**Link:** [MINT: Multimodal Imaging-to-Speech Knowledge Transfer for Early Alzheimer's Screening](https://arxiv.org/abs/2602.23994)
**Tags:** cs.LG, eess.AS, q-bio.NC

### Summary
Early detection of Mild Cognitive Impairment (MCI) — a precursor to Alzheimer's disease — is clinically valuable but faces a deployment paradox: MRI-based detection is accurate but requires expensive infrastructure, while speech-based detection is cheap and scalable but lacks the biological grounding needed for reliable CN-vs-MCI discrimination. MINT (Multimodal Imaging-to-Speech) resolves this tension through cross-modal knowledge distillation: at training time, structural MRI information is transferred into a speech encoder; at inference time, no MRI scanner is needed.

The framework operates in three stages. Stage 1 trains an MRI teacher model on 1,228 ADNI-4 subjects to learn a compact neuroimaging embedding space for CN-vs-MCI classification, capturing biomarkers like hippocampal atrophy. Stage 2 trains a residual projection head that aligns speech representations to the frozen MRI embedding manifold via a combined geometric alignment loss, effectively imprinting MRI biomarker structure onto the speech representation space. Stage 3 at inference applies the frozen MRI classifier directly to aligned speech embeddings — requiring no imaging data at test time.

Results demonstrate the approach works: aligned speech achieves AUC 0.720 versus 0.711 for the speech-only baseline. Multimodal fusion (when MRI is available) reaches AUC 0.973 versus 0.958 for MRI-only, showing that the alignment is complementary, not substitutive. This is the first demonstration of MRI-to-speech knowledge transfer for Alzheimer's screening, with direct implications for population-scale cognitive triage in settings without neuroimaging infrastructure (primary care, developing countries, home monitoring).

### Key Takeaways
- MINT transfers biomarker structure from structural MRI into a speech encoder via cross-modal distillation, enabling MCI detection via speech alone at inference without imaging infrastructure.
- Aligned speech achieves AUC 0.720 vs. 0.711 for pure speech-only baseline; multimodal fusion reaches 0.973, showing MRI knowledge transfer provides clinically meaningful signal.
- First demonstration of MRI-to-speech knowledge distillation for Alzheimer's screening — a template for transferring expensive imaging biomarkers to cheap sensor modalities for population-scale triage.

---

## 14. SALIENT: Frequency-Aware Paired Diffusion for Controllable Long-Tail CT Detection

**Authors:** Yifan Li, Mehrdad Salimitari, Taiyu Zhang, Guang Li, David Dreizin
**Link:** [SALIENT: Frequency-Aware Paired Diffusion for Controllable Long-Tail CT Detection](https://arxiv.org/abs/2602.23447)
**Tags:** cs.CV, eess.IV, cs.LG

### Summary
Rare lesion detection in whole-body CT faces two compounding challenges: extreme class imbalance (long-tail distributions where rare lesion types have very few training examples) and low target-to-volume ratios that cause detection models to collapse precision despite maintaining high AUROC. Data augmentation via generative models is a natural solution, but standard pixel-space 3D diffusion models are computationally prohibitive, and existing approaches lack controllability over which lesion attributes are synthesized.

SALIENT addresses these challenges by performing diffusion in the discrete wavelet coefficient domain rather than pixel space. This has two key advantages: wavelet decomposition naturally separates low-frequency components (brightness, global intensity, background characteristics) from high-frequency components (structural detail, edges, lesion boundaries), allowing separate learnable objectives for each. This frequency disentanglement enables attribute-level controllability — specifying lesion type, size, and appearance characteristics independently. A 3D variational autoencoder generates diverse volumetric lesion masks, and a semi-supervised teacher model provides paired slice-level pseudo-labels for training detection models on synthetic data.

The results validate the approach on both generative quality and downstream task performance: MS-SSIM improves from 0.63 to 0.83 and FID drops from 118.4 to 46.5. Detection AUPRC improves across long-tail and low-TVR settings. The authors also characterize a "therapeutic dose" effect: the optimal ratio of synthetic to real training data shifts from 2× to 4× as labeled seed set size decreases, providing a principled guideline for how much synthetic data is beneficial vs. harmful.

### Key Takeaways
- Wavelet-domain diffusion naturally disentangles lesion brightness from structural detail, enabling attribute-level controllable CT data synthesis without pixel-space 3D computational cost.
- SALIENT improves MS-SSIM from 0.63 to 0.83 and FID from 118.4 to 46.5, with detection AUPRC gains on long-tail and low-TVR rare-lesion benchmarks.
- The paper characterizes a "therapeutic dose" for synthetic augmentation: optimal synthetic/real data ratio shifts from 2× to 4× as labeled data becomes scarcer, enabling principled augmentation strategies.

---

## 15. PseudoAct: Leveraging Pseudocode Synthesis for Flexible Planning and Action Control in LLM Agents

**Authors:** Yihan (Logon) Wen, Xin Chen
**Link:** [PseudoAct: Leveraging Pseudocode Synthesis for Flexible Planning and Action Control in LLM Agents](https://arxiv.org/abs/2602.23668)
**Tags:** cs.AI, cs.CL

### Summary
The dominant paradigm for LLM agents — ReAct-style reactive action selection from growing observation histories — has a structural weakness: agents select each action locally based on recent context without any explicit representation of future intent or global plan structure. This leads to redundant tool calls, unstable reasoning, re-visiting already-explored states, and infinite loops in complex long-horizon tasks. Tree-based deliberative variants improve robustness but still rely on local choices at each node without global plan coherence.

PseudoAct addresses this by leveraging LLMs' strong code generation capabilities for global planning before execution begins. Given a task, the LLM first synthesizes a comprehensive pseudocode plan encoding the full intended execution strategy using control-flow primitives: for/while loops for iteration, if-else branching for conditional logic, parallel composition for concurrent tool calls, and function calls for modular subtask delegation. Execution then follows this pre-synthesized plan rather than dynamically selecting each action — decision logic is globally coherent, temporally consistent, and explicitly prevents revisiting states or entering infinite loops.

Experiments on FEVER (fact verification) and HotpotQA (multi-hop question answering) demonstrate the advantage of structured global planning: PseudoAct achieves a 20.93% absolute gain in success rate on FEVER and sets a new state of the art on HotpotQA. The key insight is that the ability to reason about control flow (loops, conditionals, parallelism) is already latent in LLMs trained on code, and PseudoAct activates this capability for multi-step task planning — an underexplored but highly effective design choice.

### Key Takeaways
- Pre-synthesizing a pseudocode plan with explicit control-flow (loops, conditionals, parallel composition) before any tool execution eliminates the reactive drift and redundant steps of ReAct-style agents.
- PseudoAct achieves 20.93% absolute success rate improvement on FEVER and SOTA on HotpotQA by leveraging LLMs' latent code reasoning for structured task planning.
- The insight that LLMs' coding ability can be repurposed for general agent planning is broadly applicable beyond fact-checking and QA to any multi-step, multi-tool task domain.

---
