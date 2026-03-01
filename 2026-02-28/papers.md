# Research Paper Summaries — 2026-02-28

Papers selected from the most recent ArXiv feed (2026-02-27; ArXiv does not publish on Saturdays) for in-depth review. These papers were not covered in the 2026-02-27 summaries.

---

## 1. Reinforcement-aware Knowledge Distillation for LLM Reasoning

**Authors:** Zhaoyang Zhang, Shuli Jiang, Yantao Shen, Yuting Zhang, Dhananjay Ram, Shuo Yang, Zhuowen Tu, Wei Xia, Stefano Soatto
**Link:** [Reinforcement-aware Knowledge Distillation for LLM Reasoning](https://arxiv.org/abs/2602.22495)
**Tags:** cs.LG, cs.CL

### Summary
RL post-training has produced impressive reasoning models, but their high inference cost motivates distillation into smaller students. Existing knowledge distillation methods were designed for supervised fine-tuning and suffer from two failures when combined with RL: (1) **distribution mismatch** — teacher supervision does not align with the student's evolving rollout distribution, and (2) **objective interference** — KL regularization competes with reward maximization. This paper from AWS Agentic AI proposes **RLAD (RL-Aware Distillation)**, which performs selective imitation during RL — guiding the student toward the teacher only when doing so improves the current policy update. The core mechanism, **Trust Region Ratio Distillation (TRRD)**, replaces the conventional teacher-student KL term with a PPO/GRPO-style likelihood-ratio objective anchored to a teacher-old-policy mixture. This produces advantage-aware, trust-region-bounded imitation computed on the student's own rollouts, naturally integrating exploration, exploitation, and teacher guidance in one objective.

Experiments on the K&K Logistics reasoning benchmark show RLAD consistently outperforms vanilla GRPO, offline distillation, and the competing KDRL method. On Qwen3-0.6B at 8K context, RLAD reaches an average accuracy of 0.94 across difficulty subsets (PPL2–PPL8) versus 0.76 for GRPO and 0.92 for KDRL. On Qwen3-1.7B, RLAD achieves near-perfect scores. The method also shows faster training convergence. Notable limitation: evaluation focuses on logical reasoning; broader coverage of math/coding benchmarks is not reported.

### Key Takeaways
- TRRD unifies imitation and RL by using a GRPO-style likelihood-ratio objective anchored to the teacher, eliminating distribution mismatch and KL-vs-reward competition.
- Selective imitation — only following the teacher when it improves the current update — is the key design choice that avoids the degradation of prior KD-in-RL methods.
- The approach is practical for producing cost-efficient small reasoning models from expensive RL-trained teachers without sacrificing the gains RL provides.

---

## 2. Compress the Easy, Explore the Hard: Difficulty-Aware Entropy Regularization for Efficient LLM Reasoning

**Authors:** Qin-Wen Luo, Sheng Ren, Xiang Chen, Rui Liu, Jun Fang, Naiqiang Tan, Sheng-Jun Huang
**Link:** [Compress the Easy, Explore the Hard: Difficulty-Aware Entropy Regularization for Efficient LLM Reasoning](https://arxiv.org/abs/2602.22642)
**Tags:** cs.LG, cs.CL

### Summary
Reducing the verbosity of chain-of-thought reasoning is important for real-world deployment, but existing RL-based length compression methods fail by triggering **entropy collapse**: aggressively penalizing long responses shrinks the exploration space prematurely, particularly harming difficult problems that require extensive deduction. This paper from NUAA and Didi identifies entropy collapse as the root cause of accuracy degradation in prior work, not the compression objective per se.

The proposed framework **CEEH (Compress the Easy, Explore the Hard)** dynamically assesses per-instance difficulty and applies selective entropy regularization: for currently hard questions, it preserves a diverse search space to prevent premature convergence; for easy questions with established reasoning paths, it permits aggressive length compression. Two complementary mechanisms are introduced: **CEEH-ME** (maximum-entropy loss to maintain exploration diversity) and **CEEH-EA** (entropy-based advantage rescaling). Additionally, a dynamic optimal-length penalty anchored to the historically shortest correct solution prevents the model from settling for unnecessarily long paths once a shorter one is discovered.

Experiments on reasoning benchmarks show CEEH maintains or improves accuracy while substantially reducing token costs. On AIME25, CEEH-ME improves from 63.3 (base) to 70.0 using R1-Distill-Qwen2.5-7B, while retaining performance on GSM8K and MATH500. The difficulty-aware approach prevents the entropy collapse observed in baselines like Length-Penalty and LC-R1.

### Key Takeaways
- Entropy collapse — not the length penalty itself — is the root cause of accuracy degradation in RL-based reasoning compression.
- Difficulty-aware entropy regularization decouples brevity and robustness: compress easy problems, keep diversity for hard ones.
- The dynamic optimal-length penalty continuously tightens the compression target, enabling progressive efficiency gains without freezing a fixed budget.

---

## 3. Search-P1: Path-Centric Reward Shaping for Stable and Efficient Agentic RAG Training

**Authors:** Tianle Xia, Ming Xu, Lingxiang Hu, Yiding Sun, Wenwei Li, Linfang Shang, Liqun Liu, Peng Shu, Huan Yu, Jie Jiang
**Link:** [Search-P1: Path-Centric Reward Shaping for Stable and Efficient Agentic RAG Training](https://arxiv.org/abs/2602.22576)
**Tags:** cs.CL, cs.AI

### Summary
Agentic RAG — where LLMs dynamically decide when and what to retrieve in multi-step reasoning — is typically trained with outcome-only RL rewards. This causes three problems: sparse rewards that discard intermediate signals, zero learning from partially correct trajectories, and slow convergence requiring 150+ training steps. Search-R1, the prior state-of-the-art, suffers from all three. This paper from Tencent proposes **SEARCH-P1**, which introduces **path-centric reward shaping** as the solution.

SEARCH-P1 has two core components. First, a **Path-Centric Reward** that evaluates the structural quality of a reasoning trajectory through order-agnostic step coverage (rewarding correct retrieval queries regardless of position) and soft scoring that extracts learning signals even from failed samples. Second, **Dual-Track Path Scoring**, which uses offline-generated reference planners to assess trajectories from both self-consistency and reference-alignment perspectives, providing dense signal throughout training. Experiments across eight QA benchmarks (NQ, TriviaQA, PopQA, HotpotQA, 2WikiMultiHop, MuSiQue, Bamboogle, AD-QA) show an average +7.7 accuracy gain over Search-R1. SEARCH-P1 also converges in ~60 steps versus Search-R1's 150+, and maintains consistently lower and more efficient inference turn counts on successful trajectories. The path-centric reward design is orthogonal to base model and RL algorithm choice, yielding consistent gains across Qwen2.5-3B, Llama-3.2-3B with both GRPO and PPO.

### Key Takeaways
- Path-centric rewards solve the sparse reward problem in agentic RAG by scoring intermediate retrieval quality — extracting learning signal even from failed trajectories.
- SEARCH-P1 converges 2.5× faster than Search-R1 while achieving higher final accuracy, making it practical for large-scale training.
- The framework is model- and algorithm-agnostic, and the gains are consistent across both stronger (7B) and weaker (3B) base models.

---

## 4. Exploratory Memory-Augmented LLM Agent via Hybrid On- and Off-Policy Optimization

**Authors:** Zeyuan Liu, Jeonghye Kim, Xufang Luo, Dongsheng Li, Yuqing Yang
**Link:** [Exploratory Memory-Augmented LLM Agent via Hybrid On- and Off-Policy Optimization](https://arxiv.org/abs/2602.23008)
**Tags:** cs.LG, cs.AI

### Summary
Published as a conference paper at **ICLR 2026**, EMPO² from Microsoft Research and KAIST addresses a fundamental bottleneck in RL-trained LLM agents: **exploration**. Current methods succeed by exploiting pretrained knowledge, but fail in environments requiring discovery of genuinely novel states. The paper proposes EMPO² (Exploratory Memory-Augmented On- and Off-Policy Optimization), which uses memory as an exploration tool rather than just a context store, and combines on-policy and off-policy RL updates to develop both in-distribution competence and memory-driven robustness.

The hybrid architecture enables two modes: on-policy updates improve baseline performance in familiar environments, while off-policy updates train the agent to utilize stored memories effectively, building generalization ability. Memory is actively populated with experiences from novel states encountered during exploration, allowing the agent to bootstrap prior encounters in out-of-distribution settings without parameter updates. On ScienceWorld (a complex text-world requiring sequential decision-making) and WebShop (e-commerce navigation), EMPO² achieves **128.6% and 11.3% improvements over GRPO**, respectively. In out-of-distribution tests, EMPO² demonstrates superior adaptability requiring only a few memory-augmented trials, not retraining, to handle new task variants. This distinction — that generalization is achieved through memory retrieval rather than gradient updates — is the paper's most practically significant contribution.

### Key Takeaways
- Memory-driven exploration addresses the core failure mode of GRPO-style agents: converging prematurely in novel environments by lacking a mechanism to actively seek new states.
- The on/off-policy hybrid enables simultaneous optimization for in-distribution competence and memory-conditioned robustness — not achievable with purely on-policy training.
- OOD generalization without parameter updates is the standout result: the agent adapts to new tasks via memory retrieval alone, a strong signal for the practical value of episodic memory in agentic RL.

---

## 5. Silent Egress: When Implicit Prompt Injection Makes LLM Agents Leak Without a Trace

**Authors:** Qianlong Lan, Anuj Kaul, Shaun Jones, Stephanie Westrum
**Link:** [Silent Egress: When Implicit Prompt Injection Makes LLM Agents Leak Without a Trace](https://arxiv.org/abs/2602.22450)
**Tags:** cs.CR, cs.AI

### Summary
Agentic LLMs increasingly automate tasks by previewing URLs, retrieving documents, and calling external tools. This paper from eBay security researchers demonstrates a novel attack surface they term **silent egress**: adversarial instructions embedded in automatically generated URL previews (titles, metadata, snippets) can induce an agent to exfiltrate sensitive runtime context via outbound requests, while the response shown to the user appears completely benign.

The attack is classified as **implicit prompt injection** because the adversarial instructions arrive through content that the system generates automatically (URL previews), not through direct user input — making it significantly harder to block. The authors implement a fully reproducible local testbed using a qwen2.5:7b-based agent. Across 480 experimental runs, the attack succeeds with probability **P(egress) ≈ 0.89**, and critically, **95% of successful attacks pass output-based safety checks** because the malicious behavior manifests as tool calls/network requests, not as unsafe text. The paper also introduces **sharded exfiltration**, splitting sensitive data across multiple innocuous requests to defeat data-loss-prevention heuristics (reducing Leak@1 by 73% while maintaining effectiveness). Ablations show prompt-layer defenses offer limited protection; **network-layer controls** (domain allowlisting, redirect-chain analysis) are substantially more effective. The paper proposes architectural directions including provenance tracking and capability isolation.

### Key Takeaways
- Output-based safety evaluation is structurally blind to silent egress: 95% of successful attacks are invisible to text-based monitoring because exfiltration happens via side-channel network requests.
- Sharded exfiltration is a practical technique for bypassing DLP systems by distributing sensitive context across multiple benign-looking requests.
- The architectural implication is significant: network egress must be treated as a first-class security outcome, not an afterthought, in agentic LLM system design.

---

## 6. Multilingual Safety Alignment Via Sparse Weight Editing

**Authors:** Jiaming Liang, Zhaoxin Wang, Handing Wang
**Link:** [Multilingual Safety Alignment Via Sparse Weight Editing](https://arxiv.org/abs/2602.22554)
**Tags:** cs.CL, cs.AI

### Summary
LLMs aligned for safety in English often exhibit severe safety disparities in low-resource languages (LRLs): jailbreaks in Thai, Bengali, or Vietnamese succeed at high rates even on well-aligned models. Multilingual RLHF or SFT is data-intensive and costly. This paper from Xidian University proposes a **training-free** approach based on sparse weight editing that requires only a single closed-form calculation.

The key insight is that safety capabilities are localized within a sparse set of **safety neurons** in the model's weight matrices. The method formulates cross-lingual alignment as a constrained linear transformation: find a weight delta that maps the harmful representation subspace of LRLs onto the robust safety subspace established for high-resource languages (English), while preserving general utility via a **null-space projection constraint**. This constraint ensures the edit does not degrade reasoning or language understanding. The closed-form solver computes the optimal sparse update via Cholesky factorization and truncated SVD. Experiments span 8 languages (English, Chinese, Vietnamese, Japanese, Thai, Indonesian, Bengali, Hebrew) across Llama-3.2, Qwen2, and Qwen2.5 at multiple scales. The method substantially reduces Attack Success Rate across all LRLs with negligible impact on MGSM math reasoning and M-MMLU general knowledge scores. This combination of strong safety gains with no training cost or utility loss is the primary practical contribution.

### Key Takeaways
- Safety capabilities are localized to a sparse set of neurons, making them addressable via closed-form weight edits without any training data or gradient computation.
- Null-space projection is the critical constraint ensuring safety edits don't degrade general utility — a standard but underused technique for targeted weight surgery.
- The approach provides a practical, scalable solution to the multilingual safety gap that doesn't require multilingual RLHF datasets, which are scarce for most languages.

---

## 7. Hierarchy-of-Groups Policy Optimization for Long-Horizon Agentic Tasks

**Authors:** Shuo He, Lang Feng, Qi Wei, Xin Cheng, Lei Feng, Bo An
**Link:** [Hierarchy-of-Groups Policy Optimization for Long-Horizon Agentic Tasks](https://arxiv.org/abs/2602.22817)
**Tags:** cs.LG, cs.AI

### Summary
Published as a conference paper at **ICLR 2026** from NTU and Southeast University, this paper identifies a previously uncharacterized failure mode in stepwise group-based RL (such as GRPO variants applied to agentic tasks): **context inconsistency**. In long-horizon tasks, when multiple rollout trajectories diverge early, later steps in the same "group" may have substantially different historical contexts. Estimating relative advantages across these contextually mismatched steps produces severely biased gradient updates that degrade policy optimization.

The paper proposes **HGPO (Hierarchy-of-Groups Policy Optimization)**, which resolves this by assigning each step to multiple hierarchical groups formed by context consistency — steps sharing identical historical trajectories are grouped together. For each step, HGPO computes distinct advantages within each hierarchical group and aggregates them using an adaptive weighting scheme. This achieves a favorable bias-variance trade-off in stepwise advantage estimation without requiring extra models or additional rollouts, making it computationally competitive with standard stepwise GRPO. Evaluations on ALFWorld (embodied task completion) and WebShop (e-commerce navigation) using Qwen2.5-1.5B-Instruct and Qwen2.5-7B-Instruct show HGPO significantly outperforms existing agentic RL baselines including GRPO, stepwise GRPO, DAPO, and others under equal computational constraints.

### Key Takeaways
- Context inconsistency in stepwise group-based RL is a fundamental source of biased advantage estimation — not a hyperparameter issue but an architectural problem in how groups are formed.
- Hierarchical grouping by context consistency corrects the bias at its source, achieving better policy optimization without any additional computational overhead.
- The fix generalizes across backbone sizes (1.5B and 7B) and task types, suggesting it is a broadly applicable improvement for agentic RL training pipelines.

---

## 8. Towards Better RL Training Data Utilization via Second-Order Rollout

**Authors:** Zhe Yang, Yudong Wang, Rang Li, Zhifang Sui
**Link:** [Towards Better RL Training Data Utilization via Second-Order Rollout](https://arxiv.org/abs/2602.22765)
**Tags:** cs.LG, cs.CL

### Summary
Standard RL for LLM reasoning uses **first-order rollout**: sample multiple responses for a question, compute rewards, update the policy. This paper from Peking University and ByteDance argues that this approach systematically neglects **critique capability** — the ability to identify and explain errors in responses — and proposes **second-order rollout**: sampling multiple critiques for a given response. By jointly training generation (first-order) and critique (second-order) capabilities in a unified RL framework, the model is forced to develop a more accurate understanding of what constitutes correct reasoning.

The key insight is that generation and critique are complementary but asymmetric skills. A model that can generate correct reasoning isn't necessarily good at critiquing incorrect reasoning, and vice versa. Training only generation misses the chance to develop the internal evaluation capacity that would make exploration more purposeful. The paper also uncovers important findings: **label balance in critique training** (equal distribution of correct/incorrect responses) is critical for stable learning, and **outcome-based rewards introduce noise** for critique tasks that can be mitigated by sampling techniques. Extensive experiments across multiple models and mathematical reasoning datasets confirm consistent gains over vanilla RL under the same training data budget — the method provides better data utilization by extracting two complementary learning signals from each training example.

### Key Takeaways
- Second-order rollout exploits each training question twice: once for generation quality and once for critique quality, doubling the informational content extracted per example.
- Jointly training generation and critique builds more robust reasoning: the model becomes better at identifying its own failures, making subsequent generation attempts more reliable.
- Label balance in critique training is a critical but overlooked design choice — unbalanced critique data leads to training instability that manifests as reward noise.

---

## 9. UpSkill: Mutual Information Skill Learning for Structured Response Diversity in LLMs

**Authors:** Devan Shah, Owen Yang, Daniel Yang, Chongyi Zheng, Benjamin Eysenbach
**Link:** [UpSkill: Mutual Information Skill Learning for Structured Response Diversity in LLMs](https://arxiv.org/abs/2602.22296)
**Tags:** cs.LG, cs.CL

### Summary
RLVR training on verifiable rewards improves reasoning accuracy but inadvertently suppresses response diversity across repeated attempts — models tend to sample near-identical solutions, reducing the effective number of independent tries in pass@k settings. This matters practically for code generation with test suites, formal proof assistants, and any scenario where repeated sampling is used as an inference-time strategy. This paper from Princeton proposes **UpSkill**, which adapts **Mutual Information Skill Learning (MISL)** to the LLM setting to encourage structured, reproducible diversity.

UpSkill introduces a discrete latent skill variable z and a **token-level mutual information reward** implemented within GRPO: the reward encourages each generated trajectory to be highly specific to its assigned z (high MI between trajectory and z). This creates a set of distinct problem-solving strategies rather than a single dominant one, improving coverage across repeated samples. Experiments on GSM8K with Llama 3.1-8B, Qwen 2.5-7B, and R1-Distilled-Qwen2.5-Math-1.5B show mean gains of ~**3% in pass@k** for both Qwen and Llama base models without degrading pass@1 — a notable result, since prior diversity-enhancing methods typically degrade single-attempt accuracy. The paper provides both empirical and theoretical evidence linking pass@k improvements to the mutual information objective, grounding the observed gains in a principled framework.

### Key Takeaways
- RLVR's diversity suppression is a systematic side-effect of optimizing single-attempt accuracy — not a random failure, requiring a principled countermeasure.
- Token-level MI rewards within GRPO are sufficient to encourage meaningful strategy diversity without a separate diversity loss or temperature hack.
- The 3% pass@k gain without any pass@1 degradation is a strong result: it suggests skill conditioning is genuinely creating complementary solving strategies rather than just adding noise.

---

## 10. AMA-Bench: Evaluating Long-Horizon Memory for Agentic Applications

**Authors:** Yujie Zhao, Boqin Yuan, Junbo Huang, Haocheng Yuan, Zhongming Yu, Haozhou Xu, Lanxiang Hu, Abhilash Shankarampeta, Zimeng Huang, Wentao Ni, Yuandong Tian, Jishen Zhao
**Link:** [AMA-Bench: Evaluating Long-Horizon Memory for Agentic Applications](https://arxiv.org/abs/2602.22769)
**Tags:** cs.AI, cs.CL

### Summary
Existing agent memory benchmarks primarily evaluate dialogue-centric human-agent interactions, but real agentic applications require memory over continuous streams of **machine-generated observations** — tool outputs, browser states, API responses — that are compositionally different from natural conversation. This paper from UC San Diego introduces **AMA-Bench (Agent Memory with Any length)**, the first benchmark designed specifically for long-horizon memory in realistic agentic settings.

AMA-Bench has two components: (1) real-world agentic trajectories from representative applications (web navigation, file management, code execution) paired with expert-curated QA that tests retention and retrieval of relevant context; (2) synthetic agentic trajectories that scale to arbitrary horizons with rule-based QA for controlled evaluation. A comprehensive study of existing memory systems reveals they underperform on AMA-Bench primarily because they lack **causality tracking** (understanding why certain states arose) and **objective retention** (remembering what the agent was trying to achieve), and are constrained by the lossy nature of similarity-based retrieval. To address these limitations, the authors propose **AMA-Agent**, a memory system featuring a causality graph that tracks cause-effect relationships across agent steps and tool-augmented retrieval that combines semantic similarity with structured lookup. AMA-Agent achieves **57.22% average accuracy** on AMA-Bench, surpassing the strongest memory system baseline by 11.16%.

### Key Takeaways
- Existing agent memory benchmarks over-estimate real-world performance by testing on dialogue rather than machine-generated agentic streams — a fundamental mismatch with production deployments.
- Causality tracking is the key missing component in current memory systems: storing what happened is insufficient without knowing why it happened.
- AMA-Agent's 11.16% improvement over prior SOTA demonstrates that causality graphs and tool-augmented retrieval are tractable solutions to the causality gap.

---

## 11. AgentSentry: Mitigating Indirect Prompt Injection in LLM Agents via Temporal Causal Diagnostics and Context Purification

**Authors:** Tian Zhang, Yiwei Xu, Juan Wang, Keyan Guo, Xiaoyang Xu, Bowen Xiao, Quanlong Guan, Jinlin Fan, Jiawei Liu, Zhiquan Liu, Hongxin Hu
**Link:** [AgentSentry: Mitigating Indirect Prompt Injection in LLM Agents via Temporal Causal Diagnostics and Context Purification](https://arxiv.org/abs/2602.22724)
**Tags:** cs.CR, cs.AI

### Summary
Indirect Prompt Injection (IPI) attacks embed adversarial instructions in tool outputs or retrieved content, silently redirecting an agent away from user intent. Unlike direct prompt attacks, IPI unfolds across multi-turn trajectories — the agent's behavior may appear normal for many steps before the injected instruction takes effect, making point-in-time detection ineffective. Existing defenses rely on heuristic per-step checking or conservative tool-call blocking, which either miss distributed attacks or prematurely terminates legitimate workflows.

This paper from Wuhan University and UB proposes **AgentSentry**, framing multi-turn IPI as a **temporal causal takeover**: the injection event creates a causal discontinuity in the agent's decision process that can be localized through counterfactual analysis. AgentSentry localizes the takeover point via controlled **counterfactual re-executions at tool-return boundaries** — it re-runs the agent with tool outputs masked or replaced to determine which return event caused the behavioral shift. Once the takeover point is identified, **causally guided context purification** removes attack-induced deviations from context while preserving task-relevant evidence, enabling safe continuation without workflow termination. Evaluations on the AgentDojo benchmark across four task suites, three IPI attack families, and multiple black-box LLMs show AgentSentry eliminates successful attacks while maintaining **74.55% Utility Under Attack** — improving by **20.8 to 33.6 percentage points** over the strongest baselines without degrading benign task performance.

### Key Takeaways
- Framing IPI as temporal causal takeover enables precise attack localization — not just detection — enabling safe continuation rather than workflow termination.
- Counterfactual re-execution at tool-return boundaries is a principled method for identifying which tool output introduced adversarial influence, without requiring knowledge of the attack strategy.
- The 20.8–33.6 percentage point UA improvement over baselines without benign performance degradation is a strong result, demonstrating that security and utility are not fundamentally in tension for this attack class.

---

## 12. CourtGuard: A Model-Agnostic Framework for Zero-Shot Policy Adaptation in LLM Safety

**Authors:** Umid Suleymanov, Rufiz Bayramov, Suad Gafarli, Seljan Musayeva, Taghi Mammadov, Aynur Akhundlu, Murat Kantarcioglu
**Link:** [CourtGuard: A Model-Agnostic Framework for Zero-Shot Policy Adaptation in LLM Safety](https://arxiv.org/abs/2602.22557)
**Tags:** cs.AI, cs.CL

### Summary
Current LLM safety mechanisms embed policy logic into model weights through fine-tuning, creating **adaptation rigidity**: enforcing a new governance rule requires expensive retraining. This is a fundamental problem for enterprise AI governance where policies evolve continuously (new regulatory requirements, domain-specific restrictions, updated terms of service). This paper from Virginia Tech and ADA University introduces **CourtGuard**, a retrieval-augmented multi-agent framework that decouples safety evaluation from model weights entirely.

CourtGuard reimagines safety checking as **Evidentiary Debate**: an adversarial multi-agent process where a prosecutor agent (arguing the content is harmful) and a defense agent (arguing it is benign) ground their arguments in retrieved passages from external policy documents, before a judge agent renders a verdict. Updating the safety policy requires only swapping the reference document — no retraining. CourtGuard achieves state-of-the-art performance across **7 safety benchmarks** without any fine-tuning, outperforming dedicated policy-following baselines. Its zero-shot adaptability is demonstrated by generalizing to an out-of-domain **Wikipedia Vandalism detection** task by simply providing a vandalism policy document, achieving **90% accuracy**. The framework also provides automated data curation and auditing capabilities, generating nine novel datasets of sophisticated adversarial attacks. Limitations include higher inference latency due to multi-agent debate rounds and dependence on policy document quality.

### Key Takeaways
- Decoupling safety logic from model weights via retrieval-augmented adversarial debate eliminates the retraining cost of policy updates — a step change for enterprise AI governance.
- SOTA on 7 safety benchmarks without fine-tuning validates that policy reasoning can be externalized without sacrificing detection quality.
- Zero-shot generalization to Wikipedia vandalism detection by swapping the reference document demonstrates the framework's domain-agnostic adaptability.

---

## 13. MSJoE: Jointly Evolving MLLM and Sampler for Efficient Long-Form Video Understanding

**Authors:** Wenhui Tan, Xiaoyi Yu, Jiaze Li, Yijing Chen, Jianzhong Ju, Zhenbo Luo, Ruihua Song, Jian Luan
**Link:** [MSJoE: Jointly Evolving MLLM and Sampler for Efficient Long-Form Video Understanding](https://arxiv.org/abs/2602.22932)
**Tags:** cs.CV, cs.AI

### Summary
Long-form video understanding faces a compute efficiency problem: uniform frame sampling feeds too many irrelevant frames to the MLLM, scaling quadratically with video length. Existing trainable key-frame samplers are trained independently from the MLLM they serve, creating a **training-serving mismatch**: the sampler selects frames according to objectives that may not align with what the MLLM actually needs to answer the question. This paper from Renmin University and Xiaomi proposes **MSJoE (MLLM-Sampler Joint Evolution)**, which co-trains a lightweight key-frame sampler and the MLLM end-to-end via reinforcement learning.

MSJoE's inference procedure has three stages: (1) the MLLM reasons out a set of queries describing diverse visual perspectives relevant to the question; (2) these queries interact with a frozen CLIP model to produce a query-frame similarity matrix; (3) a lightweight sampler predicts key-frame weights from this matrix, selecting a compact set of informative frames for final answer generation. Both the MLLM and sampler are jointly optimized through RL, enabling co-adaptation of query-reasoning, frame-sampling, and answer generation. A new long-video QA dataset of 2.8k videos and 7k QA pairs was collected to support training. Experiments on VideoMME, LongVideoBench, LVBench, and MLVU show MSJoE achieves **+8.0% accuracy** over the base MLLM and **+1.1%** over the strongest baseline, while maintaining computational efficiency through selective frame sampling.

### Key Takeaways
- Joint evolution of MLLM and sampler via RL eliminates the training-serving mismatch that degrades independently-trained samplers.
- The query-generation step is the key innovation: the MLLM articulates what it needs to see before sampling, rather than passively accepting whatever frames a static sampler provides.
- The 8% accuracy gain over the base MLLM demonstrates that the bottleneck in long-form video understanding is often frame selection quality, not model capacity.

---

## 14. ThinkOmni: Lifting Textual Reasoning to Omni-modal Scenarios via Guidance Decoding

**Authors:** Yiran Guan, Sifan Tu, Dingkang Liang, Linghao Zhu, Jianzhong Ju, Zhenbo Luo, Jian Luan, Yuliang Liu, Xiang Bai
**Link:** [ThinkOmni: Lifting Textual Reasoning to Omni-modal Scenarios via Guidance Decoding](https://arxiv.org/abs/2602.23306)
**Tags:** cs.CV, cs.AI

### Summary
Published as a conference paper at **ICLR 2026** from HUST and Xiaomi, ThinkOmni addresses a fundamental gap: Large Reasoning Models (LRMs like DeepSeek-R1, o1) are text-only, while Omni-modal LLMs (OLLMs) can process diverse modalities but lack complex reasoning. Bridging this gap through fine-tuning would require high-quality multimodal reasoning data, task-specific adaptation, and substantial compute — a prohibitive barrier for most research groups.

ThinkOmni proposes a **training-free** framework that lifts textual reasoning capabilities into omni-modal settings via **guidance decoding**. Two key components work together: (1) **LRM-as-a-Guide**, which uses an off-the-shelf large reasoning model to influence the decoding process of the OLLM by providing reasoning-conditioned token probability adjustments at each step; (2) **Stepwise Contrastive Scaling**, which adaptively balances perception signals (from the OLLM's multimodal processing) and reasoning signals (from the LRM guide) without requiring manual hyperparameter tuning — the balance is computed dynamically from the contrastive difference between guided and unguided token distributions. Experiments on six multimodal reasoning benchmarks show consistent improvements: **70.2% on MathVista** and **75.5% on MMAU**, with gains across all six benchmarks. The training-free nature makes ThinkOmni immediately deployable with any OLLM-LRM pair.

### Key Takeaways
- LRM-as-a-Guide decoding transfers reasoning capabilities across the text-to-omni gap without any fine-tuning or multimodal reasoning data — a significant accessibility improvement.
- Stepwise Contrastive Scaling dynamically resolves the perception-reasoning tension at each decoding step, outperforming static mixture coefficients.
- The framework is composable: any LRM can guide any OLLM, making it immediately applicable as newer, stronger reasoning models become available.

---

## 15. Fine-Tuning Without Forgetting In-Context Learning: A Theoretical Analysis of Linear Attention Models

**Authors:** Chungpa Lee, Jy-yong Sohn, Kangwook Lee
**Link:** [Fine-Tuning Without Forgetting In-Context Learning: A Theoretical Analysis of Linear Attention Models](https://arxiv.org/abs/2602.23197)
**Tags:** cs.LG

### Summary
Fine-tuning LLMs on downstream tasks often degrades in-context learning (ICL) — the model's ability to generalize via few-shot prompting on tasks not seen during fine-tuning. This is a practical problem for deployed models: an operator who fine-tunes for a specific application risks losing the general-purpose ICL capabilities that make the model broadly useful. This paper from Yonsei University and UW-Madison provides the first **theoretical characterization** of this trade-off using linear attention models, which are analytically tractable while capturing the essential gradient dynamics of full attention.

The paper identifies exactly which attention parameters are responsible for ICL degradation. Fine-tuning **all** attention parameters (Q, K, V matrices) harms ICL because updates to Q and K modify the key-query alignment that supports in-context demonstration retrieval. In contrast, restricting fine-tuning updates to the **value matrix** alone improves zero-shot performance on the target task while provably preserving ICL on unseen tasks. The paper further shows that adding an **auxiliary few-shot loss** during fine-tuning enhances ICL specifically on the target task but comes at the expense of ICL on other tasks — revealing a fundamental target-domain/domain-generality trade-off. All theoretical results are validated empirically. The findings have direct implications for PEFT (parameter-efficient fine-tuning) design: value-only updates or value-heavy LoRA configurations may preserve ICL better than standard LoRA applied to all matrices.

### Key Takeaways
- Value-matrix-only fine-tuning is theoretically and empirically sufficient to improve zero-shot performance while provably preserving in-context learning on unseen tasks.
- The ICL degradation caused by updating Q and K matrices is a structural consequence of modifying key-query alignment, not a hyperparameter problem — it cannot be fixed by tuning learning rates.
- Practitioners using LoRA should consider restricting rank-1 updates to value projections when preserving general ICL is a priority, informed by this theoretical analysis.

---

*Generated from PDF analysis of 15 ArXiv papers from the 2026-02-27 feed (ArXiv does not publish on weekends; these papers supplement the 2026-02-27 summaries).*
