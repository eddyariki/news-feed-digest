# Research Paper Summaries — 2026-02-21

Papers selected from today's digest for in-depth review.

---

## 1. Formal Mechanistic Interpretability: Automated Circuit Discovery with Provable Guarantees

**Authors:** Itamar Hadad, Guy Katz, Shahaf Bassan
**Link:** https://arxiv.org/abs/2602.16823
**Tags:** cs.LG, cs.LO

### Summary
This paper addresses a fundamental limitation in mechanistic interpretability: existing automated circuit discovery methods rely on heuristics and approximations, offering no formal guarantees about the circuits they identify. The authors leverage recent advances in neural network verification to create the first provably correct framework for automated circuit discovery. Their approach identifies the internal components of neural networks responsible for specific behaviors with guarantees over continuous input domains — a significant step beyond prior methods that could only provide approximate results on discrete test sets.

The framework integrates verification tools with mechanistic interpretability, enabling circuit discovery with provable guarantees over input domains, patching domains, and minimality. This means the discovered circuits are formally verified to capture the target behavior across all possible inputs in a given domain, not just on sampled examples. The theoretical results establish a rigorous foundation for understanding which components of a neural network are truly responsible for specific computations, moving the field from empirical observation toward mathematical certainty.

### Key Takeaways
- First work to employ neural network verification strategies for circuit discovery in mechanistic interpretability
- Provides provable guarantees over continuous input domains, patching domains, and minimality — unlike all prior heuristic-based approaches
- Lays theoretical groundwork for a new paradigm of formally verified mechanistic interpretability research

---

## 2. Training Large Reasoning Models Efficiently via Progressive Thought Encoding

**Authors:** Zeliang Zhang, Xiaodong Liu, Hao Cheng, Hao Sun, Chenliang Xu, Jianfeng Gao
**Link:** https://arxiv.org/abs/2602.16839
**Tags:** cs.LG, cs.CL

### Summary
Large reasoning models (LRMs) achieve strong performance on complex problems but face a critical efficiency bottleneck: reinforcement learning training requires long rollouts for outcome-based rewards, where autoregressive decoding dominates both time and memory usage. While sliding-window cache strategies can bound memory, they disrupt long-context reasoning and degrade performance. This paper introduces Progressive Thought Encoding, a parameter-efficient fine-tuning method that enables LRMs to reason effectively under fixed-size caches.

The key insight is to progressively encode intermediate reasoning steps into fixed-size vector representations, eliminating the need to backpropagate through full-cache rollouts. This reduces memory usage while maintaining reasoning quality during both training and inference. Experiments on three models — Qwen2.5-3B-Instruct, Qwen2.5-7B-Instruct, and DeepSeek-R1-Distill-Llama-8B — across six challenging mathematical benchmarks show consistent and substantial gains: +19.3% improvement over LoRA-based fine-tuning and +29.9% over LRMs without fine-tuning on average, with up to +23.4 accuracy points on AIME2024/2025. This work from Microsoft Research directly addresses one of the most pressing practical barriers to scaling reasoning model training.

### Key Takeaways
- Progressive Thought Encoding compresses intermediate reasoning into fixed-size vectors, enabling constant-memory inference without quality loss
- Achieves +19.3% over LoRA and +29.9% over base LRMs on challenging math benchmarks
- Directly addresses the key bottleneck (memory/compute cost of long rollouts) blocking wider adoption of RL-trained reasoning models

---

## 3. Escaping the Cognitive Well: Efficient Competition Math with Off-the-Shelf Models

**Authors:** Xingyu Dang, Rohit Agarwal, Rodrigo Porto, Anirudh Goyal, Liam H Fowl, Sanjeev Arora
**Link:** https://arxiv.org/abs/2602.16793
**Tags:** cs.LG

### Summary
While custom math reasoning models have reached IMO gold medal performance, replicating this with publicly available models has required prohibitive costs — upwards of $3,000 per problem. This paper presents an inference pipeline that achieves state-of-the-art performance on IMO-style problems at orders of magnitude lower cost, using only general-purpose off-the-shelf models.

The authors identify a critical failure mode in solver-grader pipelines called the "Cognitive Well" — a phenomenon where iterative refinement converges to a wrong solution that both the solver and the pipeline's internal grader consider essentially correct. The pipeline escapes these cognitive wells through conjecture extraction: candidate lemmas are isolated from generated solutions and independently verified alongside their negations in a fresh environment, breaking the self-reinforcing error loop. On IMO-ProofBench Advanced (PB-Adv), the pipeline achieves 67.1% using Gemini 3.0 Pro at approximately $31 per question — more than doubling the success rate of the next best publicly accessible pipeline at a fraction of the cost. This demonstrates that careful inference design can substitute for specialized model training.

### Key Takeaways
- Identifies the "Cognitive Well" failure mode — iterative refinement converging to confidently wrong solutions that fool both solver and grader
- Achieves 67.1% on IMO-ProofBench Advanced at ~$31/problem, vs. $3,000/problem for prior methods — a ~100x cost reduction
- Shows that inference pipeline design with off-the-shelf models can match or exceed specialized math reasoning models

---

## 4. Arcee Trinity Large Technical Report

**Authors:** Varun Singh, Lucas Krauss, Sami Jaghouar, Matej Sirovatka, Charles Goddard, Fares Obied, Jack Min Ong, Jannik Straube, et al. (Arcee AI, DatologyAI, Prime Intellect teams)
**Link:** https://arxiv.org/abs/2602.17004
**Tags:** cs.LG, cs.CL

### Summary
This technical report presents Arcee Trinity, a family of sparse Mixture-of-Experts (MoE) language models released under Apache 2.0. The flagship Trinity Large has 400B total parameters with 13B activated per token, alongside Trinity Mini (26B total / 3B active) and Trinity Nano (6B total / 1B active). The architecture incorporates several modern design choices: interleaved local and global attention, gated attention, depth-scaled sandwich normalization, and sigmoid routing for the MoE layers.

A notable contribution is SMEBU (Soft-clamped Momentum Expert Bias Updates), a new MoE load balancing strategy for Trinity Large that improves expert utilization. All models were trained using the Muon optimizer — Trinity Large on 17 trillion tokens and the smaller variants on 10 trillion tokens — achieving zero loss spikes throughout training. Trinity Large reaches 87.2 on MMLU and competitive scores across coding (MBPP+), math (Minerva MATH500), commonsense reasoning (HellaSwag, WinoGrande), and knowledge benchmarks (TriviaQA, ARC Challenge, GPQA Diamond). The fully open-source release (weights, code, and training details) represents a significant contribution to the open-weight frontier model ecosystem.

### Key Takeaways
- 400B MoE model with only 13B parameters activated per token, achieving frontier-level performance efficiently
- Introduces SMEBU load balancing and achieves zero loss spikes across 17T tokens of training with Muon optimizer
- Fully open-source (Apache 2.0) with competitive benchmark results (87.2 MMLU), expanding the open-weight frontier model landscape

---

## 5. Fail-Closed Alignment for Large Language Models

**Authors:** Zachary Coalson, Beth Sohler, Aiden Gabriel, Sanghyun Hong
**Link:** https://arxiv.org/abs/2602.16977
**Tags:** cs.LG, cs.CR

### Summary
This paper identifies a fundamental structural weakness in current LLM alignment: modern refusal mechanisms are "fail-open." While existing safety training encodes refusal behaviors across multiple latent features, suppressing just a single dominant feature — via prompt-based jailbreaks — can cause alignment to collapse entirely, leading to unsafe generation. The analogy to engineering is direct: current safety mechanisms behave like a door that swings open when the lock breaks, rather than remaining shut.

Motivated by this analysis, the authors propose "fail-closed alignment" as a design principle for robust LLM safety. Under this paradigm, refusal mechanisms should remain effective even under partial failures, achieved through redundant, independent causal pathways for safety-relevant behaviors. Their mechanistic analyses confirm that models trained with their method encode multiple, causally independent refusal directions that prompt-based jailbreaks cannot suppress simultaneously. This reframes the LLM safety problem: rather than making any single refusal mechanism stronger, the key is ensuring that multiple independent mechanisms exist so that no single point of failure can bypass safety. The work provides both a diagnostic framework and a constructive training approach.

### Key Takeaways
- Reveals that current LLM alignment is structurally "fail-open" — suppressing one dominant refusal feature collapses all safety
- Proposes fail-closed alignment: redundant, causally independent refusal pathways that resist simultaneous suppression
- Shifts the LLM safety paradigm from strengthening individual mechanisms to engineering redundant, independent safety pathways

---

## 6. One-step Language Modeling via Continuous Denoising

**Authors:** Chanhyuk Lee, Jaehoon Yoo, Manan Agarwal, Sheel Shah, Jerry Huang, Aditi Raghunathan, Seunghoon Hong, Nicholas M. Boffi, Jinwoo Kim
**Link:** https://arxiv.org/abs/2602.16813
**Tags:** cs.CL, cs.AI

### Summary
Discrete diffusion language models have attracted interest for their potential to generate text faster than autoregressive models, but they exhibit sharp quality degradation in the few-step regime. This paper challenges the prevailing assumption that discrete diffusion processes are necessary for generative modeling over discrete modalities like text. The authors demonstrate that flow-based continuous denoising over one-hot token encodings can outperform discrete diffusion in both quality and speed.

The approach builds a Flow-based Language Model (FLM) that performs Euclidean denoising over one-hot token encodings and is trained via a cross-entropy objective. A key technical contribution is a simple time reparameterization that greatly improves training stability and generation quality. By distilling FLM into its associated flow map, they obtain a Flow Map Language Model (FMLM) capable of few-step generation. On the LM1B and OpenWebText language datasets, FLM matches the generation quality of state-of-the-art discrete diffusion models, while FMLM outperforms all recent few-step language models — with one-step generation quality exceeding their own 8-step quality. This result fundamentally questions whether discrete state spaces are needed for text generation, opening a new direction for fast parallel text generation.

### Key Takeaways
- Flow-based continuous denoising over one-hot encodings outperforms discrete diffusion for language modeling in both quality and speed
- One-step FMLM generation exceeds 8-step quality, enabling practical single-step text generation
- Challenges the widely held assumption that discrete diffusion is necessary for modeling discrete modalities like text

---

## 7. Mobile-Agent-v3.5: Multi-platform Fundamental GUI Agents

**Authors:** Haiyang Xu, Xi Zhang, Haowei Liu, Junyang Wang, Zhaozai Zhu, Shengjie Zhou, Xuhao Hu, Feiyu Gao, Junjie Cao, Zihua Wang, Zhiyuan Chen, Jitong Liao, Qi Zheng, Jiahui Zeng, Ze Xu, Shuai Bai, Junyang Lin, Jingren Zhou, Ming Yan
**Link:** https://arxiv.org/abs/2602.16855
**Tags:** cs.AI, cs.CL

### Summary
This paper introduces GUI-Owl-1.5, a family of native GUI agent models available in instruct and thinking variants across multiple sizes (2B/4B/8B/32B/235B) that support desktop, mobile, browser, and other platforms for cloud-edge collaboration and real-time interaction. The model family achieves state-of-the-art results across 20+ GUI benchmarks among open-source models: 56.5 on OSWorld, 71.6 on AndroidWorld, 48.4 on WebArena for automation; 80.3 on ScreenSpotPro for grounding; 47.6 on OSWorld-MCP and 46.8 on MobileWorld for tool-calling; and 75.5 on GUI-Knowledge Bench for memory/knowledge.

Three key technical innovations drive these results. First, a Hybrid Data Flywheel constructs training data through a combination of simulated environments and cloud-based sandbox environments for UI understanding and trajectory generation. Second, a Unified Enhancement pipeline uses thought-synthesis to improve reasoning, with emphasis on tool/MCP use, memory, and multi-agent adaptation. Third, Multi-platform Environment RL Scaling introduces MRPO, a new environment RL algorithm addressing multi-platform conflicts and low training efficiency in long-horizon tasks. The models are fully open-sourced with an online cloud-sandbox demo, making this a practical resource for building GUI automation agents.

### Key Takeaways
- State-of-the-art open-source GUI agent across 20+ benchmarks spanning desktop, mobile, and browser platforms (56.5 OSWorld, 71.6 AndroidWorld)
- Introduces MRPO algorithm for multi-platform RL training and a hybrid data flywheel for scalable training data generation
- Open-sourced model family from 2B to 235B parameters enables cloud-edge deployment for real-world GUI automation

---

## 8. Adam Improves Muon: Adaptive Moment Estimation with Orthogonalized Momentum

**Authors:** Minxin Zhang, Yuxuan Liu, Hayden Scheaffer
**Link:** https://arxiv.org/abs/2602.17080
**Tags:** cs.LG, math.OC

### Summary
This paper bridges two of the most effective optimization approaches in deep learning: Adam's adaptive moment estimation and Muon's orthogonalized momentum. While Adam provides stability through per-parameter adaptive learning rates, Muon exploits the matrix structure of weight layers through orthogonalized momentum updates, showing superior performance in LLM pre-training. The authors propose NAMO (and its diagonal extension NAMO-D), the first principled integration of orthogonalized momentum with norm-based Adam-type noise adaptation.

NAMO scales orthogonalized momentum using a single adaptive stepsize, preserving the beneficial orthogonality properties while improving upon Muon at negligible additional cost. NAMO-D extends this by right-multiplying orthogonalized momentum with a diagonal matrix of clamped entries, enabling fine-grained per-column adaptation. Under standard assumptions, both algorithms achieve optimal convergence rates in the deterministic setting, and in the stochastic setting their convergence guarantees adapt to the noise level of stochastic gradients. Experiments on GPT-2 pre-training demonstrate improved performance over both AdamW and Muon baselines, with NAMO-D achieving further gains through a clamping hyperparameter that balances well-conditioned update directions with fine-grained noise adaptation.

### Key Takeaways
- First principled combination of Muon's orthogonalized momentum with Adam's adaptive estimation, yielding NAMO and NAMO-D optimizers
- Achieves optimal convergence rates theoretically while outperforming both AdamW and Muon on GPT-2 pre-training empirically
- NAMO-D's diagonal extension enables fine-grained noise adaptation while preserving orthogonality, at negligible computational overhead
