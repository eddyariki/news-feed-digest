# Research Paper Summaries — 2026-02-26

Papers selected from today's digest for in-depth review.

---

## 1. ARLArena: A Unified Framework for Stable Agentic Reinforcement Learning

**Authors:** Xiaoxuan Wang, Han Zhang, Haixin Wang, Yidan Shi, Ruoyan Li, Kaiqiao Han, Chenyi Tong, Haoran Deng, Renliang Sun, Alexander Taylor, Yanqiao Zhu, Jason Cong, Yizhou Sun, Wei Wang
**Link:** [ARLArena](https://arxiv.org/abs/2602.21534)
**Tags:** cs.AI

### Summary
Agentic reinforcement learning (ARL) — training LLMs to act as autonomous agents over multi-turn, interactive tasks — suffers from chronic training instability. Small early errors cascade across interaction turns, producing distribution shifts that amplify credit-assignment noise and cause training collapse. Existing methods are hard to compare because they lack a shared testbed. ARLArena addresses this by introducing (1) a standardized, reproducible testbed built on behavior cloning initialization, format correction, and KL-based regularization, and (2) a systematic decomposition of policy-gradient RL into four orthogonal design dimensions: advantage design, importance-sampling (IS) clipping, dynamic filtering, and loss aggregation. The paper maps representative algorithms (GRPO, DAPO, SAPO, GSPO, etc.) onto these dimensions and runs controlled ablations. Three key findings emerge: tolerant IS clipping causes collapse, negative advantages combined with IS ratios below 1 create instability, and sequence-level masking is a critical stabilizer. These insights are unified into **SAMPO**, a new policy optimization algorithm combining sequence-level clipping, fine-grained advantage design, and dynamic rollout filtering. On ALFWorld (web agent) and Sokoban (embodied agent), SAMPO achieves the highest success rates with monotonically stable training curves while baselines collapse or oscillate. The paper also tests on multimodal and TIR math agents, showing consistent gains. A notable limitation is that the testbed focuses on established benchmarks; scalability to more open-ended agentic environments (e.g., long-horizon coding or tool use at scale) remains to be validated.

### Key Takeaways
- Training collapse in ARL is driven by specific, diagnosable failure modes, not fundamental instability.
- Sequence-level clipping and fine-grained advantage estimation are the most impactful design choices for stability.
- SAMPO offers the research community a reproducible recipe for ARL training, which is a prerequisite for reliable scaling.

---

## 2. Power and Limitations of Aggregation in Compound AI Systems

**Authors:** Nivasini Ananthakrishnan, Meena Jagadeesan
**Link:** [Power and Limitations of Aggregation](https://arxiv.org/abs/2602.21556)
**Tags:** cs.AI

### Summary
Multi-agent compound AI systems commonly query several copies of the same model and aggregate their outputs. Given model homogeneity, it is unclear when this provides real benefit over querying a single model. This paper provides a formal theory of when aggregation helps, using a principal-agent framework where a system designer (principal) steers each agent (model copy) via reward functions and aggregates their outputs. The analysis identifies three mechanisms through which aggregation can expand the set of outputs the designer can elicit: **feasibility expansion** (aggregating feasible individual outputs into an otherwise infeasible combination), **support expansion** (enriching the support of the output distribution), and **binding set contraction** (moving outputs from the boundary of the feasible set into the interior). The paper proves that any aggregation operation must implement at least one of these mechanisms to add power, and derives necessary and sufficient conditions characterizing elicitability-expansion. These theoretical results are illustrated empirically on a reference-generation task where LLMs generate paper citation lists. A key practical implication: systems designers should deliberately design aggregation operations to exploit one of these three mechanisms, rather than assuming that "more heads are better." The work also clarifies when aggregation is redundant, which has direct cost implications for compound AI deployments.

### Key Takeaways
- Aggregation over homogeneous models is only beneficial when it implements one of three specific mechanisms: feasibility expansion, support expansion, or binding set contraction.
- Simple majority voting or union operations do not automatically improve elicitability; careful reward function co-design is required.
- The framework provides a principled basis for designing compound AI systems and diagnosing when redundant multi-model calls can be safely eliminated.

---

## 3. GradAlign: Gradient-Aligned Data Selection for LLM Reinforcement Learning

**Authors:** Ningyuan Yang, Weihua Du, Weiwei Sun, Sean Welleck, Yiming Yang
**Link:** [GradAlign](https://arxiv.org/abs/2602.21492)
**Tags:** cs.LG

### Summary
RL post-training for LLMs is critically sensitive to training data quality, yet the field still relies on crude heuristics (accuracy-based filtering, difficulty proxies near 50% accuracy) that treat RL data selection identically to SFT data selection. The core problem they ignore is RL's non-stationarity: rollouts are generated by an evolving policy, so what constitutes a "useful" training sample changes as learning progresses. GradAlign addresses this with a gradient-alignment-based adaptive curriculum. For each candidate training problem, GradAlign computes the cosine similarity between that problem's policy gradient and the aggregated gradient over a small trusted validation set. Problems whose gradients align with the validation gradient direction are prioritized, since they are most likely to produce downstream performance improvement. Crucially, GradAlign periodically recomputes these scores as the policy evolves, maintaining a continuously updated curriculum. The method is evaluated across three challenging data regimes — unreliable reward signals, distribution imbalance between training and target tasks, and low-utility training corpora — consistently outperforming scalar heuristic baselines. From Tsinghua University (IIIS) and CMU (LTI). The main limitation is computational overhead from gradient computation across the candidate dataset, though the authors use efficient approximations.

### Key Takeaways
- RL data selection requires gradient-level alignment signals, not just scalar difficulty proxies, due to the non-stationarity of policy optimization.
- GradAlign adapts its curriculum dynamically as the policy evolves, a critical property absent in prior static selection methods.
- The method is particularly valuable when training corpora are noisy or mismatched with deployment tasks — increasingly common in large-scale automated data collection.

---

## 4. Budget-Aware Agentic Routing via Boundary-Guided Training

**Authors:** Caiqi Zhang, Menglin Xia, Xuchao Zhang, Daniel Madrigal, Ankur Mallick, Samuel Kessler, Victor Rühle, Saravan Rajmohan
**Link:** [Budget-Aware Agentic Routing](https://arxiv.org/abs/2602.21227)
**Tags:** cs.CL

### Summary
In long-horizon agentic workflows, invoking a powerful (and expensive) LLM at every step is economically unsustainable, but using only cheap models fails on the critical steps requiring advanced reasoning. Agentic routing — dynamically selecting between cheap and expensive models at each step — is fundamentally harder than single-turn routing: decisions are path-dependent (early choices affect downstream states), rewards are sparse (only at episode end), and deployments impose strict per-task budget caps. This paper formalizes Budget-Aware Agentic Routing (BAAR) and introduces **Boundary-Guided Training (BGT)**, a two-stage training pipeline. First, two boundary policies (always-small vs. always-large) are used to taxonomize tasks into Easy, Hard, and Intractable categories. Boundary-Guided SFT (BoSFT) synthesizes cost-efficient training trajectories using stratified sampling from this taxonomy. Second, **Boundary-Guided Policy Optimization (BoPO)** applies online RL with a boundary-relative reward (calibrating cost penalties against difficulty) and a reference-guided advantage to prevent the common collapse to "always choose the cheap model." At inference time, Budget-Constrained Decoding prunes actions that would exceed remaining budget. Evaluated on benchmarks spanning scientific discovery, embodied agents, and tool-using coding, BAAR matches strong routing baselines at substantially lower cost and generalizes to strict inference-time budget constraints. From Cambridge and Microsoft M365 Research.

### Key Takeaways
- Agentic routing is a sequential decision problem requiring its own specialized training formulation, not a direct extension of single-turn routing.
- Boundary policies (always-cheap, always-expensive) provide a principled difficulty taxonomy that anchors learning under sparse rewards.
- The framework addresses both soft (efficiency frontier) and hard (budget cap) deployment constraints, making it practically applicable to production agentic systems.

---

## 5. Structurally Aligned Subtask-Level Memory for Software Engineering Agents

**Authors:** Kangning Shen, Jingyuan Zhang, Chenxi Sun, Wencong Zeng, Yang Yue
**Link:** [Structurally Aligned Subtask-Level Memory](https://arxiv.org/abs/2602.21611)
**Tags:** cs.SE

### Summary
LLM-based software engineering agents are increasingly augmented with memory to improve long-horizon performance. However, existing memory systems store and retrieve at the granularity of entire problem-solving episodes (instance-level memory). This creates a fundamental mismatch: software engineering tasks decompose into heterogeneous subtasks (bug analysis, fault localization, code editing, fix validation), and similarity at the global issue level is neither necessary nor sufficient for sharing relevant experience at specific reasoning stages. Two tasks with similar surface descriptions ("Fix Login Button" vs. "Fix Login Timeout") may require completely different reasoning paths, while globally dissimilar tasks may share subtask-level operations (e.g., both involve updating a frontend event listener). The paper proposes Structurally Aligned Subtask-Level Memory, where each memory entry is a triple (category z, intent description d, abstracted experience e). Retrieval uses a two-stage strategy: category z is enforced as a hard filter to eliminate cross-stage noise, then semantic similarity on intent d retrieves the most relevant experience. Memory is updated incrementally at subtask completion by abstracting transferable insights from raw trajectories. Evaluated on SWE-bench Verified across four backbone models (including Gemini 2.5 Pro), the method improves mean Pass@1 by +4.7 pp on average over the vanilla agent (+6.8 pp on Gemini 2.5 Pro), with gains growing as interaction budget increases. From Kuaishou Technology.

### Key Takeaways
- Instance-level memory granularity is fundamentally misaligned with the compositional nature of software engineering tasks.
- Subtask-level retrieval with hard category filters eliminates the dominant source of memory misretrieval in long-horizon agents.
- Performance gains scale with interaction budget, suggesting that subtask memory is most valuable for the most complex, long-running tasks.

---

## 6. Field-Theoretic Memory for AI Agents: Continuous Dynamics for Context Preservation

**Authors:** Subhadip Mitra
**Link:** [Field-Theoretic Memory for AI Agents](https://arxiv.org/abs/2602.21220)
**Tags:** cs.CL

### Summary
Standard agent memory architectures treat memories as discrete database entries, retrieved via vector similarity. This misses important temporal and semantic dynamics: memories should naturally age, consolidate, and influence each other based on semantic proximity, not just explicit query time matching. This paper proposes treating agent memory as a continuous scalar field ϕ(x, y, t) defined on a 2D semantic manifold, governed by a modified heat equation with thermodynamic decay and source terms. New information enters as localized perturbations; memories diffuse through semantically related regions (creating gradients of association), decay based on importance weighting (frequently accessed memories resist forgetting), and couple across agents in multi-agent settings without explicit coordination. Retrieval combines semantic similarity with local field amplitude. Evaluated on two long-context benchmarks: LoCoMo (300-turn conversations, 35 sessions) and LongMemEval (500+ turns). On LongMemEval, the field-theoretic approach achieves +116% F1 on multi-session reasoning (p<0.01, d=3.06), +43.8% on temporal reasoning (p<0.001), and +27.8% retrieval recall on knowledge updates. Multi-agent experiments show >99.8% collective intelligence with 2-8 agents. The JAX implementation achieves a 518x speedup via JIT compilation. From Rotalabs. A single-author paper with very large effect sizes warrants independent replication; the benchmark comparisons rely on a vector database baseline.

### Key Takeaways
- Modeling memory as a continuous PDE-governed field enables natural diffusion, decay, and inter-memory interaction absent in discrete vector databases.
- Multi-session and temporal reasoning — among the hardest memory tasks — show the largest improvements, suggesting field dynamics particularly help with long-range context.
- The multi-agent field coupling mechanism enables implicit knowledge sharing without centralized coordination, which is highly relevant for multi-agent AI systems.

---

## 7. Overconfident Errors Need Stronger Correction: Asymmetric Confidence Penalties for RL

**Authors:** Yuanda Xu, Hejian Sang, Zhengze Zhou, Ran He, Zhipeng Wang
**Link:** [Asymmetric Confidence Penalties for RL](https://arxiv.org/abs/2602.21420)
**Tags:** cs.LG

### Summary
RLVR post-training improves Pass@1 on reasoning tasks, but consistently narrows reasoning diversity — models trained with RLVR tend to underperform their base models at Pass@k for large k, concentrating probability mass on a few learned reasoning paths. This diversity collapse is commonly attributed to incorrect rollouts being penalized uniformly, regardless of how that error arises. The paper identifies a more precise root cause: **overconfident errors** — incorrect reasoning paths that RL has spuriously reinforced so that the policy assigns high probability to them relative to the reference model. Unlike exploratory errors (benign stochastic deviations) or self-correcting errors (paths the model is already abandoning), overconfident errors persistently suppress valid trajectories. Standard KL penalties are symmetric and undifferentiated, failing to apply stronger correction to these errors. The paper proposes **ACE (Asymmetric Confidence-aware Error Penalty)**, which defines a per-rollout confidence shift metric c_i = log(π_θ(y_i|x)/π_ref(y_i|x)) and uses it to dynamically modulate negative advantages: overconfident errors receive amplified penalties while exploratory errors are left approximately unchanged. Theorem 1 decomposes ACE's gradient into a selective regularizer restricted to overconfident errors plus a moderation residual. Experiments on Qwen2.5-Math-7B, Qwen3-8B-Base, and Llama-3.1-8B-Instruct using GRPO and DAPO show consistent improvements across the full Pass@k spectrum on MATH-500 and AIME 2025. From LinkedIn.

### Key Takeaways
- Not all incorrect rollouts are equal: overconfident errors (spuriously reinforced wrong paths) are the primary driver of diversity collapse in RLVR.
- Per-rollout confidence shift c_i = log(π_θ/π_ref) is a simple, computable diagnostic that distinguishes error types without requiring additional annotations.
- ACE composes with existing RLVR algorithms (GRPO, DAPO) and improves both Pass@1 and the full diversity spectrum, resolving the standard safety-diversity tradeoff.

---

## 8. Alignment-Weighted DPO: A Principled Reasoning Approach to Safety Alignment

**Authors:** Mengxuan Hu, Vivek V. Datla, Anoop Kumar, Zihan Guan, Sheng Li, Alfy Samuel, Daben Liu
**Link:** [Alignment-Weighted DPO](https://arxiv.org/abs/2602.21346)
**Tags:** cs.CL

### Summary
Despite SFT, RLHF, and DPO, LLMs remain vulnerable to jailbreaks that disguise harmful intent through indirect phrasing, role-playing, cipher encoding, or logical obfuscation. The paper begins with a causal intervention experiment: neurons critical for reasoning are deactivated, and alignment behavior is measured. Finding: the model's reasoning capacity degrades significantly, but its alignment behavior remains nearly unchanged. This supports the hypothesis that current alignment is grounded in shallow pattern recognition (detecting surface markers of harm) rather than genuine reasoning. To fix this, the paper constructs and releases a Chain-of-Thought (CoT) alignment fine-tuning dataset pairing harmful and safe prompts with step-by-step reasoning traces. SFT on this dataset produces principled refusals grounded in reasoning, outperforming standard SFT baselines. However, CoT SFT alone has failure modes: correct reasoning with unsafe final answers, and incorrect reasoning that accidentally produces safe answers. This motivates **Alignment-Weighted DPO (AW-DPO)**, which decomposes each response into a reasoning segment and an answer segment, assigning distinct preference weights to each based on their safety implications. This enables finer-grained optimization than vanilla DPO, which treats the entire response uniformly. Experiments across multiple safety and utility benchmarks show improved robustness to diverse jailbreak strategies without significant utility degradation. From UVA and Capital One.

### Key Takeaways
- Current LLM safety alignment is not grounded in reasoning — disabling reasoning neurons leaves alignment largely intact, exposing it as pattern recognition.
- Chain-of-thought fine-tuning with safety reasoning traces is a meaningful first step, but segment-level DPO weighting is needed to handle the mismatch between reasoning quality and answer safety.
- AW-DPO improves robustness to indirect, obfuscated, and logically complex jailbreak attacks that defeat pattern-matching defenses.

---

## 9. Adversarial Intent is a Latent Variable: Stateful Trust Inference for Securing Multimodal Agentic RAG

**Authors:** Inderjeet Singh, Vikas Pahuja, Aishvariya Priya Rathina Sabapathy, Chiara Picardi, Amit Giloni, Roman Vainshtein, Andrés Murillo, Hisashi Kojima, Motoyoshi Sekiya, Yuki Unno, Junichi Suga
**Link:** [Adversarial Intent is a Latent Variable](https://arxiv.org/abs/2602.21447)
**Tags:** cs.CR

### Summary
Agentic RAG systems face a fundamentally different threat model than conventional LLMs: adversarial content can enter at multiple pipeline stages — poisoned documents in knowledge stores, directive-encoding images, indirect prompt injections in tool outputs, and subverted reasoning chains. Current defenses (Llama Guard, NeMo Guardrails, retrieval-stage filters) evaluate artifacts in isolation, discarding the interaction history needed to detect distributed attacks whose components each appear benign. The paper formalizes this as a POMDP where adversarial intent is a latent variable inferred from noisy, sequential multi-stage observations. This formulation yields a key theoretical result: stateless multi-point intervention can provide zero marginal benefit when checkpoint detection events are perfectly correlated (proven in Propositions 1 and 2). The proposed defense is **MMA-RAG^T**, governed by a **Modular Trust Agent (MTA)** that maintains a cumulative belief state Φ_t via structured LLM reasoning across five configurable checkpoints, issuing APPROVE / MITIGATE / REFUSE decisions that gate artifact passage. Evaluated on 43,774 instances across five threat surfaces in the ART-SafeBench suite, MMA-RAG^T achieves a 6.50× average reduction in Attack Success Rate relative to undefended baselines, with negligible utility cost. The statefulness ablation shows +26.4 pp improvement from belief tracking alone. From Fujitsu Research (UK and Japan).

### Key Takeaways
- Distributed adversarial attacks that spread malicious semantics across pipeline stages defeat stateless defenses — statefulness is a necessary architectural property, not an optimization.
- The POMDP formulation provides a rigorous foundation for RAG security and identifies when adding more checkpoints is redundant (correlated observations).
- A 6.5× reduction in attack success rate with negligible utility cost makes MMA-RAG^T immediately relevant for real deployments of agentic RAG systems.

---

## 10. Black-Box Reliability Certification for AI Agents via Self-Consistency Sampling and Conformal Calibration

**Authors:** Charafeddine Mouzouni
**Link:** [Black-Box Reliability Certification for AI Agents](https://arxiv.org/abs/2602.21368)
**Tags:** cs.LG

### Summary
Practitioners deploying AI agents need a concrete, trustworthy measure of reliability before going to production — not vague accuracy numbers computed on benchmark sets that may not reflect deployment distributions. This paper introduces the **reliability level**: a single number per system-task pair that serves as a deployment gate with formal, finite-sample, distribution-free coverage guarantees. The method combines two ingredients. **Self-consistency sampling** queries the same system K times and ranks answers by frequency, reducing variance exponentially (Theorem 4.4). **Conformal calibration** converts these frequency signals into a coverage certificate: a human spot-checks only 50-100 items, and the framework outputs a reliability level whose validity holds regardless of the agent's systematic bias profile (Theorem 7.3). Crucially, agent bias is not hidden — it becomes visible through larger prediction sets on hard questions. Validated across five benchmarks, five models (GPT-4.1, GPT-4.1-nano, Llama 4 Maverick, Mistral Small 24B, and one more), and three model families: GPT-4.1 earns 94.6% on GSM8K and 96.8% on TruthfulQA; GPT-4.1-nano earns 89.8% on GSM8K and 66.5% on MMLU. Sequential stopping reduces API costs by ~50%. Conditional coverage on solvable items exceeds 0.93 across all configurations, and under-coverage is predicted (not hidden) by the theory when tasks exceed model capability. From OPIT and Cohorte AI.

### Key Takeaways
- A formal, black-box deployment gate requiring only API access and ~50-100 human spot-checks is now achievable with finite-sample, distribution-free guarantees.
- Self-consistency sampling reduces uncertainty variance exponentially; conformal calibration provides coverage validity independent of model bias.
- The framework makes model limitations transparent rather than hiding them in misleading aggregate accuracy scores, supporting responsible deployment decisions.

---

## 11. The Headless Firm: How AI Reshapes Enterprise Boundaries

**Authors:** Tassilo Klein, Sebastian Wieczorek
**Link:** [The Headless Firm](https://arxiv.org/abs/2602.21401)
**Tags:** cs.GT

### Summary
Building on Coase's theory that firm boundaries are set by coordination costs, this paper argues that agentic AI induces a structural change in the scaling regime of coordination. In prior modular systems (SOA, microservices), coordination costs grew with interaction topology — roughly O(n²) in the number of components — because each integration required bilateral negotiation, release coupling, and governance dependencies. In protocol-mediated agentic systems, a larger share of integration shifts to standardized tool access and outcome-based verification, collapsing coordination scaling to O(n) while verification scales with task throughput rather than interaction count. This shift selects for an "hourglass" organizational equilibrium: a personalized generative interface (Generative UI) at the top, a thin standardized protocol waist in the middle, and a competitive market of micro-specialized execution agents at the bottom. The paper formalizes this as a coordination cost model with two falsifiable empirical predictions: (1) the marginal cost of adding an execution provider should be approximately constant in a mature hourglass ecosystem; (2) the ratio of total coordination cost to task throughput should remain stable as ecosystem size grows. The analysis predicts a domain-conditional "Great Unbundling" where high knowledge-velocity domains see firm size distributions shift from large integrated incumbents toward micro-specialized agents and thin protocol orchestrators. From Mantix (the authors have a conflict of interest as founders of an agentic enterprise infrastructure company, which is transparently declared).

### Key Takeaways
- Agentic AI changes coordination scaling from O(n²) topology-dominated to O(n) throughput-dominated, making micro-specialized modular agents economically viable at scale for the first time.
- The "Headless Firm" hourglass structure (GenUI / protocol waist / execution agents) is predicted as the stable organizational equilibrium, with conditions derived for re-centralization.
- High knowledge-velocity industries (software, finance, research) are predicted to experience the most dramatic unbundling, while low-velocity industries may recentralize.

---

## 12. ECHOSAT: Estimating Canopy Height Over Space and Time

**Authors:** Jan Pauls, Karsten Schrödter, Sven Ligensa, Martin Schwartz, Berkant Turan, Max Zimmer, Sassan Saatchi, Sebastian Pokutta, Philippe Ciais, Fabian Gieseke
**Link:** [ECHOSAT](https://arxiv.org/abs/2602.21421)
**Tags:** cs.CV

### Summary
Forests absorb ~3.5 Pg of carbon per year — nearly half of anthropogenic fossil fuel emissions — making accurate forest monitoring critical for climate policy. Existing global tree height maps provide only static single-year snapshots: they cannot track year-to-year carbon dynamics, growth, or disturbances. ECHOSAT addresses this by producing the first global, temporally consistent tree height map at 10 m resolution spanning seven years (2018–2024). A specialized vision transformer is trained on multi-sensor satellite data (combining Sentinel-2, ICESat-2 lidar reference measurements, and others) to perform pixel-level temporal regression. A key technical contribution is a novel **growth loss** that enforces physically realistic forest growth curves: predictions must reflect gradual height increases over time, but can also capture abrupt declines from fires or deforestation. This addresses the sparse, irregularly distributed ground truth labels (both spatially and temporally) that plague temporal forest regression. ECHOSAT outperforms state-of-the-art single-year methods on held-out evaluation sets while also capturing temporal dynamics that no prior global model inherently learned. Applications span carbon accounting, disturbance assessment, REDD+ monitoring, and climate policy. From University of Münster, LSCE (France), Zuse Institute Berlin, and JPL/Caltech.

### Key Takeaways
- Temporally consistent global tree height maps are essential for accurate carbon accounting; ECHOSAT is the first to deliver this at 10 m resolution over multiple years.
- The growth loss framework provides a general technique for training temporal regression models with sparse, irregularly labeled ground truth — applicable beyond forest monitoring.
- ECHOSAT outperforms single-year state-of-the-art methods even on single-year tasks, suggesting temporal context improves spatial accuracy as well.

---

## 13. Virtual Biopsy for Intracranial Tumors Diagnosis on MRI

**Authors:** Xinzhe Luo, Shuai Shao, Yan Wang, Jiangtao Wang, Yutong Bai, Jianguo Zhang
**Link:** [Virtual Biopsy for Intracranial Tumors](https://arxiv.org/abs/2602.21613)
**Tags:** cs.CV

### Summary
Deep intracranial tumors located in eloquent brain regions controlling vital functions (brainstem, basal ganglia, thalamus) cannot be safely surgically resected. Clinical practice requires stereotactic biopsy before treatment, but biopsy carries risks of hemorrhage and neurological deficits, and suffers from sampling bias due to tumor spatial heterogeneity — a small biopsy sample may not represent the whole mass. This paper proposes a deep learning-based **Virtual Biopsy framework** for non-invasive MRI-based pathology prediction, comprising three components: **MRI-Processor** for multi-sequence standardization and preprocessing, **Tumor-Localizer** using vision-language models for coarse-to-fine lesion localization via weak supervision (no segmentation masks needed), and **Adaptive-Diagnoser** with a Masked Channel Attention (MCA) mechanism that fuses local discriminative features with global MRI context. To address the data scarcity problem (low tumor incidence, long collection cycles, expert annotation requiring biopsy-verified pathology), the authors construct and release **ICT-MRI**, the first public biopsy-verified benchmark with 249 cases across four tumor categories. The framework achieves >90% diagnostic accuracy, outperforming baselines by more than 20 percentage points. This could substantially reduce unnecessary invasive procedures and complement traditional biopsy with holistic tumor assessment. From USTC.

### Key Takeaways
- Non-invasive MRI-based pathology prediction for deep intracranial tumors is clinically urgent and now achievable at >90% accuracy with VLM-guided localization.
- The ICT-MRI dataset — the first public biopsy-verified benchmark for this category — is a significant community contribution that enables future research.
- The Masked Channel Attention mechanism addresses the specific challenge of tiny lesion volumes being overwhelmed by background noise in MRI scans.

---

## 14. LiLo-VLA: Compositional Long-Horizon Manipulation via Linked Object-Centric Policies

**Authors:** Yue Yang, Shuo Cheng, Yu Fang, Homanga Bharadhwaj, Mingyu Ding, Gedas Bertasius, Daniel Szafir
**Link:** [LiLo-VLA](https://arxiv.org/abs/2602.21531)
**Tags:** cs.RO

### Summary
General-purpose robot manipulation requires long-horizon tasks involving multiple kinematic structure changes (picking, attaching, detaching, pouring) in unstructured environments. Current Vision-Language-Action (VLA) models face two fundamental problems: (1) lack of compositional generalization — they cannot flexibly recombine learned skills for novel task sequences not seen during training, and (2) cascading failures — a single error at any stage corrupts all subsequent steps since VLA policies overfit to specific visual configurations. LiLo-VLA (Linked Local VLA) addresses both by decoupling manipulation into two phases: a **Reaching Module** using classical motion planning for global navigation to target vicinity, and an **Interaction Module** using an **object-centric VLA** that processes only the isolated object of interest, ensuring invariance to global workspace layout and irrelevant visual features. The object-centric design enables zero-shot compositional generalization: learned atomic skills can be reused and recombined for novel long-horizon task sequences without task-specific demonstrations. A dynamic replanning mechanism handles cascading failures by detecting when a skill fails and replanning from the new (potentially altered) scene state. Evaluated on a 21-task simulation benchmark (LIBERO-Long++ and Ultra-Long suites), LiLo-VLA achieves 69% average success, outperforming Pi0.5 by 41% and OpenVLA-OFT by 67%. Real-world evaluation across 8 long-horizon tasks achieves 85% average success rate. From UNC, Georgia Tech, and CMU.

### Key Takeaways
- Decoupling transport (classical motion planning) from interaction (object-centric VLA) is a powerful architectural principle that enables both compositional generalization and failure recovery.
- Object-centric observation spaces — showing only the object of interest — make VLA policies invariant to workspace layout variations, dramatically improving robustness.
- 85% real-world success on 8 long-horizon tasks, with zero-shot generalization, represents a significant advance for deployable general-purpose manipulation.

---

## 15. ImpRIF: Stronger Implicit Reasoning Leads to Better Complex Instruction Following

**Authors:** Yuancheng Yang, Lin Yang, Xu Wang, Chao Tong, Haihua Yang
**Link:** [ImpRIF](https://arxiv.org/abs/2602.21228)
**Tags:** cs.CL

### Summary
Real-world user instructions are rarely flat or explicit. They contain multi-hop reasoning constraints, conditional logic, nested dependencies, and implicit premises — e.g., "include a list of length equal to the number of brains of an octopus" or "characters within the range of the number of letters in the Cyrillic alphabet × 2." Current LLM instruction following research focuses on relatively well-structured, weakly constrained instructions. ImpRIF targets the harder case of **implicit reasoning instructions** where correctly identifying execution constraints requires background knowledge, logical inference, or multi-step reasoning embedded between the lines. The method formalizes such instructions as **Explicit Reasoning Graphs (ERGs)**: nodes are concrete, programmatically verifiable actions (conditional judgments, knowledge inference, mathematical computation), and edges encode dependency relations. Large-scale single- and multi-turn datasets are synthesized with controllable complexity over ERGs. Fine-tuning uses graph-based chain-of-thought reasoning as supervision. Finally, a **multi-reward reinforcement learning** stage explicitly trains models to reason along the graph structure, leveraging the structural properties of ERGs to define fine-grained reward signals. Evaluated on five complex instruction following benchmarks, models trained with ImpRIF substantially outperform their base models. From ByteDance and Beihang University.

### Key Takeaways
- Formalizing implicit reasoning constraints as explicit reasoning graphs enables both programmatic verification and structured fine-tuning targets — a clean problem decomposition.
- The distinction between explicit and implicit instruction complexity is underexplored; implicit reasoning (requiring world knowledge and inference) is qualitatively harder than multi-constraint following.
- Graph-based multi-reward RL over programmatically verifiable reasoning steps provides precise training signal for a problem class where global outcome rewards are insufficient.

---
