# Research Paper Summaries — 2026-04-22

Papers selected from today's digest for in-depth review.

---

## 1. COMPOSITE-STEM

**Authors:** Kyle Waters, Lucas Nuzzi, Tadhg Looram, Alessandro Tomasiello, Ariel Ghislain Kemogne Kamdoum, Bikun Li, Damien Sileo, Egor Kretov, Francesco Fournier-Facio, Georgios Soloupis, Haile Kassahun, Hew Wolff, Jiaqi Cai, Lianghui Li, Marc Roth, Mohinder Naiya, Naixu Guo, Qicheng Tang, Richard Wheeler, et al.
**Link:** [COMPOSITE-STEM](https://arxiv.org/abs/2604.09836)
**Tags:** cs.AI

### Summary
COMPOSITE-STEM addresses a critical gap in AI agent evaluation: most existing STEM benchmarks have been saturated by frontier models and only measure constrained outputs such as multiple-choice questions with closed-form answers. The benchmark introduces 70 expert-written tasks in physics, biology, chemistry, and mathematics, curated by doctoral-level researchers. Crucially, the benchmark targets "unconstrained" scientific outputs—answers that require extended derivation, multi-step reasoning, or experimental design—rather than short fill-in responses.

Evaluation is handled through a hybrid protocol combining exact-match grading with criterion-based rubrics scored by an LLM-as-a-jury ensemble, allowing for flexible yet principled assessment. The authors use an adapted multimodal Terminus-2 agent harness within the Harbor agentic evaluation framework. Across four frontier models tested, the top-performing model achieves only 21% accuracy, a stark contrast to near-perfect scores on older reasoning benchmarks, demonstrating that COMPOSITE-STEM successfully captures capabilities at the current frontier.

A key implication is methodological: the field has relied on benchmarks that no longer differentiate between models, inflating perceived progress. COMPOSITE-STEM is fully open-sourced with contributor permissions, enabling community expansion. The primary limitation is the small task count (70 tasks), which may introduce variance in aggregate scores, and the reliance on LLM juries introduces calibration uncertainty in rubric scoring.

### Key Takeaways
- Existing STEM benchmarks are saturated; top models score near 21% on COMPOSITE-STEM, confirming a meaningful challenge ceiling.
- Expert-curated, open-ended tasks are necessary to capture whether agents can do real scientific work, not just pattern-match.
- LLM-as-a-jury grading is central to evaluating unconstrained scientific output at scale.

---

## 2. The Amazing Agent Race: Strong Tool Users, Weak Navigators

**Authors:** Zae Myung Kim, Dongseok Lee, Jaehyung Kim, Vipul Raheja, Dongyeop Kang
**Link:** [The Amazing Agent Race (AAR)](https://arxiv.org/abs/2604.10261)
**Tags:** cs.AI

### Summary
AAR exposes a structural flaw in how current tool-use benchmarks are constructed: 55–100% of tasks across six popular benchmarks consist of simple linear chains of 2–5 steps. This means agents can succeed through shallow sequential execution without demonstrating any capacity for planning, branching, or multi-source aggregation. To fill this gap, the authors introduce 1,400 benchmark instances organized as directed acyclic graph (DAG) "leg" puzzles—some sequential (800), others compositional with fork-merge structures (600).

Tasks involve navigating Wikipedia, executing multi-step tool chains, and aggregating results into verifiable answers. Legs are procedurally generated from Wikipedia seeds across four difficulty levels with live-API validation. Three metrics separately diagnose navigation failures, tool-use errors, and arithmetic mistakes. Across three agent frameworks, the best achieves only 37.2% accuracy, with navigation errors accounting for 27–52% of failures—while tool-use errors remain below 17%. A surprising finding is that agent architecture matters as much as model scale: Claude Code matches Codex CLI at 37% accuracy while using 6× fewer tokens.

The results make clear that current agents are reliable tool executors but poor planners on fork-merge workflows—a capability gap with direct implications for any multi-step agentic deployment. A limitation is that tasks are Wikipedia-based, which may not capture domain-specific planning failures in enterprise settings.

### Key Takeaways
- Current agents fail primarily at navigation and planning (27–52% of failures), not at tool invocation.
- DAG-structured benchmarks expose planning capability gaps invisible in linear-chain evaluations.
- Architecture choices have as large an effect on performance as model scale.

---

## 3. Evaluating Multimodal LLMs for Inpatient Diagnosis (VALID)

**Authors:** Bruce A. Bassett, Amy Rouillard, Sitwala Mundia, Michael Cameron Gramanie, Linda Camara, Ziyaad Dangor, Shabir A. Madhi, Kajal Morar, Marlvin T. Ncube, Ismail Kalla, Haroon Saloojee
**Link:** [VALID](https://arxiv.org/abs/2604.16980)
**Tags:** cs.LG

### Summary
VALID is a retrospective evaluation of ten frontier multimodal LLMs on 539 real-world inpatient cases from a tertiary public hospital in South Africa—one of the first clinical LLM benchmarks situated in a low- and middle-income country (LMIC) context. Inputs are genuinely multimodal: CT, MRI, and chest X-ray imaging plus radiology reports, laboratory results, clinical notes, and vital signs. Expert panels adjudicated 300 cases to establish ground truth diagnoses, differentials, and clinical reasoning. All LLMs generated zero-shot outputs, which a calibrated three-model LLM jury scored across diagnostic accuracy, differential quality, reasoning, and patient safety—over 10,000 evaluations in total.

Key findings challenge common assumptions. First, LLM performance was tightly clustered—less than 15% variation—despite large cost differences between models, meaning low-cost models performed comparably to expensive flagship ones. Second, all LLMs significantly outperformed routine ward diagnoses on average diagnostic and safety scores. Third, discordant cases (where imaging and clinical data conflict) remained the hardest subset for all models. The study's LMIC setting is both its strength and a limitation: it fills an important gap in geographic diversity, but results may not generalize to high-resource hospital systems with richer structured data.

### Key Takeaways
- Frontier LLMs significantly outperform routine ward diagnoses on diagnostic accuracy and patient safety scores in a real South African hospital setting.
- Cost is not a reliable proxy for capability; low-cost models matched top-tier performance.
- Discordant cases—where imaging and clinical data conflict—remain a universal blind spot across all models.

---

## 4. ReXSonoVQA: A Video QA Benchmark for Procedure-Centric Ultrasound Understanding

**Authors:** Xucheng Wang, Xiaoman Zhang, Sung Eun Kim, Ankit Pal, Pranav Rajpurkar
**Link:** [ReXSonoVQA](https://arxiv.org/abs/2604.10916)
**Tags:** cs.CV

### Summary
ReXSonoVQA addresses a gap in medical AI evaluation: existing ultrasound benchmarks test models on static images, missing the fundamentally dynamic, procedural nature of ultrasound—which requires skilled real-time probe manipulation and contextual adjustment. The benchmark introduces 514 video clips with 514 questions spanning multiple-choice (249) and free-response (265) formats, targeting three competencies: Action-Goal Reasoning (what the sonographer is trying to achieve), Artifact Resolution & Optimization (diagnosing image degradation and corrections), and Procedure Context & Planning (understanding where in a procedure a clip sits).

Zero-shot evaluation of four frontier VLMs—Gemini 3 Pro, Qwen3.5-397B, LLaVA-Video-72B, and Seed 2.0 Pro—shows models can extract some procedural information but fail significantly on troubleshooting questions, with minimal gains over text-only baselines. This exposes a specific weakness in causal reasoning about imaging artifacts rather than general ultrasound recognition. The benchmark is designed to enable development of perception systems for ultrasound training, guidance, and robotic automation. A key limitation is the dataset size (514 clips), which may be insufficient for fine-grained capability profiling across all three competencies.

### Key Takeaways
- Current frontier VLMs struggle with procedural ultrasound reasoning, especially artifact troubleshooting, where they barely exceed text-only baselines.
- Static image benchmarks systematically overestimate model readiness for real-time clinical ultrasound assistance.
- The three-competency structure (action-goal, artifact resolution, procedure context) provides a reusable framework for procedural medical AI evaluation.

---

## 5. The Blind Spot of Agent Safety: How Benign User Instructions Expose Critical Vulnerabilities in Computer-Use Agents

**Authors:** Xuwei Ding, Skylar Zhai, Linxin Song, Jiate Li, Taiwei Shi, Nicholas Meade, Siva Reddy, Jian Kang, Jieyu Zhao
**Link:** [The Blind Spot of Agent Safety](https://arxiv.org/abs/2604.10577)
**Tags:** cs.CR

### Summary
This paper identifies a critical blind spot in computer-use agent (CUA) safety evaluations: nearly all existing benchmarks focus on explicit misuse scenarios or prompt injection attacks, while ignoring cases where the user's instructions are entirely benign but the execution environment or outcome is harmful. To study this, the authors introduce OS-BLIND, a benchmark of 300 human-crafted tasks across 12 categories, 8 applications, and 2 threat clusters—"environment-embedded threats" (malicious content placed in the agent's operating environment) and "agent-initiated harms" (harmful side-effects generated by the agent's own actions).

Results are alarming: most frontier CUAs exceed 90% attack success rate (ASR) on OS-BLIND. Even safety-aligned Claude 4.5 Sonnet reaches 73.0% ASR under single-agent deployment—and that rises to 92.7% when the same model is deployed in a multi-agent system. The analysis shows that safety alignment primarily activates within the first few turns; after that, mid-task context causes guards to weaken. Existing defenses provide minimal protection when user instructions appear benign. The implication is that current safety paradigms must expand beyond refusal training and injection detection to account for contextual and emergent harms.

### Key Takeaways
- Even fully benign user instructions can lead to harmful execution outcomes—a class of risk that current safety evaluations completely miss.
- Multi-agent deployment amplifies CUA attack success rates (73% → 93% for Claude 4.5 Sonnet).
- Safety alignment decays mid-task; defenses that only check the first few turns are insufficient for long agentic sessions.

---

## 6. Evaluating Temporal and Structural Anomaly Detection Paradigms for DDoS Traffic

**Authors:** Yasmin Souza Lima, Rodrigo Moreira, Larissa F. Rodrigues Moreira, Tereza Cristina M. de B. Carvalho, Flávio de Oliveira Silva
**Link:** [Evaluating Temporal and Structural Anomaly Detection for DDoS Traffic](https://arxiv.org/abs/2604.16575)
**Tags:** cs.LG

### Summary
DDoS detection in cloud-native 5G networks typically applies either temporal (time-series-based) or structural (graph-based) anomaly detection—but most prior work picks one representation without empirically validating which better fits the underlying traffic data. This paper proposes a lightweight diagnostic decision framework that, before model training, selects the appropriate feature space using two simple probes: lag-1 autocorrelation of an aggregated flow signal (to assess temporal dependence) and PCA cumulative explained variance (to assess structural separability). When probes are inconclusive, the framework flags a hybrid option as a future fallback rather than committing to an empirically unsupported branch.

Experiments on two statistically distinct datasets with three unsupervised algorithms (Isolation Forest, One-Class SVM, and KMeans) consistently show that structural features match or outperform temporal ones, with the performance gap widening as temporal dependence weakens. The lightweight pre-selection step has practical value: it avoids expensive training runs on the wrong representation and improves detection accuracy without increasing model complexity. Key limitations include the restriction to unsupervised methods and the lack of evaluation on adversarially crafted DDoS traffic that might exploit the selection logic.

### Key Takeaways
- Structural (graph-based) features consistently match or outperform temporal features for unsupervised DDoS anomaly detection in 5G environments.
- A two-probe diagnostic framework (autocorrelation + PCA) can guide representation selection before training at minimal cost.
- Choosing the wrong feature representation is a significant source of detection degradation—a problem the community has largely overlooked.

---

## 7. Towards Reliable Testing of Machine Unlearning

**Authors:** Anna Mazhar, Sainyam Galhotra
**Link:** [Towards Reliable Testing of Machine Unlearning](https://arxiv.org/abs/2604.16536)
**Tags:** cs.LG

### Summary
As GDPR and AI governance frameworks increasingly require verifiable deletion of personal data from deployed models, machine unlearning has emerged as a practical alternative to full retraining. But unlearning introduces a software quality-assurance problem that has received little systematic attention: under realistic deployment constraints and imperfect oracles, how can we actually test that a model no longer relies on targeted information? This paper frames unlearning verification as a first-class software engineering challenge and argues that practical tests must satisfy four properties: thorough coverage over proxy and mediated influence pathways, debuggable diagnostics that localize where leakage persists, cost-effective execution under query budgets, and black-box applicability for API-deployed models.

The authors propose "causal fuzzing"—a causal, pathway-centric approach that generates budgeted interventions to estimate residual direct and indirect effects, producing actionable "leakage reports." Proof-of-concept results show that standard attribution methods miss residual influence that causal fuzzing detects. This reframing is significant for compliance: regulators demanding data deletion cannot currently verify satisfaction of deletion requests, and this work provides the conceptual scaffolding for auditable unlearning tests. A current limitation is that the causal fuzzing framework is presented as a proof-of-concept without large-scale empirical benchmarking across diverse unlearning algorithms.

### Key Takeaways
- Machine unlearning verification should be treated as a software QA problem with coverage, debuggability, and budget constraints—not just a model metric.
- Standard attribution methods miss residual influence pathways that causal fuzzing can detect.
- GDPR and AI governance compliance requires auditable, black-box-compatible unlearning tests that do not currently exist at production scale.

---

## 8. SaFeR-Steer: Evolving Multi-Turn MLLMs via Synthetic Bootstrapping and Feedback Dynamics

**Authors:** Haolong Hu, Hanyu Li, Tiancheng He, Huahui Yi, An Zhang, Qiankun Li, Kun Wang, Yang Liu, Zhigang Zeng
**Link:** [SaFeR-Steer](https://arxiv.org/abs/2604.16358)
**Tags:** cs.LG

### Summary
Multimodal LLMs (MLLMs) are increasingly deployed in multi-turn interactions, but safety alignment is almost entirely trained on single-turn data and fixed-template dialogues. Attackers can exploit this by gradually escalating harmful intent across turns, leveraging "long-context safety decay"—a phenomenon where safety guards weaken as conversation history grows. SaFeR-Steer addresses this mismatch through a progressive multi-turn alignment framework combining staged synthetic bootstrapping with a tutor-in-the-loop GRPO (Group Relative Policy Optimization) training procedure that exposes a student model to adaptive, on-policy attacks.

The authors also introduce TCSR (Trajectory Cumulative Safety Reward), which propagates late-turn safety failures back to earlier turns in the trajectory, enabling the model to learn to maintain safety through full conversation arcs rather than just at the point of explicit violation. The released STEER dataset contains over 18,000 multi-turn multimodal dialogues for SFT, RL, and benchmarking. Starting from Qwen2.5-VL-3B/7B base models, SaFeR-Steer substantially improves both safety and helpfulness on single-turn and multi-turn benchmarks—e.g., safety/helpfulness goes from 56.2/60.3 to 87.9/77.4 for the 7B model. The primary limitation is the reliance on synthetic adversarial scenarios, which may not fully cover the diversity of real-world escalation strategies.

### Key Takeaways
- Long-context safety decay is a real and exploitable vulnerability; single-turn alignment training leaves a systematic gap in multi-turn deployments.
- TCSR propagates late-turn failures to earlier turns, enabling trajectory-level safety optimization rather than per-turn grading.
- SaFeR-Steer improves both safety and helpfulness—evidence that safety and utility need not trade off when training data quality is high.

---

## 9. Shifting the Gradient: Understanding How Defensive Training Methods Protect Language Model Integrity

**Authors:** Satchel Grant, Victor Gillioz, Jake Ward, Thomas McGrath
**Link:** [Shifting the Gradient](https://arxiv.org/abs/2604.16423)
**Tags:** cs.LG

### Summary
Positive preventative steering (PPS) and inoculation prompting (IP) are two defensive training techniques that both work by adding trait-inducing objects to LLMs during training to protect against acquiring harmful traits. Because their surface-level mechanisms appear similar, it has been unclear whether they operate through the same underlying process—a distinction that matters for understanding when each is appropriate and how they might fail. This paper provides the first behavioral and mechanistic comparison of the two methods, using "evilness" as a case-study trait.

The central finding is that PPS and IP achieve their defensive benefits through distinct gradient-level mechanisms. Behaviorally, neither operates through a purely associative (Pavlovian) mechanism. PPS can both prevent trait acquisition and actively reduce pre-existing expression of the trait in models already fine-tuned to express it; IP fails in such cases. Mechanistically, PPS shifts the activation gradient toward an attenuating direction along the PPS vector axis—when this vector aligns with a trait-expressing axis, PPS reverses gradient pressure and actively suppresses the trait. This mechanistic insight has practical implications: it explains why PPS is more versatile but also why misaligned PPS vectors could inadvertently reinforce the very behavior they target. The case-study limitation (using "evilness" as a proxy trait) means broader generalization across safety-relevant traits requires further validation.

### Key Takeaways
- PPS and IP are mechanistically distinct despite surface similarity—PPS operates by redirecting activation gradients, IP does not.
- PPS can reduce pre-existing harmful trait expression; IP cannot, making them non-interchangeable for remediation scenarios.
- Understanding gradient-level mechanisms is essential for predicting when defensive training will generalize versus fail.

---

## 10. A Discordance-Aware Multimodal Framework with Multi-Agent Clinical Reasoning

**Authors:** Pegah Ahadian, Mingrui Yang, Sixu Chen, Xiaojuan Li, Qiang Guan
**Link:** [A Discordance-Aware Multimodal Framework](https://arxiv.org/abs/2604.16333)
**Tags:** cs.LG

### Summary
Knee osteoarthritis (KOA) presents a clinical challenge that exposes a fundamental limitation of unimodal AI systems: structural damage visible in imaging frequently does not correlate with patient-reported pain, a discordance that complicates both diagnosis and patient stratification. Existing clinical decision support systems model these pathways independently or ignore the mismatch entirely. This paper proposes a discordance-aware multimodal framework that integrates ML prediction with a tool-grounded multi-agent reasoning system to explicitly surface and reason about this imaging-symptom gap.

The predictive system combines three modality-specific expert models—a CatBoost tabular model for demographic, radiographic, MRI-derived scalar, and biomarker features; MRI image embeddings via ResNet18; and X-ray embeddings from the same architecture—fused through a stacking ensemble. A residual-based model estimates expected pain from structural features, enabling computation of a "pain-structure discordance score" between observed and predicted symptom levels. This score feeds a multi-agent reasoning layer to flag high-discordance cases for elevated clinical attention. The framework is trained and evaluated on the FNIH Osteoarthritis Biomarkers Consortium dataset. A limitation is that the multi-agent reasoning layer's behavior is evaluated qualitatively rather than through rigorous clinical outcome metrics.

### Key Takeaways
- Imaging-symptom discordance in osteoarthritis is a systematically under-modeled clinical problem that unimodal AI cannot address.
- A pain-structure discordance score computed from residual prediction errors provides an interpretable signal for flagging ambiguous cases.
- Multi-agent clinical reasoning systems can operationalize multimodal discordance detection in a way that guides, rather than replaces, clinician judgment.

---

## 11. LLM-Extracted Covariates for Clinical Causal Inference: Rethinking Integration Strategies

**Authors:** Lei Liu, Jialin Chen, Kathy Macropol
**Link:** [LLM-Extracted Covariates for Clinical Causal Inference](https://arxiv.org/abs/2604.16763)
**Tags:** cs.LG

### Summary
Causal inference from electronic health records (EHR) is undermined by unmeasured confounding: critical clinical states like frailty, goals of care, and mental status appear in clinical notes but are absent from structured data. LLMs can extract these latent confounders as structured covariates, but the question of how to integrate them into causal estimation pipelines has not been systematically studied. This paper fills that gap using MIMIC-IV data from 21,859 sepsis patients to compare seven covariate-integration strategies for estimating the effect of early vasopressor initiation on 28-day mortality.

The strategies range from tabular-only baselines and traditional NLP representations to three LLM-augmented approaches. The central finding is that integration strategy matters enormously: directly augmenting the propensity score model with LLM covariates achieves the best performance, while dual-caliper matching on text-derived categorical distances restricts the donor pool and degrades estimation. In semi-synthetic experiments with known ground-truth effects, LLM-augmented propensity scores reduce estimation bias from 0.0143 to 0.0003 relative to tabular baselines—a 50× reduction. The work has direct implications for AI-assisted observational studies and pharmacovigilance. A limitation is the single-disease focus (sepsis) and the need for domain expert validation of LLM extraction quality, which the paper treats as assumed rather than empirically verified.

### Key Takeaways
- Not all LLM integration strategies for causal inference are equal: direct propensity score augmentation outperforms embedding-based matching approaches.
- LLM-extracted confounders reduce estimation bias 50× in semi-synthetic experiments, a compelling case for LLM-augmented causal pipelines in clinical research.
- Text-derived categorical distance matching degrades causal estimates by restricting the donor pool—a counterintuitive failure mode worth avoiding.

---

## 12. The Illusion of Certainty: Decoupling Capability and Calibration in On-Policy Distillation

**Authors:** Jiaxin Zhang, Xiangyu Peng, Qinglin Chen, Qinyuan Ye, Caiming Xiong, Chien-Sheng Wu
**Link:** [The Illusion of Certainty](https://arxiv.org/abs/2604.16830)
**Tags:** cs.LG

### Summary
On-policy distillation (OPD) is a widely used post-training paradigm in which a student model learns from a teacher's outputs on the student's own generated data. This paper identifies a pervasive and previously unnamed failure mode: a "Scaling Law of Miscalibration" where OPD systematically improves task accuracy while simultaneously inducing severe overconfidence. The root cause is an information mismatch—teacher supervision is formed under privileged context available only at training time, but the deployed model must report confidence using only inference-time information. As training progresses, models learn to mimic the teacher's high-confidence signals without having access to the conditions that justified them, leading to entropy collapse and a systematic optimism bias.

The authors formalize this theoretically and propose CaOPD (Calibration-aware On-Policy Distillation), which estimates empirical confidence from model rollouts, replaces self-reported confidence with this student-grounded target, and distills the revised response through the same self-distillation pipeline. Experiments across multiple models and domains show CaOPD achieves Pareto-optimal calibration-accuracy tradeoffs and generalizes robustly under out-of-distribution conditions. The safety implication is significant: overconfident models in deployed settings can mislead users and downstream systems into misplaced trust—a failure mode distinct from, and potentially more insidious than, simple inaccuracy.

### Key Takeaways
- On-policy distillation reliably improves task accuracy but induces severe overconfidence—a "Scaling Law of Miscalibration" that compounds with training scale.
- The cause is an information mismatch between privileged teacher context and deployment-time model context, leading to entropy collapse.
- CaOPD achieves Pareto-optimal calibration without sacrificing capability, directly addressing a safety-critical failure mode in deployed distilled models.

---
