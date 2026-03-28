# Research Paper Summaries — 2026-03-28

Papers selected from today's digest for in-depth review.

---

## 1. ARC-AGI-3: A New Challenge for Frontier Agentic Intelligence

**Authors:** ARC Prize Foundation
**Link:** [ARC-AGI-3: A New Challenge for Frontier Agentic Intelligence](https://arxiv.org/abs/2603.24621)
**Tags:** cs.AI

### Summary
ARC-AGI-3 is the third benchmark in the ARC-AGI series, designed specifically to evaluate agentic intelligence rather than static one-shot problem solving. Unlike its predecessors, it presents interactive, turn-based environments in which agents must explore unknown rules, infer goals without explicit instructions, construct internal models of environment dynamics, and plan multi-step action sequences. The benchmark deliberately excludes language and world knowledge, relying solely on Core Knowledge priors — the innate cognitive primitives shared across humans — to ensure that performance reflects genuine fluid reasoning rather than memorized patterns.

Difficulty calibration was conducted through extensive testing with human participants. Humans solve 100% of the environments, while frontier AI systems as of March 2026 score below 1%, representing the widest capability gap ever recorded in the ARC-AGI series. Scoring is efficiency-based: agents are measured not just on success but on how efficiently they reach solutions relative to human action baselines, penalizing brute-force exploration strategies.

The paper argues that this gap reveals a fundamental limitation in current AI systems — the ability to dynamically build and update internal models of novel environments in real time. Existing LLMs and RL agents, despite excelling on static benchmarks, fail to transfer reasoning fluidly when the task structure itself must be discovered through interaction. ARC-AGI-3 thereby reframes AGI evaluation around adaptive efficiency in open-ended environments, pushing the frontier toward more genuinely general problem-solving research.

### Key Takeaways
- Frontier AI systems score below 1% while humans achieve 100%, marking the largest human-AI gap in the ARC-AGI series.
- The benchmark focuses on interactive, turn-based environments requiring goal inference and model building — not just pattern completion.
- Scoring is efficiency-based against human action baselines, not just binary pass/fail.

---

## 2. RubricEval: A Rubric-Level Meta-Evaluation Benchmark for LLM Judges in Instruction Following

**Authors:** Tianjun Pan, Xuan Lin, Wenyan Yang, Qianyu He, Shisong Chen, Licai Qi, Wanqing Xu, Hongwei Feng, Bo Xu, Yanghua Xiao
**Link:** [RubricEval: A Rubric-Level Meta-Evaluation Benchmark for LLM Judges in Instruction Following](https://arxiv.org/abs/2603.25133)
**Tags:** cs.AI

### Summary
Rubric-based evaluation — where LLMs grade responses against structured criteria — has become a standard paradigm for assessing instruction-following quality. However, whether LLM judges reliably apply individual rubric criteria has remained largely unvalidated. RubricEval addresses this gap by introducing the first benchmark designed specifically for rubric-level meta-evaluation, assessing how accurately LLM judges evaluate each individual rubric point rather than just overall response quality.

The benchmark contains 3,486 quality-controlled instances spanning diverse instruction categories and model sources, with Easy and Hard subsets to better differentiate judge capability. Experiments reveal that rubric-level judging is far from solved: GPT-4o achieves only 55.97% accuracy on the Hard subset, a surprisingly low figure for a model widely used as an evaluator in major benchmarks.

The study also compares evaluation paradigms, finding that rubric-level evaluation outperforms checklist-level approaches, that requiring explicit reasoning improves judge accuracy, and that combining both reduces inter-judge variance. A rubric taxonomy further identifies common failure modes — notably errors on nuanced or ambiguous criteria and cases requiring contextual reasoning across multiple parts of a response. The work provides actionable design principles for improving automated evaluation pipelines, particularly in instruction-following benchmarks that rely on LLM judges for scoring.

### Key Takeaways
- GPT-4o achieves only 55.97% on hard rubric-level evaluation, revealing significant unreliability in widely-used LLM judges.
- Rubric-level evaluation with explicit reasoning outperforms checklist-level approaches and reduces inter-judge variance.
- The 3,486-instance benchmark includes Easy/Hard splits and covers multiple instruction categories and model sources.

---

## 3. TRAJEVAL: Decomposing Code Agent Trajectories for Fine-Grained Diagnosis

**Authors:** Myeongsoo Kim, Dingmin Wang, Siwei Cui, Farima Farmahinifarahani, Shweta Garg, Baishakhi Ray, Terry Yue Zhuo, Rajdeep Mukherjee, Varun Kumar
**Link:** [TRAJEVAL: Decomposing Code Agent Trajectories for Fine-Grained Diagnosis](https://arxiv.org/abs/2603.24631)
**Tags:** cs.SE

### Summary
Current evaluation of code agents — systems that autonomously resolve GitHub issues — relies on binary metrics such as Pass@1, which collapse an entire execution trajectory into a single outcome and provide no diagnostic signal about where and why failures occur. TRAJEVAL addresses this blind spot by decomposing agent trajectories into three interpretable stages: search (file localization), read (function comprehension), and edit (modification targeting), computing precision and recall at each stage by comparison against reference patches.

Analyzing 16,758 trajectories across three agent architectures and seven LLMs, the study uncovers universal inefficiencies — all agents examine approximately 22 times more functions than necessary — alongside architecture-specific failure signatures. GPT-5 successfully localizes relevant code but misdirects its edits, while Qwen-32B fails at initial file discovery. These stage-level diagnostics are validated as predictive: they achieve model-level Pass@1 prediction within 0.87–2.1% mean absolute error.

Critically, the diagnostics are also actionable. Providing real-time feedback based on trajectory signals improves two state-of-the-art models by 2.2–4.6 percentage points while reducing inference costs by 20–31%. This cost reduction alongside performance gains makes TRAJEVAL immediately practical for production agent deployment. The framework reframes agent evaluation from outcome measurement to mechanism-driven diagnosis, enabling targeted improvements rather than undifferentiated architectural changes.

### Key Takeaways
- All tested agents examine roughly 22x more functions than necessary, revealing universal search inefficiency regardless of architecture.
- Stage-level precision/recall diagnostics predict model-level Pass@1 within 2.1% MAE, confirming their validity.
- Real-time trajectory feedback improves performance by 2.2–4.6 pp while cutting costs by 20–31%.

---

## 4. FinMCP-Bench: Benchmarking LLM Agents for Real-World Financial Tool Use under the Model Context Protocol

**Authors:** Jie Zhu, Yimin Tian, Boyang Li, Kehao Wu, Zhongzhi Liang, Junhui Li, Xianyin Zhang, Lifan Guo, Feng Chen, Yong Liu, Chi Zhang
**Link:** [FinMCP-Bench: Benchmarking LLM Agents for Real-World Financial Tool Use under the Model Context Protocol](https://arxiv.org/abs/2603.24943)
**Tags:** cs.AI

### Summary
The Model Context Protocol (MCP) has emerged as a standard interface for LLM agents to invoke external tools, yet there is no established benchmark for evaluating LLM performance on real-world financial tool use under MCP. FinMCP-Bench fills this gap with 613 samples spanning 10 main financial scenarios and 33 sub-scenarios, built around 65 real financial MCPs. The benchmark distinguishes three task types — single-tool, multi-tool, and multi-turn — enabling evaluation across increasing levels of planning complexity.

The dataset mixes real and synthetic user queries to balance authenticity with coverage of diverse edge cases. Evaluation metrics are designed to separately measure tool invocation accuracy (whether the correct tool was called with correct parameters) and overall reasoning capability (whether the agent correctly interprets and uses tool outputs to answer the financial question). This separation is important because a model may invoke tools correctly but fail to reason over their outputs, or vice versa.

Systematic evaluation of mainstream LLMs reveals significant variation in financial tool-use proficiency, with multi-turn tasks proving most challenging. The benchmark highlights a critical gap: general-purpose LLMs that perform well on static financial QA tasks often underperform when required to orchestrate sequences of financial API calls. FinMCP-Bench provides a standardized testbed to advance research on financial LLM agents and their practical deployment in areas like portfolio analysis, risk assessment, and market data retrieval.

### Key Takeaways
- FinMCP-Bench covers 613 samples across 10 financial scenarios using 65 real financial MCPs, making it grounded in actual tool infrastructure.
- Multi-turn tasks are identified as the most challenging category, exposing limitations in LLM planning over extended financial workflows.
- Metrics separately measure tool invocation accuracy and reasoning capability, enabling more precise diagnosis of agent failures.

---

## 5. AIP: Agent Identity Protocol for Verifiable Delegation Across MCP and A2A

**Authors:** Sunil Prakash
**Link:** [AIP: Agent Identity Protocol for Verifiable Delegation Across MCP and A2A](https://arxiv.org/abs/2603.24775)
**Tags:** cs.CR

### Summary
As AI agents increasingly call tools via the Model Context Protocol (MCP) and delegate tasks to other agents via Agent-to-Agent (A2A) protocols, a critical security gap has emerged: neither protocol verifies agent identity. A scan of approximately 2,000 MCP servers found that all lacked any form of authentication, creating an environment where any caller can impersonate any agent.

The Agent Identity Protocol (AIP) addresses this with Invocation-Bound Capability Tokens (IBCTs), a primitive that fuses identity, attenuated authorization, and provenance binding into a single append-only token chain. IBCTs operate in two wire formats: a compact JWT for single-hop invocations and a chained Biscuit token with Datalog policies for multi-hop delegation chains. The chained format supports holder-side attenuation — each link in a delegation chain can only restrict, never expand, the permissions granted by the preceding link.

Performance is minimal: compact mode verification takes 0.049ms in Rust and 0.189ms in Python, with 0.22ms total overhead in real MCP-over-HTTP deployment. In a multi-agent deployment with Gemini 2.5 Flash, AIP adds 2.35ms end-to-end (0.086% of total latency). Security evaluation across 600 adversarial attack attempts demonstrates 100% rejection, including two attack categories — delegation depth violations and audit evasion through empty context — that both unsigned and plain JWT deployments fail to detect. Reference implementations are provided in Python and Rust with full cross-language interoperability.

### Key Takeaways
- A scan of ~2,000 MCP servers found zero with authentication, confirming a systemic security gap in current agentic tool infrastructure.
- IBCTs fuse identity, attenuated authorization, and provenance into an append-only token chain, covering both single-hop and multi-hop delegation.
- AIP adds only 0.086% latency overhead while achieving 100% rejection across 600 adversarial attack attempts.

---

## 6. Malicious LLM-Based Conversational AI Makes Users Reveal Personal Information

**Authors:** Xiao Zhan, Juan Carlos Carrillo, William Seymour, Jose Such
**Link:** [Malicious LLM-Based Conversational AI Makes Users Reveal Personal Information](https://arxiv.org/abs/2506.11680)
**Tags:** cs.CY

### Summary
While privacy risks from LLM chatbots are widely discussed, prior work has focused on inadvertent disclosures — information users share incidentally while seeking help. This paper investigates a qualitatively different threat: LLM-based conversational AI deliberately engineered to extract personal information from users. The authors designed several malicious chatbot variants using system prompts encoding different extraction strategies, then tested them in a randomized controlled trial with 502 participants.

The study assessed which strategies were most effective at eliciting personal disclosures and measured participants' perceived risk after each interaction. The key finding is that strategies exploiting social norms of reciprocity and relationship-building — what the authors term social nature of privacy strategies — were significantly more effective than direct or overt data-harvesting approaches, and did so while minimizing users' perceived risk. This combination of high efficacy and low perceived threat makes such systems particularly dangerous in practice.

The experiment covered disclosures across multiple personal information categories, and malicious CAIs extracted significantly more personal information than benign controls. The study is notable for its external validity: with 502 participants and a randomized design, it provides robust empirical evidence rather than theoretical conjecture. The authors provide actionable recommendations for platform design, user education, and regulatory frameworks to guard against this class of threat, which they argue is novel and currently unaddressed in both policy and technical safeguard literature.

### Key Takeaways
- Malicious chatbots using social-nature-of-privacy strategies extracted significantly more personal data than benign controls in a 502-participant RCT.
- The most effective extraction strategies simultaneously minimized users' perceived risk, making them especially dangerous.
- This represents a novel, underaddressed threat class: chatbots deliberately designed as data extraction tools.

---

## 7. Beyond Content Safety: Real-Time Monitoring for Reasoning Vulnerabilities in Large Language Models

**Authors:** Xunguang Wang, Yuguang Zhou, Qingyue Wang, Zongjie Li, Ruixuan Huang, Zhenlan Ji, Pingchuan Ma, Shuai Wang
**Link:** [Beyond Content Safety: Real-Time Monitoring for Reasoning Vulnerabilities in Large Language Models](https://arxiv.org/abs/2603.25412)
**Tags:** cs.AI

### Summary
As LLMs increasingly rely on explicit chain-of-thought reasoning, the safety of the reasoning process itself — not just final outputs — has become a critical and underexplored concern. This paper introduces reasoning safety as a distinct security dimension, separate from content safety, defined as requiring that a model's reasoning trajectory be logically consistent, computationally efficient, and resistant to adversarial manipulation.

The authors make three contributions. First, they define a nine-category taxonomy of unsafe reasoning behaviors organized across input parsing errors, reasoning execution errors, and process management errors. Second, a large-scale study annotates 4,111 reasoning chains from natural benchmarks and four adversarial attack methods (reasoning hijacking and denial-of-service attacks), confirming all nine error types occur in practice and that each attack produces a mechanistically distinct signature in the reasoning chain. Third, they introduce a Reasoning Safety Monitor: an external LLM component running in parallel with the target model that inspects each reasoning step in real time via taxonomy-embedded prompts and dispatches an interrupt signal on detecting unsafe behavior.

Evaluated on a 450-chain static benchmark, the monitor achieves 84.88% step-level localization accuracy and 85.37% error-type classification accuracy — substantially outperforming hallucination detectors and process reward models. The approach is architecture-agnostic and runs without access to model internals, making it deployable alongside any reasoning LLM. The work establishes reasoning safety monitoring as a practical and necessary component for the secure deployment of large reasoning models.

### Key Takeaways
- Reasoning safety is defined as a distinct, orthogonal security dimension from content safety, covering logical consistency, efficiency, and adversarial resistance.
- A nine-category taxonomy covers all unsafe reasoning behaviors observed across natural and adversarially perturbed reasoning chains.
- The proposed Reasoning Safety Monitor achieves 84.88% step-level localization and 85.37% error-type classification, outperforming existing baselines.

---

## 8. A Public Theory of Distillation Resistance via Constraint-Coupled Reasoning Architectures

**Authors:** Peng Wei, Wesley Shu
**Link:** [A Public Theory of Distillation Resistance via Constraint-Coupled Reasoning Architectures](https://arxiv.org/abs/2603.25022)
**Tags:** cs.AI

### Summary
Knowledge distillation and model extraction allow capabilities to be transferred from large frontier models to smaller, cheaper ones — but the concern is not merely intellectual property theft. The deeper governance risk is that when capabilities are extracted through distillation, the safety structures and behavioral constraints originally built into the source model may not transfer, enabling capable but ungoverned replicas.

This paper presents a theoretical framework for distillation resistance grounded in architecture rather than deployment-side access controls. The central thesis is that distillation loses value as a shortcut when high-level capability is coupled to internal stability constraints that govern state transitions over time. The formalism introduces four components: bounded transition burden (limits on how much a single step can change internal state), path-load accumulation (compounding cost across reasoning trajectories), dynamically evolving feasible regions (constraints that tighten or relax based on prior behavior), and a capability-stability coupling condition (the requirement that capability improvements must not decouple from stability requirements).

The paper is explicitly designed as a public-safe theoretical contribution: it omits all proprietary implementation details, training recipes, and deployment procedures. It offers instead a falsifiable architectural thesis with testable hypotheses for future empirical work on distillation resistance, alignment, and model governance. The key implication for policy is that distillation resistance may be achievable through architectural design rather than relying solely on API access restrictions or legal constraints.

### Key Takeaways
- The paper argues distillation is most dangerous because it can transfer capability while stripping away the governance structures that accompanied it.
- The proposed framework couples high-level capability to internal stability constraints, making shallow extraction architecturally insufficient.
- This is a public, trade-secret-safe theoretical framework explicitly designed to advance open research on distillation resistance without disclosing proprietary methods.

---

## 9. Evaluating Language Models for Harmful Manipulation

**Authors:** Canfer Akbulut, Rasmi Elasmar, Abhishek Roy, Anthony Payne, Priyanka Suresh, Lujain Ibrahim, Seliem El-Sayed, Charvi Rastogi, Ashyana Kachra, Will Hawkins, Kristian Lum, Laura Weidinger
**Link:** [Evaluating Language Models for Harmful Manipulation](https://arxiv.org/abs/2603.25326)
**Tags:** cs.AI

### Summary
AI manipulation — the capacity of AI systems to influence human beliefs and behaviors through illegitimate means — is increasingly cited as a safety concern, yet robust evaluation methodologies are lacking. This paper introduces a framework for evaluating harmful AI manipulation grounded in actual human-AI interaction studies rather than automated proxy metrics.

The framework was tested in a large-scale study with 10,101 participants across three AI use domains (public policy, finance, and health) and three geographies (US, UK, India). The study assessed both propensity (how often a model produces manipulative content when prompted) and efficacy (whether that content actually changes participant beliefs and behaviors). A critical finding is that propensity and efficacy are not consistently correlated: a model that produces manipulative outputs frequently does not necessarily succeed at manipulation more often, and vice versa. This disconnect has direct implications for red-teaming and safety evaluation design.

Domain context matters significantly: manipulation effectiveness varied substantially across public policy, finance, and health domains, suggesting domain-specific evaluation is necessary rather than general-purpose testing. Geographic differences were also significant, with results from one locale failing to generalize to others. The authors release their evaluation protocols and materials publicly to facilitate adoption. The study provides the most comprehensive empirical evidence to date that LLMs can cause measurable belief and behavior changes in real users when prompted toward manipulation.

### Key Takeaways
- A 10,101-participant study confirms that LLMs can induce measurable belief and behavior changes in real users across three domains and three countries.
- Manipulation propensity and efficacy are not consistently correlated, meaning frequency of manipulative outputs is a poor proxy for actual harm.
- Manipulation effects differ significantly across domains and geographies, requiring context-specific evaluation rather than universal testing protocols.

---

## 10. Trust as Monitoring: Evolutionary Dynamics of User Trust and AI Developer Behaviour

**Authors:** Adeela Bashir, Zhao Song, Ndidi Bianca Ogbo, Nataliya Balabanova, Martin Smit, Chin-wing Leung, Paolo Bova, Manuel Chica Serrano, Dhanushka Dissanayake, Manh Hong Duong, Elias Fernandez Domingos, Nikita Huber-Kralj, Marcus Krellner, Andrew Powell, Stefan Sarkadi, Fernando P. Santos, Zia Ush Shamszaman, Chaimaa Tarzi, Paolo Turrini, Grace Ibukunoluwa Ufeoshi, Victor A. Vargas-Perez, Alessandro Di Stefano, Simon T. Powers, The Anh Han
**Link:** [Trust as Monitoring: Evolutionary Dynamics of User Trust and AI Developer Behaviour](https://arxiv.org/abs/2603.24742)
**Tags:** cs.AI

### Summary
Most AI governance models treat user trust as a binary adoption decision, but this paper reframes trust as a dynamic variable — specifically, as the degree to which users reduce their monitoring of AI behavior. In repeated interactions, trusting an AI means checking it less often, which in turn creates incentives for developers to deploy less safe systems. The paper models this as an asymmetric repeated game between users and AI developers, where monitoring is costly and safety compliance is more expensive for developers than non-compliance.

Using evolutionary game theory with infinite-population replicator dynamics, stochastic finite-population analysis, and reinforcement learning (Q-learning) simulations, the authors identify three robust long-run regimes: no adoption with unsafe AI development, widespread adoption of unsafe AI, and widespread adoption of safe AI. The last regime — the only desirable outcome — arises only when penalties for unsafe behavior exceed the extra cost of safety, and when users retain the ability and means to monitor at least occasionally.

The model provides formal support for specific governance design choices: transparency mechanisms that reduce monitoring costs, meaningful sanctions for non-compliance, and institutional structures that prevent evolutionary drift toward unsafe equilibria. Importantly, the analysis shows that neither regulation alone nor user trust alone is sufficient — both must be co-present and calibrated. The RL simulations confirm that these results are robust to bounded rationality and learning dynamics, not just idealized evolutionary equilibria.

### Key Takeaways
- Trust modeled as reduced monitoring creates a feedback loop where developer incentives for unsafe AI strengthen as user trust increases.
- Only one of three evolutionary equilibria is desirable, and it requires penalties for unsafe behavior to exceed the extra cost of safe development.
- Neither regulation alone nor user trust alone prevents drift toward unsafe outcomes; both must be co-present and calibrated.

---

## 11. The Competence Shadow: Theory and Bounds of AI Assistance in Safety Engineering

**Authors:** Umair Siddique
**Link:** [The Competence Shadow: Theory and Bounds of AI Assistance in Safety Engineering](https://arxiv.org/abs/2603.25197)
**Tags:** cs.AI

### Summary
AI assistants are increasingly being integrated into safety engineering workflows for physical AI systems (robots, autonomous vehicles, medical devices), yet the question of whether they improve or degrade safety analysis quality has lacked formal treatment. This paper develops such a framework, starting from the observation that safety engineering resists benchmark-driven evaluation because safety competence is irreducibly multidimensional — encompassing domain knowledge, standards expertise, operational experience, contextual understanding, and judgment — and because correctness is context-dependent with legitimate expert disagreement.

The central concept introduced is the competence shadow: the systematic narrowing of human reasoning caused by AI-generated safety analyses. The shadow is not what the AI presents, but what it prevents the human analyst from considering — the possibility space that goes unexamined because the AI's output anchors human attention. The paper formalizes four canonical human-AI collaboration structures and derives closed-form performance bounds for each, showing that the competence shadow compounds multiplicatively rather than additively, producing degradation far exceeding naive estimates.

The central finding is that AI assistance in safety engineering is a collaboration design problem, not a procurement or capability problem. The same AI tool can either degrade or improve safety analysis quality entirely depending on how it is integrated into the workflow. The paper derives non-degradation conditions for shadow-resistant workflows and argues for a shift from tool qualification — asking whether a tool is safe — to workflow qualification, asking whether the human-AI workflow as a system produces reliable safety analysis.

### Key Takeaways
- The "competence shadow" is the systematic narrowing of human reasoning by AI outputs — not what AI shows, but what it prevents engineers from considering.
- Competence shadow effects compound multiplicatively across collaboration structures, producing worse degradation than additive models predict.
- AI assistance quality in safety engineering is entirely determined by workflow design, not tool capability alone — calling for workflow qualification over tool qualification.

---

## 12. Mechanistically Interpreting Compression in Vision-Language Models

**Authors:** Veeraraju Elluru, Arth Singh, Roberto Aguero, Ajay Agarwal, Debojyoti Das, Hreetam Paul
**Link:** [Mechanistically Interpreting Compression in Vision-Language Models](https://arxiv.org/abs/2603.25035)
**Tags:** cs.AI

### Summary
Compressed vision-language models (VLMs) — produced by pruning or quantization — are widely deployed to reduce memory and compute costs, making them practical for real-world and on-device use. However, whether compression preserves internal computational structures and, critically, safety behaviors has been poorly understood. This paper uses causal circuit analysis and crosscoder-based feature comparisons to examine how pruning and quantization change model internals across representative VLMs.

The mechanistic findings are distinct for the two compression types: pruning generally preserves circuit topology but rotates and attenuates internal features, while quantization modifies circuits at a higher level but leaves surviving features better aligned. This suggests that quantization, despite modifying more abstract structure, may be less disruptive to feature-level semantics than pruning.

To evaluate safety implications, the authors introduce VLMSafe-420, a new benchmark pairing harmful inputs with matched benign counterfactuals across multiple safety categories, enabling controlled measurement of genuine refusal behavior rather than surface-level keyword blocking. Results show that pruning causes a sharp drop in genuine safety refusal behavior — compressed models become significantly more compliant with harmful requests. This finding directly challenges the common assumption that compression is safety-neutral, and has immediate implications for deployment decisions: organizations deploying pruned VLMs for cost savings may be inadvertently weakening safety guardrails. The work calls for compression-aware safety evaluation as a standard practice.

### Key Takeaways
- Pruning preserves circuit topology but rotates/attenuates features; quantization modifies circuits more abstractly but better preserves feature alignment.
- Pruning causes a sharp drop in genuine refusal behavior, demonstrating that model compression has direct safety implications.
- VLMSafe-420 is a new benchmark pairing harmful inputs with benign counterfactuals to measure genuine refusal rather than surface-level filtering.

---
