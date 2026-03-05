# Research Paper Summaries — 2026-03-05

Papers selected from today's digest for in-depth review.

---

## 1. Annotation-Efficient Universal Honesty Alignment

**Authors:** Shiyu Ni, Keping Bi, Jiafeng Guo, Minghao Tang, Jingtong Wu, Zengxin Han, Xueqi Cheng
**Link:** [Annotation-Efficient Universal Honesty Alignment](https://arxiv.org/abs/2510.17509)
**Tags:** cs.CL

### Summary
LLMs often fail to recognize the limits of their own knowledge — expressing false confidence on questions they cannot reliably answer. Existing approaches to this "honesty alignment" problem either avoid training altogether (using token probabilities or self-consistency as proxies) or require large amounts of costly correctness annotations. This paper introduces **EliCal** (Elicitation-Then-Calibration), a two-stage training framework that bridges these extremes. In the first stage, the model is trained with inexpensive self-consistency supervision to elicit its internal confidence. In the second stage, a small set of correctness annotations is used to calibrate that elicited confidence, anchoring it to ground truth. To support evaluation at scale, the authors also release **HonestyBench**, a benchmark spanning ten free-form QA datasets with 560k training and 70k evaluation instances labeled with both correctness and self-consistency signals. Experiments show that EliCal reaches near-optimal honesty alignment using just 1,000 correctness annotations — only 0.18% of full supervision — and generalizes better to unseen MMLU tasks than calibration-only baselines. The result is a scalable path toward LLMs that know what they don't know, without requiring prohibitively expensive annotation pipelines.

### Key Takeaways
- Two-stage EliCal framework achieves near-optimal honesty calibration with only 1k correctness labels (0.18% of full supervision)
- Self-consistency signals serve as an inexpensive proxy for the first stage, dramatically reducing labeling burden
- HonestyBench provides a large-scale public resource for studying and benchmarking LLM calibration

---

## 2. Secure Semantic Communications via AI Defenses: Fundamentals, Solutions, and Future Directions

**Authors:** Lan Zhang, Chengsi Liang, Zeming Zhuang, Yao Sun, Fang Fang, Xiaoyong Yuan, Dusit Niyato
**Link:** [Secure Semantic Communications via AI Defenses: Fundamentals, Solutions, and Future Directions](https://arxiv.org/abs/2602.22134)
**Tags:** cs.CR, eess.SY

### Summary
Semantic communication (SemCom) systems shift the goal of wireless transmission from reproducing raw symbols to conveying task-relevant meaning using AI-native encoders and decoders. While this enables dramatic efficiency gains, it opens a new class of security vulnerabilities that conventional cryptographic protections cannot address. This survey provides a defense-centered taxonomy of threats specific to SemCom architectures: adversarial perturbations to learned semantic encoders, corruption of shared semantic priors through poisoned training data, channel-realizable attacks that exploit the wireless medium to manipulate inference, and adversarial propagation through distributed multi-agent semantic inference. For each threat class, the authors catalog AI-based defense strategies and map them to where semantic integrity can fail despite correct symbol delivery. The survey also examines practical operating tradeoffs between semantic fidelity, robustness, latency, and energy efficiency, and identifies open problems in cross-layer composition and certification. This work is notable for providing a unified system-level view of a problem that has historically been treated in scattered, per-attack literature, and for framing the challenge in terms of deployment-time certification rather than just model-level robustness.

### Key Takeaways
- SemCom introduces four distinct attack surfaces — model-level, channel-realizable, knowledge-based, and networked inference — that bypass conventional cryptographic defenses
- Defense strategies must be mapped to where in the semantic pipeline integrity can fail, not just to attack types
- Deployment-time certification and cross-layer composition remain open problems for next-generation intelligent networks

---

## 3. FlowCorrect: Efficient Interactive Correction of Generative Flow Policies for Robotic Manipulation

**Authors:** Edgar Welte, Yitian Shi, Rosa Wolf, Maximillian Gilles, Rania Rayyes
**Link:** [FlowCorrect: Efficient Interactive Correction of Generative Flow Policies for Robotic Manipulation](https://arxiv.org/abs/2602.22056)
**Tags:** cs.RO, cs.LG

### Summary
Generative manipulation policies based on flow matching are powerful but brittle: when deployment conditions shift even slightly from training, they can fail catastrophically despite coming very close to succeeding. FlowCorrect addresses this by treating near-miss failures not as retraining signals but as correction opportunities. The system is modular — it sits on top of any flow-matching policy without modifying the backbone — and uses a lightweight VR interface through which a human operator provides brief, sparse, relative pose nudges during execution. These corrections locally adapt the policy for the failed case while preserving learned behavior on previously solved scenarios. Evaluated on a real robot across four tabletop tasks (pick-and-place, pouring, cup uprighting, and insertion), FlowCorrect achieves an 80% success rate on previously failing cases with a minimal correction budget. A key design principle is that the corrections are relative rather than absolute, making them easier for operators to provide and more invariant to workspace variation. The approach is particularly relevant for deployment scenarios where retraining is expensive or impractical.

### Key Takeaways
- Achieves 80% recovery on near-miss failures using sparse human corrections, with no backbone retraining
- Modular design is policy-agnostic and can wrap any flow-matching manipulation policy
- Relative pose corrections via a VR interface are lightweight to provide and generalizable across workspaces

---

## 4. Momentum Memory for Knowledge Distillation in Computational Pathology

**Authors:** Yongxin Guo, Hao Lu, Onur C. Koyun, Zhengjie Zhu, Muhammet Fatih Demir, Metin Nafi Gurcan
**Link:** [Momentum Memory for Knowledge Distillation in Computational Pathology](https://arxiv.org/abs/2602.21395)
**Tags:** cs.CV

### Summary
Integrating genomic data with histopathology images is a promising direction for cancer diagnosis, but paired histology-genomics datasets are scarce and expensive to collect. Knowledge distillation (KD) offers a way to bake genomic supervision into a histology-only model at training time, enabling accurate inference from slide images alone. However, existing KD methods rely on batch-local alignment — comparing genomic and histological features only within each mini-batch — which limits the diversity of comparisons and leads to unstable training. This paper proposes **MoMKD** (Momentum Memory Knowledge Distillation), which maintains a momentum-updated memory bank that accumulates cross-modal feature representations across batches, substantially enlarging the effective supervisory context. The method also decouples the gradient updates for the genomics and histology branches during training, preventing the stronger genomic signal from dominating histology feature learning and eliminating modality-gap artifacts at inference time. Experiments on TCGA-BRCA for HER2, PR, and ODX classification tasks, as well as an independent in-house dataset, show consistent outperformance of both standard MIL baselines and state-of-the-art multimodal KD methods, with strong generalization to out-of-distribution data.

### Key Takeaways
- Momentum memory bank expands cross-modal supervisory context beyond batch boundaries, stabilizing distillation training
- Gradient decoupling between genomics and histology branches prevents modality dominance and inference-time gap
- Demonstrates strong generalization on both TCGA-BRCA benchmarks and an independent clinical dataset

---

## 5. Automatic Map Density Selection for Locally-Performant Visual Place Recognition

**Authors:** Somayeh Hussaini, Tobias Fischer, Michael Milford
**Link:** [Automatic Map Density Selection for Locally-Performant Visual Place Recognition](https://arxiv.org/abs/2602.21473)
**Tags:** cs.CV

### Summary
Visual place recognition (VPR) systems must operate reliably across all parts of a deployment environment, yet most existing research optimizes for global average performance metrics. In practice, a robot or autonomous vehicle that consistently fails in specific local areas — even if its global recall is high — is not deployable. This paper addresses the under-studied problem of reference map density selection: how densely should a mapping traverse be sampled to guarantee that local performance requirements are met? The authors introduce a dynamic mapping approach driven by two user-specified requirements: a target Local Recall@1 and a Recall Achievement Rate (RAR) — the fraction of the environment that must meet or exceed that recall threshold. The system learns to predict the required density from match patterns observed across multiple reference traverses at varying densities, then selects the appropriate operating point automatically. Experiments on the Nordland and Oxford RobotCar benchmarks across multiple VPR methods show consistent satisfaction of the specified local recall level while avoiding unnecessary over-densification. An important finding is that conventional global Recall@1 is a poor predictor of RAR, motivating the shift toward locally-specified performance contracts.

### Key Takeaways
- Introduces RAR (Recall Achievement Rate) as a more operationally meaningful metric than global Recall@1 for VPR deployment
- Automated density selection satisfies user-specified local performance contracts without manual tuning
- Global recall metrics are poor proxies for local reliability, which has implications for how VPR benchmarks are designed

---

## 6. Meenz bleibt Meenz, but Large Language Models Do Not Speak Its Dialect

**Authors:** Minh Duc Bui, Manuel Mager, Peter Herbert Kann, Katharina von der Wense
**Link:** [Meenz bleibt Meenz, but Large Language Models Do Not Speak Its Dialect](https://arxiv.org/abs/2602.16852)
**Tags:** cs.CL

### Summary
Meenzerisch is the traditional dialect of Mainz, Germany — best known as the language of the Mainz carnival — and like many regional German dialects, it is endangered. This paper presents the first NLP research explicitly targeting Meenzerisch, introducing a digital dictionary of 2,351 dialect words paired with Standard German definitions derived from a 1966 print resource. The authors use this dataset to probe state-of-the-art LLMs on two tasks: generating Standard German definitions for dialect words, and generating Meenzerisch words from their definitions. Results are sobering: the best model achieves only 6.27% accuracy on definition generation and 1.51% on word generation. Few-shot prompting and rule extraction improve results, but accuracy remains below 10% across all conditions. The work highlights a fundamental gap: current LLMs, despite their multilingual and multi-dialect pre-training, effectively cannot engage with low-resource endangered dialects. Beyond the linguistic interest in Meenzerisch specifically, the paper serves as a call to action for the broader NLP community to prioritize dialect preservation research and data collection for languages without digital resources.

### Key Takeaways
- State-of-the-art LLMs effectively cannot model Meenzerisch: best accuracy is 6.27% on definitions, 1.51% on word generation
- Few-shot learning and explicit rule extraction improve results but do not close the gap, indicating data scarcity is the core bottleneck
- Introduces a reusable NLP-ready dataset for Meenzerisch and argues for increased research focus on endangered dialects

---
