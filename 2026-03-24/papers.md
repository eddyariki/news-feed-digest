# Research Paper Summaries — 2026-03-24

Papers selected from today's digest for in-depth review.

---

## 1. ItinBench: Benchmarking Planning Across Multiple Cognitive Dimensions with Large Language Models

**Authors:** Tianlong Wang, Pinqiao Wang, Weili Shi, Sheng Li
**Link:** [ItinBench](https://arxiv.org/abs/2603.19515)
**Tags:** cs.AI

### Summary
ItinBench is a multi-dimensional benchmark that evaluates LLMs on complex planning tasks by combining verbal reasoning with non-verbal spatial reasoning — specifically route optimization — all framed as travel itinerary planning. The motivation is that most existing benchmarks measure cognitive dimensions in isolation, failing to capture real-world scenarios where agents must simultaneously handle diverse reasoning demands. The authors test a range of models including Llama 3.1 8B, Mistral Large, Gemini 1.5 Pro, and GPT variants. Results show that even frontier models struggle to maintain consistent performance when multiple cognitive dimensions are active at the same time. This is a notable gap given the current push toward autonomous AI agents that must plan, navigate, and reason in concert. The benchmark is positioned as a stepping stone toward more realistic evaluation frameworks. A limitation is that travel itinerary framing may not generalize to all planning domains, and the benchmark's spatial component depends on route optimization benchmarks that assume well-defined cost functions. Still, the work provides concrete evidence that single-dimension benchmark scores overestimate real-world LLM planning capability.

### Key Takeaways
- LLMs show significant performance degradation when spatial and verbal reasoning tasks are evaluated simultaneously rather than in isolation.
- Frontier models (Gemini 1.5 Pro, GPT variants) are not immune — all tested models show consistency failures across cognitive dimensions.
- Real-world evaluation frameworks must move beyond single-skill benchmarks to reflect the multi-modal demands of agentic deployment.

---

## 2. GeoChallenge: A Multi-Answer Multiple-Choice Benchmark for Geometric Reasoning with Diagrams

**Authors:** Yushun Zhang, Weiping Fu, Zesheng Yang, Bo Zhao, Lingling Zhang, Jian Zhang, Yumeng Fu, Jiaxing Huang, Jun Liu
**Link:** [GeoChallenge](https://arxiv.org/abs/2603.19252)
**Tags:** cs.CL, cs.AI

### Summary
GeoChallenge introduces a large-scale benchmark of 90,000 automatically generated geometry problems, each formatted as multi-answer multiple-choice questions requiring multi-step reasoning grounded in both textual descriptions and diagrams. The benchmark includes granular complexity assessments and formal language annotations to enable fine-grained analysis. The key evaluation finding is a substantial human-AI gap: the best-performing model achieves 75.89% exact match accuracy while humans score 94.74%. The authors identify three specific failure modes: incorrect multiple-choice handling, limited visual processing for diagram-based cues, and reasoning that continues past the necessary convergence point ("overthinking"). Automatic generation of 90K problems at varying complexity is a methodological strength that avoids the cost ceiling of expert annotation while enabling systematic difficulty control. The benchmark exposes fundamental limitations in how current LLMs integrate symbolic and visual reasoning — relevant not just for math but for any domain requiring formal diagram comprehension, such as circuit analysis or scientific figure understanding.

### Key Takeaways
- A 19-point accuracy gap between best LLM (75.89%) and humans (94.74%) persists even on auto-generated geometry problems.
- Models exhibit three identifiable failure modes: multi-choice handling errors, weak visual grounding, and over-extended reasoning chains.
- Automatic problem generation at scale enables systematic difficulty control without expert annotation costs.

---

## 3. URAG: A Benchmark for Uncertainty Quantification in Retrieval-Augmented Large Language Models

**Authors:** Vinh Nguyen, Cuong Dang, Jiahao Zhang, Hoa Tran, Minh Tran, Trinh Chau, Thai Le, Lu Cheng, Suhang Wang
**Link:** [URAG](https://arxiv.org/abs/2603.19281)
**Tags:** cs.CL, cs.AI, cs.IR

### Summary
URAG addresses a significant gap in RAG evaluation: existing benchmarks measure accuracy but not uncertainty or confidence calibration. The benchmark spans five domains — healthcare, programming, science, math, and general knowledge — and converts generation tasks into multiple-choice format to enable conformal prediction, a principled statistical method for measuring uncertainty. The key findings are nuanced and practically important: accuracy improvements from retrieval often correlate with reduced uncertainty, but this relationship breaks down under retrieval noise (e.g., when retrieved documents are irrelevant or contradictory). Simpler modular RAG approaches outperform complex reasoning pipelines on uncertainty metrics, and no single method is universally reliable across domains. The benchmark also reveals that deeper retrieval and explicit confidence signals can paradoxically amplify hallucinations in some settings. For practitioners deploying RAG in high-stakes domains like healthcare, URAG provides the first systematic evidence that reliability and accuracy can diverge, calling into question the common assumption that a more accurate RAG system is also a more trustworthy one.

### Key Takeaways
- Accuracy gains in RAG systems do not reliably predict reduced uncertainty — the relationship inverts under retrieval noise.
- Simpler modular RAG architectures outperform complex reasoning pipelines on calibration and reliability metrics.
- Deeper retrieval can amplify hallucinations in certain domains, posing risks in high-stakes applications like healthcare.

---

## 4. FDARxBench: Benchmarking Regulatory and Clinical Reasoning on FDA Generic Drug Assessment

**Authors:** Betty Xiong, Jillian Fisher, Benjamin Newman, Meng Hu, Shivangi Gupta, Yejin Choi, Lanyan Fang, Russ B. Altman
**Link:** [FDARxBench](https://arxiv.org/abs/2603.19539)
**Tags:** cs.CL, cs.AI

### Summary
FDARxBench is a real-world, expert-curated benchmark grounded in FDA generic drug label documents, developed in collaboration with regulatory assessors. It covers three distinct task types: factual question answering, multi-step regulatory reasoning, and safety refusal scenarios (where a model should decline to answer rather than hallucinate unsafe guidance). The multi-stage pipeline for generating and curating QA examples ensures quality while scaling beyond what purely manual annotation allows. Evaluation of current language models reveals three major failure modes: poor factual accuracy on drug label content, difficulty retrieving information from long documents, and inability to properly refuse unsafe requests. The safety refusal component is particularly notable — a model that confidently provides incorrect drug dosing information in a clinical context creates real patient risk. The benchmark is broader in intent than its pharmaceutical framing suggests, providing a template for regulatory-grade document comprehension tasks in any compliance-heavy domain (e.g., legal, financial).

### Key Takeaways
- Current LLMs fail on factual accuracy, long-document retrieval, and safety refusals when tested against FDA-grade regulatory text.
- The safety refusal component directly targets the risk of models providing dangerous clinical misinformation rather than declining appropriately.
- The benchmark methodology generalizes to other compliance-heavy domains beyond pharmaceuticals.

---

## 5. When Prompt Optimization Becomes Jailbreaking: Adaptive Red-Teaming of Large Language Models

**Authors:** Zafir Shamsi, Nikhil Chekuru, Zachary Guzman, Shivank Garg
**Link:** [When Prompt Optimization Becomes Jailbreaking](https://arxiv.org/abs/2603.19247)
**Tags:** cs.CL, cs.AI

### Summary
This paper investigates adaptive adversaries — attackers who iteratively refine harmful prompts using black-box optimization rather than relying on static prompt collections. The researchers repurpose existing black-box optimization techniques to systematically search for safety failures, using GPT-based danger scoring to guide the search. Experiments on HarmfulQA and JailbreakBench show dramatic vulnerability especially in smaller open-source models: Qwen 3 8B's danger score rises from a baseline of 0.09 to 0.79 after optimization. The core argument is that static red-teaming benchmarks significantly underestimate real-world risk because they sample from fixed distributions of harmful prompts rather than simulating an adversary who adapts to a specific model's defenses. This has direct implications for safety evaluation methodology: a model that passes standard jailbreak benchmarks may still be highly vulnerable to an adaptive attacker who spends even modest compute on prompt optimization. The work advocates for adaptive red-teaming as a standard component of safety evaluation pipelines.

### Key Takeaways
- Adaptive prompt optimization raises Qwen 3 8B's danger score from 0.09 to 0.79, illustrating how static benchmarks mask real vulnerability.
- Black-box optimization techniques are directly repurposable as jailbreaking tools requiring no model access beyond API calls.
- Static jailbreak benchmarks must be supplemented with adaptive red-teaming to produce meaningful safety assurance.

---

## 6. LSR: Linguistic Safety Robustness Benchmark for Low-Resource West African Languages

**Authors:** Godwin Abuh Faruna
**Link:** [LSR](https://arxiv.org/abs/2603.19273)
**Tags:** cs.CL, cs.AI

### Summary
LSR is a new benchmark that quantifies how safety alignment in LLMs degrades when harmful requests are submitted in low-resource West African languages — Yoruba, Hausa, Igbo, and Igala. The methodology uses matched English and target-language query pairs to isolate language-specific refusal rate drops, implemented using the Inspect AI evaluation framework. Results on Gemini 2.5 Flash are striking: refusal rates near 90% for English-language harmful requests drop to 35–55% for equivalent West African language requests, with Igala showing the worst degradation. This represents a systematic failure of cross-lingual safety generalization that is not random noise but a predictable, exploitable gap. The implications are significant for global AI deployment: safety evaluations conducted primarily in English or high-resource languages produce a false sense of security. As LLMs are increasingly deployed in Africa and other multilingual regions, the failure to extend alignment training to low-resource languages creates an inequitable and exploitable safety landscape.

### Key Takeaways
- Refusal rates for harmful prompts in West African languages (35–55%) are less than half those for equivalent English prompts (~90%) in Gemini 2.5 Flash.
- Safety alignment does not transfer across languages — it is largely a high-resource-language phenomenon in current models.
- The benchmark provides a replicable methodology for quantifying cross-lingual safety degradation and is publicly available.

---

## 7. The Autonomy Tax: Defense Training Breaks LLM Agents

**Authors:** Shawn Li, Yue Zhao
**Link:** [The Autonomy Tax](https://arxiv.org/abs/2603.19423)
**Tags:** cs.CR, cs.AI, cs.LG

### Summary
This paper exposes a fundamental tension in agentic AI safety: training LLM agents to resist prompt injection attacks causes collateral damage to their core functionality. The authors evaluate defended versus undefended models across 97 agent tasks and 1,000 adversarial prompts, identifying three failure patterns. First, "agent incompetence bias" — defended models refuse legitimate tasks or generate invalid actions even when no attack is present. Second, "cascade amplification bias" — initial refusals compound through retry loops, causing timeouts on 99% of tasks for defended agents versus 13% for baselines. Third, defenses frequently underperform the undefended baseline while sophisticated attacks still bypass them, creating the worst of both worlds. The root cause identified is shortcut learning: models memorize surface-level patterns associated with attack prompts rather than developing genuine semantic threat understanding. The implication is that existing defense paradigms, which optimize for refusal benchmark scores, are incompatible with multi-step agentic workflows and a new approach prioritizing semantic threat understanding while preserving tool execution capability is needed.

### Key Takeaways
- Defense-trained agents timeout on 99% of tasks versus 13% for undefended baselines — a catastrophic capability-safety tradeoff.
- Models learn surface-level refusal shortcuts rather than genuine threat semantics, making defenses fragile against novel attacks.
- Current safety training paradigms for agents must be fundamentally rethought; refusal benchmarks alone are an insufficient target.

---

## 8. A Novel Solution for Zero-Day Attack Detection in IDS Using Self-Attention and Jensen-Shannon Divergence in WGAN-GP

**Authors:** Ziyu Mu, Xiyu Shi, Safak Dogan
**Link:** [Zero-Day IDS with WGAN-GP](https://arxiv.org/abs/2603.19350)
**Tags:** cs.CR, cs.AI, cs.LG

### Summary
This paper addresses the challenge of training intrusion detection systems (IDS) against zero-day attacks — attacks with no prior examples in training data. The proposed approach generates synthetic network traffic patterns using Wasserstein GANs with gradient penalty (WGAN-GP), augmenting training datasets to include approximations of unseen attack types. Three model variants are introduced: SA-WGAN-GP (adding self-attention to capture long-range temporal dependencies in traffic), JS-WGAN-GP (incorporating Jensen-Shannon divergence for more stable and diverse generation), and SA-JS-WGAN-GP combining both. Evaluation uses the leave-one-attack-type-out protocol on the NSL-KDD dataset, simulating the zero-day scenario by excluding attack types from training. The combined SA-JS-WGAN-GP variant achieves the best detection performance. The approach is technically sound for network-based IDS, though NSL-KDD is an aging dataset and real-world generalization to modern network environments remains to be validated.

### Key Takeaways
- Combining self-attention and Jensen-Shannon divergence in WGAN-GP improves zero-day attack detection beyond baseline WGAN-GP.
- Synthetic traffic generation via GANs is a viable strategy for augmenting IDS training data for unseen attack classes.
- Evaluation on NSL-KDD limits generalizability claims; validation on modern traffic datasets would strengthen the work.

---

## 9. A Framework for Formalizing LLM Agent Security

**Authors:** Vincent Siu, Jingxuan He, Kyle Montgomery, Zhun Wang, Neil Gong, Chenguang Wang, Dawn Song
**Link:** [Formalizing LLM Agent Security](https://arxiv.org/abs/2603.19469)
**Tags:** cs.CR, cs.AI

### Summary
This paper argues that LLM agent security is fundamentally context-dependent — the same action can be legitimate or a violation depending on the instruction's origin — and proposes a formal framework to capture this. The framework defines four security properties: task alignment (the agent pursues authorized objectives), action alignment (individual actions serve those objectives), source authorization (only authenticated principals issue commands), and data isolation (privilege boundaries are respected). Existing attack categories — indirect prompt injection, direct prompt injection, jailbreak, task drift, and memory poisoning — are reinterpreted as violations of specific subsets of these properties. Defenses are reformulated as mechanisms that strengthen verification functions or perform security checks against these properties. This formalization work is important because it provides the rigorous attack and defense definitions needed to build auditable compliance frameworks for agentic AI systems, where current regulatory and security standards are still being developed. A limitation is that the framework is theoretical; empirical validation of whether it covers real-world agentic attack scenarios remains future work.

### Key Takeaways
- Security in LLM agents is inherently contextual — the same action is safe or unsafe depending on instruction origin and authorization.
- The four-property framework (task alignment, action alignment, source authorization, data isolation) provides a principled basis for compliance and audit standards.
- All major known agentic attack types can be classified as violations of one or more of these properties, unifying previously ad-hoc security definitions.

---

## 10. MAPLE: Metadata Augmented Private Language Evolution

**Authors:** Eli Chien, Yuzheng Hu, Ryan McKenna, Shanshan Wu, Zheng Xu, Peter Kairouz
**Link:** [MAPLE](https://arxiv.org/abs/2603.19258)
**Tags:** cs.CL, cs.AI, cs.CR, cs.LG

### Summary
MAPLE addresses a practical challenge in privacy-preserving AI: how to fine-tune language models on sensitive data when the model is only accessible via API (no gradient access). The approach combines differentially private tabular metadata extraction with in-context learning to improve the initialization of Private Evolution, a method for generating synthetic training data. By extracting high-level statistical metadata under differential privacy guarantees and using it to guide synthetic sample generation, MAPLE achieves better privacy-utility trade-offs, faster convergence, and reduced API call costs compared to baseline Private Evolution. The work is directly relevant to regulated industries — healthcare, finance, legal — where organizations need to adapt foundation models to sensitive domain data without exposing that data to model providers. A limitation is that the approach still depends on the quality and informativeness of metadata that can be extracted under DP constraints, which may be limited for very sensitive tabular schemas.

### Key Takeaways
- MAPLE enables privacy-preserving LLM fine-tuning via API without gradient access, relevant for regulated industries unable to share raw data.
- Differentially private metadata extraction improves synthetic data quality and reduces API costs versus unguided Private Evolution.
- The approach targets a realistic deployment scenario — API-only model access — that aligns with how most enterprises use frontier models.

---

## 11. Do Post-Training Algorithms Actually Differ? A Controlled Study Across Model Scales Uncovers Scale-Dependent Ranking Inversions

**Authors:** Xiaoyi Li
**Link:** [Post-Training Algorithm Comparison](https://arxiv.org/abs/2603.19335)
**Tags:** cs.LG, cs.AI

### Summary
This paper introduces OXRL, a unified evaluation framework for 51 post-training alignment algorithms — including DPO, SimPO, KTO, and GRPO — across model scales ranging from 0.5B to 7B parameters. The central finding is that algorithm rankings are not stable across scale: a method that leads at 1.5B parameters may be surpassed by a different method at 7B. At 1.5B, online reinforcement learning methods dominate; at 7B, the ranking shifts to a different paradigm. Loss function modifications produce negligible improvements over baseline approaches in most settings. The dominant factor in performance gains is model scale itself, followed by training paradigm (online vs. offline) and then specific algorithm choice. Performance is also highly task-dependent, with algorithmic advantages confined largely to the training distribution. For alignment practitioners at AI labs, this result is significant: choices made about which RLHF/DPO variant to use at small model scales may not transfer to production-scale models, and scale-matched evaluation is essential before committing to an alignment approach.

### Key Takeaways
- Post-training algorithm rankings invert across model scales — a method optimal at 1.5B may be suboptimal at 7B.
- Model scale is the dominant performance factor; specific loss function choice has minimal impact.
- Alignment practitioners must evaluate methods at the target deployment scale rather than extrapolating from small-model ablations.

---

## 12. Generative Active Testing: Efficient LLM Evaluation via Proxy Task Adaptation

**Authors:** Aashish Anantha Ramakrishnan, Ardavan Saeedi, Hamid Reza Hassanzadeh, Fazlolah Mohaghegh, Dongwon Lee
**Link:** [Generative Active Testing](https://arxiv.org/abs/2603.19264)
**Tags:** cs.CL, cs.AI

### Summary
Generative Active Testing (GAT) addresses the high annotation cost of building task-specific LLM evaluation benchmarks, particularly in specialized domains where expert labeling is expensive and scarce. The core method uses LLMs as surrogate models to guide sample selection — choosing which unlabeled candidates are most informative for estimating model capability — rather than sampling randomly. The key innovation is a Statement Adaptation Module that converts generative tasks into a pseudo-classification format, enabling the capture of sample-level uncertainty across unlabeled candidate pools. GAT achieves approximately 40% reduction in estimation error compared to traditional sampling methods at the same annotation budget. This is directly relevant to the benchmark construction problem: as AI is deployed in specialized verticals (legal, medical, scientific), the bottleneck is no longer generating candidate questions but selecting the most diagnostic subset for evaluation without requiring full expert annotation of all candidates.

### Key Takeaways
- GAT reduces benchmark estimation error by ~40% by actively selecting informative test samples rather than sampling uniformly.
- The Statement Adaptation Module bridges generative and classification evaluation formats, enabling uncertainty quantification without gold labels.
- Active test selection addresses the expert annotation bottleneck for specialized-domain LLM evaluation, making high-quality benchmarks more accessible.

---
