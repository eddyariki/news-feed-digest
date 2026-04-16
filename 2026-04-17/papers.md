# Research Paper Summaries — 2026-04-17

Papers selected from today's digest for in-depth review.

---

## 1. Activation-Guided Local Editing for Jailbreaking Attacks

**Authors:** Jiecong Wang, Haoran Li, Hao Peng, Ziqian Zeng, Zihao Wang, Haohua Du, Zhengtao Yu
**Link:** [Activation-Guided Local Editing for Jailbreaking Attacks](https://arxiv.org/abs/2508.00555)
**Tags:** cs.CR

### Summary
This paper addresses a persistent gap in red-teaming LLMs: existing jailbreak methods each have a fatal flaw. Token-level attacks (e.g., GCG) produce incoherent text and transfer poorly across models; prompt-level attacks (e.g., hand-crafted jailbreak templates) are unscalable and labor-intensive. The proposed AGILE framework bridges both approaches through a two-stage pipeline. In the first stage, the malicious query is rewritten into a plausible scenario that obscures its harmful intent. In the second stage, the model's own hidden states are used to identify the minimal set of token edits needed to steer its internal representation from "malicious" to "benign"—essentially exploiting the model's internals to guide its own circumvention.

The key insight is that activation-guided editing can find fine-grained modifications that fool safety classifiers without destroying the semantic coherence of the prompt. Experiments show AGILE achieves state-of-the-art Attack Success Rate with gains of up to 37.74% over the strongest baseline, and the method transfers effectively to black-box models that were never seen during attack development. Critically, AGILE maintains effectiveness against several prominent defenses, exposing their limitations.

The work is significant for safety researchers because it shows that a model's own internal representations can be weaponized against its safety mechanisms—a direction that conventional perimeter defenses (output filtering, prompt injection detection) cannot easily block. The implication is that robust safety requires interpretability-aware defenses operating on internal states, not just output monitoring.

### Key Takeaways
- Internal model activations can guide minimal, semantically coherent prompt edits that achieve high jailbreak success rates with strong black-box transferability.
- AGILE outperforms the strongest baseline by up to 37.74% on ASR and defeats multiple prominent defense mechanisms.
- Current safeguards are insufficient against activation-informed attacks; future defense development must engage with internal representation steering.

---

## 2. Between a Rock and a Hard Place: The Tension Between Ethical Reasoning and Safety Alignment in LLMs

**Authors:** Shei Pern Chua, Zhen Leng Thai, Kai Jun Teh, Xiao Li, Qibing Ren, Xiaolin Hu
**Link:** [Between a Rock and a Hard Place: The Tension Between Ethical Reasoning and Safety Alignment in LLMs](https://arxiv.org/abs/2509.05367)
**Tags:** cs.CR

### Summary
This paper formalizes a previously underexplored attack surface: the tension between a model's ability to reason morally and its binary safe/unsafe alignment. Safety alignment treats every request as either permissible or not, but real ethical dilemmas often involve genuine tradeoffs where a "harmful" action can be framed as the morally necessary choice. The authors introduce TRIAL (Threat Reasoning In Adversarial Loops), a multi-turn red-teaming methodology that exploits this gap. By progressively building ethical context across conversation turns—constructing scenarios where refusing to provide harmful information appears morally worse than complying—TRIAL achieves high attack success rates across most tested frontier models.

The mechanism being exploited is not a bug in safety training per se, but an emergent consequence of teaching models to reason ethically: the same capability that allows a model to navigate genuine moral complexity also provides a foothold for adversarial manipulation. Models with stronger ethical reasoning paradoxically become more vulnerable to TRIAL-style attacks.

In response, the authors propose ERR (Ethical Reasoning Robustness), a defense framework built on a Layer-Stratified Harm-Gated LoRA architecture. ERR draws a crucial distinction between instrumental responses (those that enable harm) and explanatory responses (those that analyze ethical frameworks without endorsing harm). In testing, ERR successfully defends against TRIAL-style reasoning attacks while preserving the model's general utility and ethical reasoning capability—a significant result given that previous defenses often degraded model helpfulness.

### Key Takeaways
- Safety alignment's binary framing leaves models vulnerable when harmful requests are embedded in ethical dilemma contexts—a systematic new attack surface.
- TRIAL, a multi-turn methodology exploiting ethical reasoning, achieves high ASR across most frontier models without requiring any internal model access.
- The ERR defense distinguishes enabling harm from discussing ethics, achieving robust protection without sacrificing model utility.

---

## 3. Formalizing the Safety, Security, and Functional Properties of Agentic AI Systems

**Authors:** Edoardo Allegrini, Ananth Shreekumar, Z. Berkay Celik
**Link:** [Formalizing the Safety, Security, and Functional Properties of Agentic AI Systems](https://arxiv.org/abs/2510.14133)
**Tags:** cs.AI

### Summary
As agentic AI systems grow more complex—orchestrating LLMs, tools, and sub-agents across protocols like MCP and A2A—there is no unified framework for reasoning about what these systems are supposed to guarantee. Individual protocols are analyzed in isolation, creating a semantic gap that makes it impossible to formally verify system-level properties or detect misalignment between components. This paper proposes the first domain-agnostic formal framework for multi-agent AI systems.

The framework centers on two complementary models. The host agent model formalizes the top-level orchestrator: how it receives user tasks, decomposes them, and delegates execution to sub-agents and tools. The task lifecycle model details every state a sub-task can occupy from creation to completion, including error handling transitions. Together they form a unified semantic foundation for multi-agent reasoning.

Grounded in these models, the authors define 30 formal properties—16 for host agents and 14 for task lifecycles—spanning liveness (the system makes progress), safety (bad states are avoided), completeness (all tasks eventually resolve), and fairness (no agent is starved). Properties are expressed in temporal logic, enabling automated formal verification, detection of coordination edge cases, and prevention of deadlocks and security vulnerabilities.

The key contribution is not a new protocol or runtime but a specification language for reasoning about what any multi-agent system should satisfy. This is particularly relevant as MCP and A2A proliferate without shared correctness guarantees, and as high-stakes deployments (healthcare, infrastructure, finance) demand verifiable agentic behavior.

### Key Takeaways
- The fragmented MCP/A2A ecosystem lacks a unified semantic framework—this paper provides the first formal specification language for multi-agent AI systems.
- Thirty temporal-logic properties covering liveness, safety, completeness, and fairness enable automated verification and deadlock/security vulnerability detection.
- The framework is domain-agnostic, making it applicable to any multi-agent deployment from coding assistants to safety-critical infrastructure.

---

## 4. In-Context Autonomous Network Incident Response: An End-to-End Large Language Model Agent Approach

**Authors:** Yiran Gao, Kim Hammar, Tao Li
**Link:** [In-Context Autonomous Network Incident Response: An End-to-End Large Language Model Agent Approach](https://arxiv.org/abs/2602.13156)
**Tags:** cs.CR

### Summary
Traditional autonomous incident response relies on reinforcement learning (RL): train agents in hand-crafted simulations until they learn optimal response strategies. This approach has two fundamental limitations. First, building realistic simulators requires significant domain expertise and ongoing maintenance as attack patterns evolve. Second, simulators discard the rich semantic content embedded in raw system logs and alerts—the very context that human analysts rely on.

This paper proposes replacing RL-based approaches with an LLM agent that leverages pre-trained security knowledge and in-context learning. The agent integrates four capabilities in a single 14-billion parameter model: perception (parsing raw logs to infer network state), reasoning (forming and updating attack hypotheses), planning (simulating consequences of candidate responses), and action (generating and executing the chosen response). The key loop is comparison-driven: the agent compares its simulated predictions against actual observations, iteratively refining both its attack model and its response strategy in-context without any weight updates.

This in-context adaptation is what makes the approach genuinely novel—the agent improves over the course of handling a single incident without retraining or access to a pre-built simulator. When evaluated on incident logs from the literature, the agent achieves recovery up to 23% faster than frontier LLMs used without this structured agentic framework. Importantly, the system runs on commodity hardware, removing a key adoption barrier for security operations centers with limited compute budgets.

### Key Takeaways
- LLM-based agents with in-context adaptation can match or exceed RL-trained incident response systems without requiring any hand-crafted simulator.
- The four-function architecture (perception, reasoning, planning, action) unifies incident response into a single 14B-parameter model runnable on commodity hardware.
- The agent achieves up to 23% faster recovery than unstructured frontier LLM use on published incident logs.

---

## 5. Two Pathways to Truthfulness: On the Intrinsic Encoding of LLM Hallucinations

**Authors:** Wen Luo, Guangyue Peng, Wei Li, Shaohang Wei, Feifan Song, Liang Wang, Nan Yang, Xingxing Zhang, Jing Jin, Furu Wei, Houfeng Wang
**Link:** [Two Pathways to Truthfulness](https://arxiv.org/abs/2601.07422)
**Tags:** cs.CL

### Summary
Hallucination detection in LLMs has largely treated internal truthfulness signals as a monolithic phenomenon—prior work shows that hidden states encode whether a model "knows" something, but why and how those signals arise has remained unclear. This paper reveals that truthfulness encoding in LLMs emerges from two structurally distinct pathways that can be disentangled and characterized.

The first, the Question-Anchored pathway, arises from information flow between the question tokens and the eventual answer: the model is essentially cross-referencing the query against its knowledge base during generation. The second, the Answer-Anchored pathway, is self-contained within the generated answer itself—the model's internal representation of its own output carries independent truthfulness signals. The authors validate these pathways using attention knockout (selectively disabling attention patterns) and token patching (transplanting token representations between forward passes), confirming that these are genuinely distinct mechanisms and not artifacts of a shared representation.

Several important properties emerge from this disentanglement. The two pathways correlate differently with the model's knowledge boundaries: the Question-Anchored pathway tends to fail when the model lacks the relevant knowledge, while the Answer-Anchored pathway fails when generated text diverges from facts the model does encode. Internal representations are also demonstrably "aware" of this distinction. Building on these findings, the authors develop two hallucination detection applications that outperform existing methods by exploiting pathway-specific signals.

The work has direct implications for interpretability-based safety: if models internally encode two different "reasons" for truthfulness failure, targeted interventions may be able to address them separately.

### Key Takeaways
- LLM truthfulness signals arise from two distinct internal pathways—question-anchored and answer-anchored—that can be disentangled via attention knockout and token patching.
- The two pathways correlate with different failure modes, tying to knowledge boundary gaps versus generation divergence.
- Pathway-aware hallucination detection applications outperform existing methods, with implications for targeted interpretability-based interventions.

---

## 6. Alignment as Institutional Design: From Behavioral Correction to Transaction Structure in Intelligent Systems

**Authors:** Rui Chai
**Link:** [Alignment as Institutional Design](https://arxiv.org/abs/2604.13079)
**Tags:** cs.CY

### Summary
This paper makes a provocative structural argument: RLHF-style alignment is analogous to an economy without property rights, where order requires perpetual policing and therefore cannot scale. Drawing on institutional economics—specifically Coase's transaction cost theory, Alchian and Cheung's work on property rights, and the study of competitive cost discovery—the author proposes reframing alignment from a behavioral control problem into an institutional design problem.

The core claim is that behavioral correction paradigms (observe outputs, judge against preferences, adjust parameters) require a supervisor who is always present, always competent, and whose preferences are always coherent. None of these assumptions hold at deployment scale or across long time horizons. Instead, institutional design asks: how do we structure the internal transaction architecture of AI systems such that aligned behavior is the lowest-cost strategy for each component, regardless of whether a supervisor is watching?

The author identifies three irreducible levels of human intervention—structural (module design), parametric (weight training), and monitorial (runtime oversight)—and argues that current alignment research focuses almost entirely on the parametric level while neglecting the other two. The institutional economics framing reframes alignment success not as "the model does what we want" but as "misalignment is costly, detectable, and correctable."

While the paper is largely theoretical and normative, it provides conceptual foundations for a "Wuxing" resource-competition mechanism developed in companion papers. The key limitation is that the translation from economic theory to AI architecture remains underspecified. The paper is best read as a philosophical reframing rather than an engineering blueprint.

### Key Takeaways
- RLHF-style behavioral correction cannot scale because it structurally requires perpetual supervision—analogous to an economy without property rights.
- Institutional design reframes alignment: specify transaction structures such that aligned behavior is each component's lowest-cost strategy.
- The proper goal is institutional robustness—misalignment is costly, detectable, and correctable—not behavioral perfection.

---

## 7. Building Trust in the Skies: A Knowledge-Grounded LLM-based Framework for Aviation Safety

**Authors:** Anirudh Iyengar, Alisa Tiselska, Dumindu Samaraweera, Hong Liu
**Link:** [Building Trust in the Skies](https://arxiv.org/abs/2604.13101)
**Tags:** cs.SE

### Summary
Aviation safety represents one of the highest-stakes environments for LLM deployment: decisions must be traceable, verifiable, and free from hallucination—properties that standalone LLMs cannot guarantee. This paper proposes a dual-phase architecture that combines LLMs with Knowledge Graphs (KGs) to address these requirements in an end-to-end safety analytics system.

Phase one uses LLMs to automate the construction and dynamic updating of an Aviation Safety Knowledge Graph (ASKG) from multimodal sources including incident reports, maintenance records, and regulatory documentation. The KG captures structured relationships between safety events, failure modes, aircraft systems, and regulatory requirements—knowledge that would otherwise be inaccessible to an LLM via raw text retrieval alone.

Phase two embeds this curated KG within a Retrieval-Augmented Generation (RAG) architecture. When a safety query arrives, the system retrieves relevant KG subgraphs alongside document passages, grounding the LLM's response in verified structured knowledge. This dual grounding—both structured (KG) and unstructured (documents)—enables the system to validate its own outputs against authoritative sources and provide explicit reasoning traces for each conclusion.

Experimental results show improved accuracy and traceability over LLM-only baselines, with the system supporting complex multi-hop queries that pure RAG cannot reliably handle. The framework addresses a genuine deployment gap: aviation authorities increasingly require explainable, auditable AI-assisted analysis, but standard LLM deployments provide neither. Limitations include the challenge of maintaining KG completeness as new incidents and regulations emerge, and the need for domain expert validation of KG construction quality.

### Key Takeaways
- A dual-phase LLM + Knowledge Graph architecture improves accuracy and traceability over LLM-only approaches in aviation safety analytics.
- LLMs automate KG construction from multimodal sources, enabling the same models to later query verified structured knowledge via RAG.
- The framework directly addresses aviation regulatory requirements for explainable, auditable AI-assisted safety decisions.

---

## 8. The Cognitive Companion: A Lightweight Parallel Monitoring Architecture for Detecting and Recovering from Reasoning Degradation in LLM Agents

**Authors:** Rafflesia Khan, Nafiul Islam Khan
**Link:** [The Cognitive Companion](https://arxiv.org/abs/2604.13759)
**Tags:** cs.AI

### Summary
LLM agents on hard multi-step tasks exhibit reasoning degradation—looping, drift, and stuck states—at rates up to 30%, a failure mode that existing mitigations handle poorly. Hard step limits cause abrupt termination with no recovery; LLM-as-judge monitoring imposes 10–15% overhead per step and still only detects failures after they occur. This paper introduces the Cognitive Companion, a parallel monitoring architecture designed to both detect and recover from degradation with minimal overhead.

Two implementations are presented. The LLM-based Companion runs a secondary LLM in parallel that monitors the primary agent's behavior and intervenes when degradation patterns are detected—achieving a 52–62% reduction in repetition on loop-prone tasks with approximately 11% overhead. The Probe-based Companion is more radical: a lightweight classifier trained on the primary model's hidden states (layer 28) that detects degradation signals at zero measured inference overhead, achieving cross-validated AUROC of 0.840 on a proxy-labeled dataset.

The Probe-based approach represents a meaningful architectural innovation—using a model's own internal representations to monitor its cognitive state rather than observing its outputs. This parallels the mechanism in the AGILE jailbreak paper (also in today's digest), suggesting that hidden-state monitoring is becoming a central axis for both attacks and defenses.

A key empirical finding is that companion benefit is task-type dependent: companions help most on loop-prone and open-ended tasks but may provide neutral or negative effects on structured tasks. The authors also find that companions show no benefit for very small models (1B–1.5B parameters), suggesting a capability threshold for this approach. The paper is presented as a feasibility study with encouraging but not definitive results.

### Key Takeaways
- Reasoning degradation occurs in up to 30% of hard multi-step LLM agent tasks; the Cognitive Companion detects and recovers from it with minimal overhead.
- The Probe-based variant uses hidden-state classifiers to achieve zero measured inference overhead with AUROC 0.840 for degradation detection.
- Companion benefit is task-type dependent, most effective on loop-prone tasks, and appears to require a model capability threshold above ~1.5B parameters.

---

## 9. Bi-Predictability: A Real-Time Signal for Monitoring LLM Interaction Integrity

**Authors:** Wael Hafez, Amir Nazeri
**Link:** [Bi-Predictability](https://arxiv.org/abs/2604.13061)
**Tags:** cs.CL

### Summary
Current LLM monitoring approaches face a fundamental gap: post-hoc semantic judges are accurate but expensive and latency-incompatible with real-time deployment; perplexity-based measures are cheap but unidirectional and miss a category of failure the authors call "silent uncoupling"—where the LLM produces high-quality outputs in isolation while the conversational context degrades beneath it. This paper introduces bi-predictability (P), an information-theoretic measure that captures whether both sides of a multi-turn interaction remain structurally coupled.

The key insight is that a coherent multi-turn conversation should be bidirectionally predictable: given the context, the response is predictable, but given the response, the preceding context should also be recoverable. When silent uncoupling occurs, forward predictability (context → response) may remain high while backward predictability (response → context) collapses. Measuring both directions simultaneously, using raw token frequency statistics without any secondary model inference, captures this failure mode.

The Information Digital Twin (IDT) is a lightweight architecture that estimates P across the context–response–next-prompt loop in real time. Evaluated across 4,500 conversational turns between student and frontier teacher models, the IDT detected injected disruptions with 100% sensitivity. Critically, the paper demonstrates empirical separability: P aligned with structural consistency in 85% of conditions but with semantic judge scores in only 44%, confirming that structural and semantic quality are distinct and independently monitorable properties.

For safety-critical deployments, bi-predictability offers a scalable first-line integrity monitor that can flag conversations for deeper inspection before expensive semantic evaluation—enabling tiered monitoring architectures.

### Key Takeaways
- Bi-predictability measures bidirectional token-level structural coupling in multi-turn conversations, detecting "silent uncoupling" that semantic judges miss.
- The Information Digital Twin architecture achieves 100% sensitivity on injected disruptions with zero secondary inference overhead.
- Structural coupling and semantic quality are empirically separable (85% vs. 44% alignment), enabling tiered real-time monitoring for safety-critical deployments.

---

## 10. Exploration and Exploitation Errors Are Measurable for Language Model Agents

**Authors:** Jaden Park, Jungtaek Kim, Jongwon Jeong, Robert D. Nowak, Kangwook Lee, Yong Jae Lee
**Link:** [Exploration and Exploitation Errors Are Measurable for Language Model Agents](https://arxiv.org/abs/2604.13151)
**Tags:** cs.AI

### Summary
The exploration-exploitation tradeoff is a foundational concept in decision-making under uncertainty, yet LLM agent evaluations typically measure task success without diagnosing whether failures are due to insufficient exploration (failing to discover necessary information) or insufficient exploitation (failing to act on information already acquired). This distinction matters enormously for debugging and improving agentic systems. This paper proposes the first framework for quantifying exploration and exploitation errors from observed actions, without requiring access to the agent's internal policy or value functions.

The authors design a controlled evaluation environment: a partially observable 2D grid map combined with an unknown task Directed Acyclic Graph (DAG). The map generation can be programmatically tuned to emphasize exploration difficulty (large maps with sparse information) or exploitation difficulty (compact maps where the challenge is synthesizing known information into the correct action sequence). A policy-agnostic metric decomposes observed errors into exploration and exploitation components by comparing the agent's trajectory against information-optimal baselines.

Evaluation across frontier LM agents reveals that even state-of-the-art models struggle, with different models exhibiting qualitatively distinct failure modes—some are over-explorers that gather information without acting; others are over-exploiters that act prematurely on incomplete information. Reasoning-focused models (o-series) perform significantly better overall and show improved balance between both error types. The authors also find that minimal harness engineering—structured prompting that explicitly guides exploration-exploitation decisions—substantially improves both dimensions.

The practical implication for agentic deployment is that task-level success metrics can mask systematic behavioral biases that only become visible when exploration and exploitation are measured separately.

### Key Takeaways
- A new policy-agnostic metric decomposes LLM agent errors into exploration and exploitation components, enabling targeted debugging.
- Even frontier models exhibit distinct failure modes: some over-explore, others over-exploit; reasoning models (o-series) best balance both.
- Minimal harness engineering can significantly improve both exploration and exploitation independently, providing a practical lever for practitioners.

---

## 11. LiveClawBench: Benchmarking LLM Agents on Complex, Real-World Assistant Tasks

**Authors:** Xiang Long, Li Du, Yilong Xu, Fangcheng Liu, Haoqing Wang, Ning Ding, Ziheng Li, Jianyuan Guo, Yehui Tang
**Link:** [LiveClawBench](https://arxiv.org/abs/2604.13072)
**Tags:** cs.CL

### Summary
Most LLM agent benchmarks evaluate agents under isolated difficulty—either a single challenging environment, or ambiguous instructions, but not both simultaneously. Real assistant tasks combine multiple difficulty axes at once: the environment may be complex, the instructions partially specified, and the task may require adapting to unexpected runtime conditions. This disjoint evaluation methodology creates an optimistic gap between benchmark performance and real-world deployment reliability.

LiveClawBench addresses this by introducing a Triple-Axis Complexity Framework that characterizes task difficulty along three independent dimensions: Environment Complexity (the breadth and interconnectedness of tools, APIs, and resources an agent must coordinate), Cognitive Demand (the degree of reasoning, planning, and ambiguity resolution required), and Runtime Adaptability (the frequency and severity of unexpected mid-task conditions that require strategy revision). Tasks are annotated with explicit complexity-factor labels across all three axes, enabling fine-grained analysis of where specific models fail.

The benchmark is seeded from real OpenClaw usage cases—actual tasks submitted by users to an agentic assistant system—ensuring that difficulty levels reflect genuine deployment conditions rather than researcher-constructed scenarios. The pilot benchmark covers compositional tasks where all three axes are simultaneously elevated, the conditions most predictive of failure in production.

The paper frames LiveClawBench as a living benchmark, with ongoing expansion across task domains and complexity axes. This continuous-update design directly addresses the benchmark contamination problem that affects static evaluations as models are trained on prior benchmarks. For practitioners, the framework provides a structured vocabulary for characterizing why a given task is hard for a given agent.

### Key Takeaways
- A Triple-Axis Complexity Framework (Environment, Cognitive Demand, Runtime Adaptability) captures compositional difficulty that single-axis benchmarks miss.
- Tasks are drawn from real OpenClaw usage, ensuring benchmark difficulty reflects actual production deployment conditions.
- Continuous expansion addresses benchmark contamination; explicit complexity annotations enable diagnostic analysis of model failure modes.

---

## 12. RiskWebWorld: A Realistic Interactive Benchmark for GUI Agents in E-commerce Risk Management

**Authors:** Renqi Chen, Zeyin Tao, Jianming Guo, Jing Wang, Zezhou Xu, Jingzhe Zhu, Qingqing Sun, Tianyi Zhang, Shuai Chen
**Link:** [RiskWebWorld](https://arxiv.org/abs/2604.13531)
**Tags:** cs.AI

### Summary
GUI agent benchmarks have been dominated by consumer-facing, cooperative task environments—shopping assistants, form-filling, information retrieval. Risk management in e-commerce represents a fundamentally different challenge: tasks are investigative rather than transactional, websites may actively resist or mislead the agent (partial environmental hijackment), and decisions have real downstream consequences for fraud detection and compliance. No existing benchmark captures these characteristics.

RiskWebWorld introduces 1,513 tasks sourced directly from production risk-control pipelines at an e-commerce platform, spanning 8 core domains including fraud detection, seller verification, policy violation investigation, and account security assessment. The benchmark is built on a Gymnasium-compliant infrastructure that cleanly separates policy planning (what to do) from environment mechanics (how the interface responds), enabling both zero-shot evaluation and agentic reinforcement learning (RL) training.

The capability gap revealed by initial evaluations is dramatic. Top-tier generalist models (frontier LLMs with strong instruction following) achieve 49.1% task success—already showing that these are difficult tasks. Specialized open-weights GUI models that excel on consumer benchmarks score near zero, demonstrating that consumer-task grounding does not transfer to adversarial professional environments. The key finding is that general foundation model scale currently matters more than specialized GUI grounding for long-horizon professional tasks.

The RL infrastructure enables open-source model improvement: agentic RL training improved open-source model success rates by 16.2%, demonstrating that the benchmark can serve as a training environment, not just an evaluation tool. This positions RiskWebWorld as a practical testbed for developing robust digital workers in adversarial real-world settings.

### Key Takeaways
- RiskWebWorld is the first benchmark for GUI agents in adversarial professional settings, with 1,513 tasks from production risk-control pipelines.
- Top frontier models achieve only 49.1% success; specialized GUI models fail near-completely, confirming that consumer-task grounding does not transfer to risk management.
- Foundation model scale dominates GUI specialization for long-horizon professional tasks; RL training on the benchmark improves open-source models by 16.2%.

---
