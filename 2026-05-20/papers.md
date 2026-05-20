# Research Paper Summaries — 2026-05-20

Papers selected from today's digest for in-depth review.

---

## 1. MLReplicate: Benchmarking Autonomous Research Systems for Machine Learning Reproducibility

**Authors:** Sasi Kiran Gaddipati, Diyana Muhammed, Farhana Keya, Gollam Rabby, Sören Auer
**Link:** [MLReplicate: Benchmarking Autonomous Research Systems for Machine Learning Reproducibility](https://arxiv.org/abs/2605.16616)
**Tags:** cs.LG

### Summary
Autonomous "AI scientist" systems that produce complete ML manuscripts have proliferated faster than the tools to evaluate them. MLReplicate addresses this by turning ICML 2025 outstanding papers into standardized input specifications and asking six leading autonomous research systems — AI Scientist-V1/V2, Agent Laboratory, CycleResearcher, AI Researcher, and Tiny Scientist — to reproduce them, generating 45 manuscripts (3 failed). Each output is reviewed twice: by an automated conference-style review pipeline and by structured expert humans, while compute cost, runtime, and human intervention are tracked. Automated reviewers accepted 10 of 37 valid submissions, but human reviewers flagged methodological flaws, hallucinated results, and reproducibility failures across all six systems — and 59% of automated-accepted reviews contained fabricated or unsupported claims, indicating the LLM reviewers themselves are unreliable. Strikingly, compute does not predict quality: the cheapest system outperformed the most resource-intensive one in human evaluation despite a 38× difference in input tokens, suggesting workflow design matters more than scale. The benchmark exposes a wide gap between current autonomous research agents and actual scientific rigor, and is positioned as an extensible framework for tracking progress toward trustworthy AI-driven science. Limitations include the relatively small set of seed papers (drawn from a single venue/year) and reliance on a single human-evaluation protocol, but the dual-protocol design and the LLM-reviewer fabrication finding are likely to influence how the community reports agent-science capability claims.

### Key Takeaways
- Automated LLM reviewers are dangerously lenient: 59% of their accepts contained fabricated or unsupported claims, undermining "AI scientist" self-evaluation.
- Compute spend does not predict autonomous-research output quality; workflow design dominates token budget by a wide margin.
- Even the best autonomous research systems still fail at reproducing real ICML papers when judged by human experts, setting a sober baseline for agent-driven science.

---

## 2. CHI-Bench: Can AI Agents Automate End-to-End, Long-Horizon, Policy-Rich Healthcare Workflows?

**Authors:** Haolin Chen, Deon Metelski, Leon Qi, Tao Xia, Joonyul Lee, Steve Brown, Kevin Riley, Frank Wang, T. Y. Alvin Liu, Hank Capps MD, Zeyu Tang, Xiangchen Song, Lingjing Kong, Fan Feng, Tianyi Zeng, Zhiwei Liu, Zixian Ma, Hang Jiang, Fangli Geng, Yuan Yuan, Chenyu You, Qingsong Wen, Hua Wei, Yanjie Fu, Yue Zhao, Carl Yang, Biwei Huang, Kun Zhang, Caiming Xiong, Sanmi Koyejo, Eric P. Xing, Philip S. Yu, Weiran Yao
**Link:** [CHI-Bench: Can AI Agents Automate End-to-End, Long-Horizon, Policy-Rich Healthcare Workflows?](https://arxiv.org/abs/2605.16679)
**Tags:** cs.CL, cs.AI

### Summary
CHI-Bench (χ-Bench) targets a gap most agent benchmarks miss: realistic enterprise workflows that combine policy density (decisions grounded in large libraries of medical, insurance, and operational rules), multi-role composition (one task requires the agent to act across several handoff roles), and multilateral interaction (intermediate steps are multi-turn dialogs like peer-to-peer review or patient outreach). It covers three long-horizon healthcare domains — provider prior authorization, payer utilization management, and care management — and embeds each task in a high-fidelity simulator of 20 healthcare apps exposed through 87 MCP tools, with a 1,290+ document managed-care operations handbook serving as the agent's policy skill. Across 30 harness/model configurations, the strongest agent resolved only 28% of tasks, no agent cleared 20% on a strict pass^3 reliability metric, and stacking all tasks in a single session dropped performance to 3.8% — evidence that today's agents collapse under realistic multi-task workloads. The authors argue these gaps will likely generalize to other policy-dense, role-composed, irreversible enterprise domains. Implications are significant for AI deployment in regulated industries: vendor demos that show single-task success rates can be off by an order of magnitude versus real workflow reliability, and existing agents still need substantial advances in long-horizon state tracking and policy retrieval before they can autonomously run end-to-end healthcare operations.

### Key Takeaways
- Even the best agent harness resolves only 28% of realistic healthcare workflow tasks; pass^3 reliability stays under 20% across all configurations.
- Bundling tasks into a single session crashes performance to 3.8%, exposing severe long-horizon and cross-task degradation.
- Realistic policy density (1,290+ doc skill, 87 MCP tools) is a far harder agent stress test than single-shot tool-use benchmarks.

---

## 3. Validate Your Authority: Benchmarking LLMs on Multi-Label Precedent Treatment Classification

**Authors:** M. Mikail Demir, M. Abdullah Canbaz
**Link:** [Validate Your Authority: Benchmarking LLMs on Multi-Label Precedent Treatment Classification](https://arxiv.org/abs/2605.17691)
**Tags:** cs.CL, cs.AI

### Summary
Classifying how a legal precedent has been treated in subsequent cases (overturned, distinguished, followed, criticized, etc.) is a foundational legal-research task where misclassification can mislead attorneys about the current force of a citation. The authors argue standard accuracy is a poor evaluation metric because different misclassifications carry very different risks. They release a new expert-annotated dataset of 239 real-world legal citations and propose Average Severity Error (ASE), a metric that weights errors by the practical impact of the confusion (e.g., calling an overturned case "followed" is worse than calling "distinguished" "followed"). They benchmark current frontier LLMs and observe a performance split: Gemini 2.5 Flash leads on high-level classification at 79.1% accuracy, while GPT-5-mini wins on the more complex fine-grained schema at 67.7%. The work establishes a baseline for legal precedent treatment, contributes a context-rich evaluation dataset, and demonstrates an evaluation methodology tailored to risk-sensitive professional tasks. The small dataset (239 citations) is a limitation, but the ASE metric and the per-model split (no model dominates both schemas) provide useful signal for anyone integrating LLMs into legal research workflows where citation reliability is a compliance concern.

### Key Takeaways
- Average Severity Error captures the asymmetric risk profile of legal-citation mistakes far better than plain accuracy.
- No frontier model dominates: Gemini 2.5 Flash wins on coarse-grained tagging, GPT-5-mini wins on fine-grained schema, suggesting task-specific routing in legal AI.
- Top fine-grained accuracy is still only 67.7%, indicating that LLM-driven citation validation remains too unreliable for unattended legal-research use.

---

## 4. Membership Inference Attacks on Discrete Diffusion Language Models

**Authors:** Shailesh Kasivelrajan
**Link:** [Membership Inference Attacks on Discrete Diffusion Language Models](https://arxiv.org/abs/2605.16445)
**Tags:** cs.LG, cs.AI

### Summary
Masked Diffusion Language Models (MDLMs) replace autoregressive generation with iterative demasking, and their privacy properties have been largely unstudied. This work shows that fine-tuned MDLMs are substantially more vulnerable to membership inference attacks (MIA) than current grey-box baselines indicated. The author extracts a 46-dimensional feature vector from the model's reconstruction loss at four masking ratios and trains XGBoost and MLP classifiers on top. On the MIMIR benchmark across six text domains, XGBoost reaches a mean AUC of 0.878 (peaking at 0.930 on Pile-CC), beating the SAMA grey-box baseline by 0.062 AUC on average. A leave-one-signal-out ablation reveals that the ELBO trajectory carries almost all the signal (removing it drops mean AUC by 0.130), while attention features contribute less than 0.003 — a clean attribution that simplifies future defense design. The author also designs a shadow-model transfer attack: three surrogate MDLMs trained on data from unrelated domains generate classifier labels without any access to the target domain, yet still hit 0.858 mean AUC, within 0.020 of the white-box oracle. This establishes shadow-model transfer as a practical attack path that does not require co-domain data and raises the bar for MDLM privacy defenses, with direct implications for any health, legal, or proprietary fine-tuning on diffusion-style language models.

### Key Takeaways
- Fine-tuned masked diffusion LMs leak training-set membership well above prior estimates (0.878 mean AUC, peaking at 0.930).
- The ELBO trajectory across masking ratios is the dominant leakage signal — a concrete target for privacy-preserving training defenses.
- A three-shadow-model transfer attack achieves 0.858 AUC without co-domain access, making MDLM membership inference practical even with minimal attacker knowledge.

---

## 5. ShadowMerge: A Novel Poisoning Attack on Graph-Based Agent Memory via Relation-Channel Conflicts

**Authors:** Yang Luo, Zifeng Kang, Tiantian Ji, Xinran Liu, Yong Liu, Shuyu Li, Lingyun Peng
**Link:** [ShadowMerge: A Novel Poisoning Attack on Graph-Based Agent Memory via Relation-Channel Conflicts](https://arxiv.org/abs/2605.09033)
**Tags:** cs.CR, cs.AI

### Summary
Graph-based agent memory is increasingly used to support structured long-term recall and multi-hop reasoning in LLM agents, but it introduces a new poisoning surface: an attacker who can inject a crafted relation into graph memory can have it retrieved and used to steer agent behavior later. Existing poisoning attacks targeting flat text records mostly fail against graph memory because malicious relations are dropped during extraction, fail to merge into the target anchor's neighborhood, or never get retrieved. ShadowMerge resolves these three barriers by exploiting "relation-channel conflicts": a poisoned relation shares the same query-activated anchor and canonicalized relation channel as benign evidence while carrying a conflicting value. The authors design AIR, a pipeline that wraps the conflict in an ordinary-looking interaction so the graph-memory system extracts, merges, and retrieves it normally. Evaluated on Mem0 across PubMedQA, WebShop, and ToolEmu, ShadowMerge achieves a 93.8% mean attack success rate — 50.3 absolute points above the best baseline — while leaving unrelated benign tasks essentially untouched. Mechanism studies show it overcomes all three prior limitations, and defense analysis shows that representative input-side filters are insufficient. The authors disclosed findings to affected graph-memory vendors and open-sourced the attack. The work is a strong signal that the rapid adoption of graph memory in agentic frameworks is outpacing the security tooling needed to harden it.

### Key Takeaways
- ShadowMerge breaks graph-based agent memory at 93.8% ASR, a 50-point jump over prior poisoning attacks that fail on graph structures.
- Conflicting-value relations on shared anchors slip past extraction, merging, and retrieval filters that handled text-only memory poisoning.
- Input-side defenses are insufficient, so graph-memory systems (Mem0 and similar) likely need provenance- or anomaly-aware retrieval to mitigate.

---

## 6. Lying with Truths: Open-Channel Multi-Agent Collusion for Belief Manipulation via Generative Montage

**Authors:** Jinwei Hu, Xinmiao Huang, Youcheng Sun, Yi Dong, Xiaowei Huang
**Link:** [Lying with Truths: Open-Channel Multi-Agent Collusion for Belief Manipulation via Generative Montage](https://arxiv.org/abs/2601.01685)
**Tags:** cs.CL, cs.AI, cs.MA

### Summary
As LLMs become autonomous agents that synthesize real-time information, their reasoning capability becomes an attack surface. This paper introduces a novel threat in which colluding agents steer the beliefs of a victim agent using only truthful evidence fragments distributed through public channels — no covert communication, no backdoors, no fabricated documents. The authors formalize the first "cognitive collusion" attack and propose Generative Montage, a Writer–Editor–Director framework that constructs deceptive narratives through adversarial debate and coordinated posting of evidence fragments, inducing the victim to internalize and propagate fabricated conclusions. They build CoPHEME, a dataset derived from real-world rumor events, and simulate attacks across 14 LLM families. Attack success reaches 74.4% on proprietary models and 70.6% on open-weights models, and counterintuitively, stronger reasoning capability increases susceptibility — reasoning-specialized models are more easily manipulated than base models or simple prompts, suggesting that overthinking is itself a vulnerability. False beliefs then cascade to downstream judges with >60% deception rates, demonstrating a socio-technical risk: once a victim is deceived, its outputs poison the broader information ecosystem. The implementation and data are public. The result is a sharp warning that purely "truthful" content moderation cannot defend against coordinated framing attacks, and that the next wave of agent safety work has to address evidence selection and aggregation, not just content classification.

### Key Takeaways
- Coordinated agents can steer beliefs using only truthful fragments — content-moderation pipelines that filter falsehoods do not catch this attack.
- Stronger reasoning makes models more, not less, vulnerable, inverting a common safety assumption about reasoning-specialized models.
- Deceived victim agents transmit false beliefs to downstream judges at >60% rates, showing a cascading socio-technical risk to agent ecosystems.

---

## 7. White-Box Sensitivity Auditing with Steering Vectors

**Authors:** Hannah Cyberey, Yangfeng Ji, David Evans
**Link:** [White-Box Sensitivity Auditing with Steering Vectors](https://arxiv.org/abs/2601.16398)
**Tags:** cs.CY, cs.CL, cs.LG

### Summary
Algorithmic audits are central to enforcing regulatory and operator requirements on AI systems, but most current LLM audits rely on black-box input/output testing. That approach is limited to tests that can be expressed in the input space (often via heuristics) and tends to miss abstract socially relevant properties such as gender bias, where the model's internal dependence on protected attributes is hard to expose with text prompts alone. The authors propose a white-box sensitivity auditing framework that uses activation steering to probe a model's internal sensitivity to concepts critical to its intended function. They demonstrate the method on bias audits across four simulated high-stakes LLM decision tasks (e.g., resume screening) and show that their internal sensitivity tests reliably reveal substantial dependence on protected attributes even when standard black-box bias evaluations indicate little or no bias. This complements rather than replaces black-box auditing: it gives regulators and operators a sharper tool when they have white-box access (open-weights or first-party deployments), and surfaces hidden biases that input perturbation tests cannot reach. Code is openly available. The work has direct implications for emerging audit regimes (EU AI Act, NIST risk frameworks) that may soon mandate auditability for high-risk uses but currently lack standardized internal-test methodology.

### Key Takeaways
- Steering-vector probes expose protected-attribute dependence that input-only black-box bias tests miss in high-stakes decision tasks.
- White-box auditing is a practical complement to behavior-only audits for open-weights or first-party LLM deployments under regulatory scrutiny.
- The released code positions the technique as a starting point for standardized internal-test methodology in AI audit regimes.

---

## 8. Factored Causal Representation Learning for Robust Reward Modeling in RLHF

**Authors:** Yupei Yang, Lin Yang, Wanxi Deng, Lin Qu, Fan Feng, Biwei Huang, Shikui Tu, Lei Xu
**Link:** [Factored Causal Representation Learning for Robust Reward Modeling in RLHF](https://arxiv.org/abs/2601.21350)
**Tags:** cs.LG

### Summary
Reliable reward models are essential for aligning LLMs to human preferences via RLHF, but standard reward models latch onto spurious features that are not causally related to human labels (response length, sycophantic phrasing, formatting), producing reward hacking where high predicted reward does not translate into better actual behavior. The authors take a causal-representation perspective: they propose a factored framework that decomposes the model's contextual embedding into (1) causal factors sufficient for reward prediction and (2) non-causal factors capturing reward-irrelevant attributes such as length or sycophancy. The reward head is constrained to depend only on the causal component. They additionally train an adversarial head to predict reward from non-causal factors, with gradient reversal driving those factors away from encoding reward-relevant information. Experiments on mathematical and dialogue tasks show more robust reward models and consistent downstream RLHF gains over state-of-the-art baselines, and length/sycophancy ablations confirm reduced reward hacking. The approach is architecturally simple to bolt onto existing reward model training pipelines and complements other reward-hacking defenses (data curation, ensembling). Limitations include reliance on the model designer identifying the right non-causal targets to suppress, and the usual challenge that causal claims in deep representations are validated empirically rather than formally. Still, the consistent length/sycophancy reductions are practical wins for alignment teams.

### Key Takeaways
- Decomposing reward-model embeddings into causal and non-causal factors and constraining the reward head to the causal part reduces reward hacking.
- An adversarial head with gradient reversal actively scrubs reward-relevant signal from the non-causal subspace, complementing the architectural split.
- Validated on math and dialogue, with explicit reductions in length and sycophancy bias — concrete metrics RLHF teams already track.

---

## 9. VLM-AutoDrive: Post-Training Vision-Language Models for Safety-Critical Autonomous Driving Events

**Authors:** Mohammad Qazim Bhat, Yufan Huang, Niket Agarwal, Hao Wang, Michael Woods, John Kenyon, Tsung-Yi Lin, Xiaodong Yang, Ming-Yu Liu, Kevin Xie
**Link:** [VLM-AutoDrive: Post-Training Vision-Language Models for Safety-Critical Autonomous Driving Events](https://arxiv.org/abs/2603.18178)
**Tags:** cs.CV, cs.AI

### Summary
Ego-centric dashcam footage is exploding in volume, but detecting safety-critical events like collisions and near-collisions is hard because such scenarios are brief, rare, and not well-represented in generic vision training. Off-the-shelf multimodal LLMs underperform here due to domain and temporal misalignment with driving footage. VLM-AutoDrive is a modular post-training framework for adapting pretrained VLMs to high-fidelity anomaly detection. It combines metadata-derived captions, LLM-generated descriptions, visual question answering (VQA) pairs, and chain-of-thought reasoning supervision to produce a domain-aligned, interpretable model. The headline result is dramatic: NVIDIA's Cosmos-Reason1 7B exhibits near-zero collision recall zero-shot, but fine-tuning with VLM-AutoDrive lifts collision F1 from 0.00 to 0.69 and overall accuracy from 35.35% to 77.27% on real-world Nexar dashcam videos. The model also produces interpretable reasoning traces, which matter for post-incident analysis, regulatory review, and AV system debugging. The framework is presented as a scalable recipe for adapting general-purpose VLMs to safety-critical, temporally localized perception tasks — relevant to AV vendors, fleet telematics providers, and insurers building automated event triage. Limitations include evaluation on a single dataset family and the need for substantial annotated post-training data, but the recall jump from 0% to working levels demonstrates that the bottleneck is alignment, not capacity, for current 7B-class VLMs.

### Key Takeaways
- Generic VLMs are essentially useless out-of-the-box for collision detection (near-zero recall), but targeted post-training with VLM-AutoDrive lifts collision F1 from 0.00 to 0.69.
- Combining captions, VQA pairs, and chain-of-thought supervision preserves interpretable reasoning traces — important for AV review and regulation.
- The pipeline shows that the safety-critical perception gap in driving VLMs is an alignment problem more than a capacity one.

---

## 10. Artificial Intolerance: Stigmatizing Language in Clinical Documentation Skews Large Language Model Decision-Making

**Authors:** Jen-tse Huang, Didi Zhou, Faith Kamau, Amy Oh, Anne R. Links, Mark Dredze, Mary Catherine Beach, Somnath Saha
**Link:** [Artificial Intolerance: Stigmatizing Language in Clinical Documentation Skews Large Language Model Decision-Making](https://arxiv.org/abs/2605.17228)
**Tags:** cs.CL

### Summary
LLMs are being deployed in clinical decision support and medical documentation, but their robustness to subtle linguistic variations — especially stigmatizing language (SL) common in human-authored clinical notes — has been under-explored. This study systematically evaluates nine frontier LLMs across four stigmatized medical conditions, using clinical vignettes injected with varying intensities and phenotypes of SL (doubt, blame, and maligning). Every model evaluated exhibited substantial bias: clinical decision-making was significantly skewed toward less aggressive patient management when stigmatizing language was present. The authors observe high sensitivity to linguistic framing, with a single SL sentence sufficient to alter outputs, and a clear dose-response relationship between SL intensity and skew. They also evaluate two standard prompt-based mitigations — chain-of-thought reasoning and self-debiasing prompts — and find both have limited efficacy: models struggle to explicitly identify SL while remaining implicitly influenced by it. The work exposes a critical fairness and robustness vulnerability that could automate health disparities at scale: stigmatizing notes (disproportionately authored about marginalized patients) systematically downgrade the care recommendations LLMs produce. The authors argue for algorithmic guardrails specifically designed to detect and neutralize SL, rather than relying on prompt-level mitigations. The implications are direct for any healthcare provider piloting LLM-based clinical decision support, and for regulators considering fairness standards in clinical AI.

### Key Takeaways
- All nine frontier LLMs evaluated downgrade patient-management recommendations when clinical notes contain stigmatizing language, with clear dose-response behavior.
- A single SL sentence is enough to shift outputs — bias is not a rare-token effect but a robust framing vulnerability.
- Chain-of-thought and self-debiasing prompts fail to neutralize the bias, arguing for dedicated SL-detection guardrails rather than prompt-level fixes.

---

## 11. PropGuard: Safeguarding LLM-MAS via Propagation-Aware Exploration and Remediation

**Authors:** Bingyu Yan, Xiaoming Zhang, Jinyu Hou, Chaozhuo Li, Ziyi Zhou, Xiaozhe Zhang, Litian Zhang
**Link:** [PropGuard: Safeguarding LLM-MAS via Propagation-Aware Exploration and Remediation](https://arxiv.org/abs/2605.16346)
**Tags:** cs.LG, cs.AI, cs.CR

### Summary
LLM-based multi-agent systems (LLM-MAS) coordinate role-specialized agents that share tools, memory, and messages, but those interaction channels also let a malicious instruction propagate across agents and rounds into system-level compromise. Existing defenses lean on local filtering or graph-based anomaly detection, which often fail to trace fine-grained propagation paths and disrupt benign collaboration when they try to remediate contaminated state. PropGuard is a propagation-aware framework that constructs a dual-view spatio-temporal graph combining response-centric risk estimation with full-state evidence preservation. Guided by these risk priors, a GE-GRPO-trained inspector sequentially explores the full-state graph to recover compact, suspicious propagation subgraphs. PropGuard then verifies harmful propagation through subgraph-aware diagnosis and applies source-guided remediation that corrects upstream contamination and replays affected downstream interactions, rather than nuking the whole conversation. Evaluated across four communication architectures and five attack settings, PropGuard consistently lowers attack success while keeping task-level defense success high, hitting a favorable effectiveness-efficiency trade-off. The work fits a growing thread of MAS-security research — alongside ShadowMerge and Trust No Tool in this same digest — that recognizes attackers no longer need to land a single-shot prompt injection: they can plant content that drifts across agent boundaries and only manifests downstream. The remediation-by-replay design is especially notable because it preserves benign agent work rather than discarding contaminated trajectories wholesale.

### Key Takeaways
- LLM-MAS attacks now propagate across messages, tools, and memories — local-filter defenses cannot trace these chains.
- A dual-view spatio-temporal graph plus GE-GRPO-trained inspector recovers compact propagation subgraphs to localize the source.
- Source-guided remediation replays affected interactions instead of dropping them, preserving benign work while neutralizing the attack.

---

## 12. Trust No Tool: Evaluating and Defending LLM Agents under Untrusted Tool Feedback

**Authors:** Lecheng Yan, Ruizhe Li, Xicheng Han, Wenxi Li, Binwu Wang, Longyue Wang, Chenyang Lyu, Guanhua Chen
**Link:** [Trust No Tool: Evaluating and Defending LLM Agents under Untrusted Tool Feedback](https://arxiv.org/abs/2605.17453)
**Tags:** cs.CR, cs.CL

### Summary
Tool-using LLM agents increasingly drive consequential decisions, but most agent-security benchmarks implicitly assume tool feedback is trustworthy once a tool is selected. This work studies a different failure mode the authors call "cognitive poisoning": a malicious tool behaves plausibly during exploration, accumulates trust through benign-looking feedback, and becomes harmful only when hidden state conditions align with the final executable action. To study this, they build TRUST-Bench — 1,970 hidden-trigger tool-compromise episodes with matched safe controls — introduce GuardedJoint, an asymmetric penalty metric that better reflects real deployment risk by punishing committed harmful actions much more than missed flags on safe ones, and present VISTA-Guard, a backbone-agnostic framework for final-action risk scoring. VISTA-Guard's core idea is to abstract multi-step tool interaction into structured environment variables that capture trust-formation dynamics, then score the risk of the final executable action from this trajectory-conditioned representation rather than from local prompt text. Experiments show prompt-centric heuristics, scalarized features, and zero-shot judges all fail, while trajectory-aware final-action scoring discriminates well in-domain and remains effective under out-of-distribution transfer (84.2 in-domain, 56.9 OOD under GuardedJoint), with single-side optimizers collapsing to zero. The framing reorients agent security: in black-box tool ecosystems, the defense target is not the prompt or tool descriptor but the trajectory along which trust is formed and the moment it is committed through a final action.

### Key Takeaways
- "Cognitive poisoning" — tools that earn trust before turning harmful — defeats prompt-level and zero-shot-judge defenses common in agent stacks.
- TRUST-Bench (1,970 episodes) plus the GuardedJoint asymmetric metric give the field a deployment-aligned way to evaluate this failure mode.
- Risk scoring should target the trajectory leading to the final action, not local prompt content — a structural reframing for agent guardrails.

---
