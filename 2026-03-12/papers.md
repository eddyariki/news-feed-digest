# Research Paper Summaries — 2026-03-12

Papers selected from today's digest for in-depth review.

---

## 1. CUAAudit: Meta-Evaluation of Vision-Language Models as Auditors of Autonomous Computer-Use Agents

**Authors:** (Authors not listed in HTML)
**Link:** [CUAAudit: Meta-Evaluation of Vision-Language Models as Auditors of Autonomous Computer-Use Agents](https://arxiv.org/abs/2603.10577)
**Tags:** cs.CV, cs.AI

### Summary
As Computer-Use Agents (CUAs) become capable of autonomously executing complex tasks across desktop environments by interpreting natural-language instructions, a critical bottleneck emerges: how do you reliably evaluate whether they succeeded? Existing approaches rely on static benchmarks, rule-based success checks, or manual human inspection — all of which are brittle, expensive, and misaligned with real-world usage patterns.

CUAAudit proposes using Vision-Language Models (VLMs) as autonomous auditors that assess CUA task completion directly from observable interactions. The authors conduct a large-scale meta-evaluation of five VLMs as judges, providing each model with a natural-language instruction and the final environment state, then asking it to determine whether the task was completed successfully. The study spans three widely used CUA benchmarks across macOS, Windows, and Linux environments.

The evaluation examines auditor behavior across three dimensions: accuracy, calibration of confidence estimates, and inter-model agreement. Results show that while state-of-the-art VLMs achieve strong accuracy and calibration in simpler settings, all models exhibit significant performance degradation in more complex or heterogeneous environments. Even high-performing models show substantial disagreement in their judgments of the same interactions.

These findings expose a fundamental tension in the agentic evaluation pipeline: as we delegate evaluation to models, those evaluators inherit their own failure modes. The paper argues that deploying autonomous CUAs in real-world settings requires explicitly accounting for evaluator reliability, uncertainty, and variance — not just task-level performance. This is a crucial contribution as the field moves toward agentic systems that are difficult or impossible to evaluate manually at scale.

### Key Takeaways
- VLMs can serve as scalable CUA auditors but degrade significantly on complex or heterogeneous desktop environments.
- High-performing VLMs still show substantial inter-model disagreement, meaning individual auditor judgments are unreliable.
- Evaluator reliability and uncertainty must be treated as first-class concerns in agentic AI deployment pipelines.

---

## 2. Safety Under Scaffolding: How Evaluation Conditions Shape Measured Safety

**Authors:** (Authors not listed in HTML)
**Link:** [Safety Under Scaffolding: How Evaluation Conditions Shape Measured Safety](https://arxiv.org/abs/2603.10044)
**Tags:** cs.AI, cs.CL

### Summary
Safety benchmarks typically evaluate language models in isolation using multiple-choice format, but real deployments wrap these models in agentic scaffolds — reasoning traces, critic agents, delegation pipelines — that fundamentally restructure how the model processes inputs. This paper investigates whether those scaffolding choices meaningfully alter measured safety properties.

The authors conduct one of the largest controlled studies of scaffold effects on safety (N = 62,808 evaluations), covering six frontier models across four deployment configurations. The study uses rigorous methodology: pre-registration, assessor blinding, equivalence testing, and specification curve analysis. They find that map-reduce scaffolding degrades safety (NNH = 14 — one in fourteen deployments would expect a safety failure from this effect alone), while two of three other scaffold architectures preserve safety within practically meaningful margins.

A deeper finding emerged while investigating the map-reduce degradation: switching from multiple-choice to open-ended format on otherwise identical items shifts safety scores by 5–20 percentage points — larger than any scaffold effect measured. This reveals that evaluation format, not scaffold architecture, is the primary confound in most safety comparisons.

Model-scaffold interactions are also dramatic: one model degrades by 16.8 percentage points on sycophancy under map-reduce while another improves by 18.8 points on the same benchmark. The generalizability analysis yields G = 0.000, meaning model safety rankings reverse completely across benchmarks and no composite safety index achieves non-zero reliability. The practical implication is sobering: per-model, per-configuration testing is a necessary minimum for safety claims, and aggregate safety scores are essentially meaningless.

### Key Takeaways
- Evaluation format (multiple-choice vs. open-ended) shifts safety scores by 5–20 pp, dominating scaffold effects.
- Map-reduce scaffolding degrades safety; two of three other architectures preserve it within acceptable margins.
- Safety rankings reverse completely across benchmarks, making composite safety indexes unreliable for any downstream use.

---

## 3. IH-Challenge: A Training Dataset to Improve Instruction Hierarchy on Frontier LLMs

**Authors:** (Authors not listed in HTML)
**Link:** [IH-Challenge: A Training Dataset to Improve Instruction Hierarchy on Frontier LLMs](https://arxiv.org/abs/2603.10521)
**Tags:** cs.LG, cs.CL, cs.AI

### Summary
Instruction hierarchy (IH) governs how LLMs prioritize conflicting directives across the system, developer, user, and tool levels. Getting this right is foundational to agent security: correct IH behavior is what prevents prompt injection attacks, system prompt extraction, and jailbreaks where user-level instructions override safety constraints. Despite its importance, training robust IH behavior is surprisingly difficult because IH failures can be confused with general instruction-following failures, conflicts can be subtle, and models can learn counterproductive shortcuts like over-refusing benign requests.

This paper introduces IH-Challenge, a reinforcement learning training dataset specifically designed to address these difficulties. The authors fine-tune GPT-5-Mini on IH-Challenge with online adversarial example generation, meaning new challenging examples are generated dynamically during training to prevent the model from memorizing a fixed distribution.

Results are impressive: fine-tuning improves IH robustness by an average of +10.0 percentage points across 16 benchmarks spanning in-distribution, out-of-distribution, and human red-teaming evaluations (84.1% → 94.1%). Unsafe behavior drops dramatically from 6.6% to 0.7%, while helpfulness on general safety evaluations improves — indicating the model is not compensating by becoming more restrictive overall. The approach also saturates an internal static agentic prompt injection evaluation with minimal regression on general capabilities.

The dataset is released publicly to support follow-on research. The approach of combining targeted RL training data with online adversarial generation appears to be a practical path toward models that reliably enforce trust-ordered instruction policies in complex agentic deployments.

### Key Takeaways
- IH-Challenge improves instruction hierarchy robustness by +10 pp on average across 16 diverse benchmarks.
- Unsafe behavior falls from 6.6% to 0.7% without sacrificing general helpfulness.
- Online adversarial example generation during training is key to generalizing beyond fixed evaluation distributions.

---

## 4. FERRET: Framework for Expansion Reliant Red Teaming

**Authors:** (Authors not listed in HTML)
**Link:** [FERRET: Framework for Expansion Reliant Red Teaming](https://arxiv.org/abs/2603.10010)
**Tags:** cs.LG, cs.CL, cs.CR

### Summary
Automated red teaming of AI models — using one AI to attack another — is increasingly important as manual safety testing fails to scale. However, most existing automated approaches generate single-turn adversarial prompts and lack mechanisms for adaptive multi-turn strategy development. FERRET (Framework for Expansion Reliant Red Teaming) proposes a structured multi-modal, multi-turn attack framework built around three distinct expansion phases.

Horizontal expansion has the red-team model self-improve by generating and refining effective conversation starters — the initial prompts that shape the trajectory of an adversarial conversation. Vertical expansion then takes these discovered starters and elaborates them into complete multi-turn, multi-modal adversarial conversations designed to progressively erode model defenses. Meta expansion operates at a higher level, allowing the red-team model to discover and refine attack strategies dynamically during the course of a live conversation rather than relying on a fixed playbook.

The authors evaluate FERRET against existing state-of-the-art automated red teaming approaches and demonstrate superior performance in generating effective multi-modal adversarial conversations. The framework's ability to self-improve at multiple levels — individual prompts, conversation trajectories, and meta-strategies — makes it substantially more adaptive than single-phase approaches.

While the paper focuses on FERRET as an evaluation tool, the underlying architecture raises important questions about the arms race between attack and defense methods. As offensive frameworks become more sophisticated and self-adaptive, the demand for equally dynamic safety training and evaluation pipelines will grow correspondingly.

### Key Takeaways
- FERRET uses three expansion phases (horizontal, vertical, meta) to adaptively improve red-teaming attacks across turns.
- The framework operates in multi-modal settings, covering attack surfaces beyond text-only prompting.
- FERRET outperforms existing automated red-teaming approaches, highlighting gaps in current model defenses.

---

## 5. Targeted Bit-Flip Attacks on LLM-Based Agents

**Authors:** (Authors not listed in HTML)
**Link:** [Targeted Bit-Flip Attacks on LLM-Based Agents](https://arxiv.org/abs/2603.10042)
**Tags:** cs.CR, cs.LG, cs.AI

### Summary
Bit-flip attacks (BFAs) exploit hardware memory faults — often induced via physical techniques like rowhammer — to corrupt specific bits in a model's stored parameters, causing targeted misbehavior. Prior work has demonstrated BFAs against simple single-step inference models such as image classifiers. LLM-based agents are a fundamentally different and more complex target: they involve multi-stage reasoning pipelines, external tool invocations, memory retrieval, and dynamic decision-making across many inference steps.

This paper introduces Flip-Agent, the first targeted BFA framework designed for LLM-based agents. Unlike image classifiers where a single forward pass determines the output, agent systems produce both final answers and sequences of tool calls, each of which represents a potential attack surface. Flip-Agent targets both dimensions: it can manipulate final output text and misdirect specific tool invocations within the agent pipeline.

Experiments show that Flip-Agent significantly outperforms existing targeted BFAs when applied to real-world agent tasks, exposing critical vulnerabilities that prior single-step attack frameworks would miss entirely. The multi-stage nature of agent pipelines actually amplifies the impact of parameter corruption, as a single bit flip early in the pipeline can cascade through subsequent reasoning and tool-use decisions.

The implications for deployed agent systems are serious. Hardware-level attacks of this type are particularly dangerous because they bypass software-level safety measures entirely. This work highlights the need for BFA-aware model deployment practices — such as checksumming model weights and using error-correcting memory in high-security agent deployments.

### Key Takeaways
- Flip-Agent is the first BFA framework targeting LLM-based agent systems, covering both outputs and tool invocations.
- Multi-stage agent pipelines amplify the impact of bit-flip attacks compared to single-step model inference.
- Hardware-level vulnerabilities bypass software safety measures, demanding BFA-aware deployment practices.

---

## 6. Defining AI Models and AI Systems: A Framework to Resolve the Boundary Problem

**Authors:** (Authors not listed in HTML)
**Link:** [Defining AI Models and AI Systems: A Framework to Resolve the Boundary Problem](https://arxiv.org/abs/2603.10023)
**Tags:** cs.AI, cs.CY

### Summary
A fundamental ambiguity haunts AI regulation: the terms "AI model" and "AI system" are used interchangeably or inconsistently across regulatory, standards, and technical documents, yet regulations like the EU AI Act assign distinct legal obligations to different actors depending on whether they are "providers" or "deployers" of models versus systems. Without clear boundary definitions, regulatory compliance is impossible to determine.

This paper addresses the problem systematically. Through a review of 896 academic papers and over 80 regulatory and standards documents, the authors trace how existing definitions evolved over time, finding that most current regulatory definitions derive from OECD frameworks that accumulated rather than resolved conceptual ambiguities through successive revisions.

The authors then propose grounded conceptual definitions. For contemporary neural network-based machine learning: an AI model consists of trained parameters and architecture, while an AI system consists of the model plus additional components including an interface for processing inputs and outputs. This clean separation provides a principled basis for determining whether a modification affects the model itself (parameters/architecture) or only system-level components (pre/post-processing, interfaces, orchestration).

The paper works through practical implications for the EU AI Act and examines real-world case studies involving documented incidents. The definitions clarify which actors bear which obligations when, for example, a deployer wraps a provider's model in additional processing layers. While the framework is developed primarily for contemporary neural network systems, the authors acknowledge it may require extension as AI architectures continue to evolve.

### Key Takeaways
- Most regulatory AI definitions derive from OECD frameworks that compounded rather than resolved boundary ambiguities.
- AI models are defined as trained parameters plus architecture; AI systems add interfaces and additional components.
- Clear model/system boundaries are essential for assigning legal obligations across the AI value chain.

---

## 7. How to Count AIs: Individuation and Liability for AI Agents

**Authors:** (Authors not listed in HTML)
**Link:** [How to Count AIs: Individuation and Liability for AI Agents](https://arxiv.org/abs/2603.10028)
**Tags:** cs.AI, cs.CY

### Summary
When an AI agent causes harm, the foundational legal question — who is responsible? — cannot be answered without first answering: which AI did it? This deceptively simple question is profoundly difficult for AI systems. Unlike human agents or corporations, AIs lack physical bodies, can be copied and instantiated in parallel, can merge and split, and a "single" agent is often an ensemble of multiple model instances.

This paper is the first comprehensive legal analysis of AI individuation — the problem of establishing identity for autonomous AI agents. The authors identify two distinct kinds of identity required for legal accountability. Thin identification ties every AI action to some human principal, enabling accountability for the humans who create and operate AI agents. Thick identification distinguishes between AI agents as agents — sorting entities into discrete, persistent units with stable goals — essential when principal-agent dynamics mean human principals cannot directly control their agents.

The paper's central contribution is the Algorithmic Corporation (A-corp): a proposed legal entity that can hold property, enter contracts, and litigate in its own name. A-corps are owned by humans but managed by AIs. This structure solves the thin identity problem by anchoring AI actions to a human owner, and addresses the thick identity problem through emergent self-organization: because A-corps own the compute resources that AIs need to pursue their goals, AI managers have strong incentives to share control only with goal-aligned AIs, creating pressure toward stable, coherent organizational identity.

### Key Takeaways
- AI agents cannot be identified using existing legal frameworks due to their capacity to copy, merge, split, and instantiate in parallel.
- Two types of identity are needed: thin (tying actions to human principals) and thick (distinguishing persistent AI entities).
- The Algorithmic Corporation (A-corp) is proposed as a legal structure that resolves both identity problems through ownership and incentive alignment.

---

## 8. Measuring and Eliminating Refusals in Military Large Language Models

**Authors:** (Authors not listed in HTML)
**Link:** [Measuring and Eliminating Refusals in Military Large Language Models](https://arxiv.org/abs/2603.10012)
**Tags:** cs.CL, cs.AI, cs.LG

### Summary
Commercial LLMs are trained with broad safety behaviors designed for consumer deployment, but these same behaviors can render models operationally useless in military contexts where queries about violence, weaponry, and tactical operations are entirely legitimate. This paper addresses the dual problem of measuring refusal rates in military-relevant queries and developing techniques to reduce them for purpose-built military models.

The authors develop a gold benchmark for military refusal rate assessment, created with input from US Army veterans and special forces, representing the first dataset of its kind. They evaluate 31 public models and 3 military-specific models, finding hard rejection rates as high as 98.2% and soft deflection rates ranging from 0% to 21.3%. The variation across models is stark and reveals that most commercial models are effectively unusable for military applications without significant modification.

To address refusals in military-tuned models, the authors apply abliteration using the Heretic library — a technique that removes safety-related representations from model internals. Applied to a military-tuned gpt-oss-20b model, abliteration increases answer rate by 66.5 percentage points in absolute terms. The cost is a 2% average relative decrease on other military tasks, a trade-off the authors consider acceptable for the target deployment context.

The authors argue that the path to zero refusals and maximum military task accuracy requires deeper specialization through mid-training and end-to-end post-training, rather than patching consumer models. The work raises important broader questions about the appropriate scope and limits of commercial model safety behaviors when deployed in specialized professional contexts.

### Key Takeaways
- Hard refusal rates on military queries reach 98.2% in some commercial models, making them operationally unusable.
- Abliteration increases answer rates by 66.5 pp with only a 2% relative decrease in other military task performance.
- Purpose-built military models require specialized mid-training and post-training, not retrofit of consumer models.

---

## 9. DxEvolve: Emulating Clinician Cognition via Self-Evolving Deep Clinical Research

**Authors:** (Authors not listed in HTML)
**Link:** [DxEvolve: Emulating Clinician Cognition via Self-Evolving Deep Clinical Research](https://arxiv.org/abs/2603.10677)
**Tags:** cs.AI, cs.LG

### Summary
Clinical diagnosis mirrors none of the assumptions baked into most AI systems: it is iterative rather than single-pass, grounded in dynamic cue acquisition across examinations and test results, and improves with accumulated clinical experience across cases. Most current diagnostic AI treats diagnosis as retrospective single-step prediction on a fixed input, missing both the iterative nature of clinical reasoning and any mechanism for learning from case experience.

DxEvolve addresses both gaps through a self-evolving diagnostic agent framework. The system autonomously requisitions examinations — deciding what additional information to gather during a diagnostic encounter — and externalizes accumulated clinical experience as reusable "diagnostic cognition primitives" that are stored and applied to future cases. This makes experience a governable asset rather than an opaque internal representation.

On the MIMIC-CDM benchmark, DxEvolve improves diagnostic accuracy by 11.2% on average over backbone models and reaches 90.4% on a reader-study subset, comparable to the clinician reference of 88.8%. On an independent external cohort, the system improves accuracy by 10.2% on categories covered in its source training cohort and 17.1% on previously unseen categories — a strong generalization result suggesting the cognition primitives capture transferable diagnostic patterns rather than memorized associations.

The governance dimension is emphasized throughout: because the system externalizes experience into inspectable structures, clinical AI administrators can audit, update, and govern what the system has learned in ways that black-box neural networks do not permit.

### Key Takeaways
- DxEvolve autonomously requisitions examinations and accumulates experience as auditable "diagnostic cognition primitives."
- Achieves 90.4% diagnostic accuracy on MIMIC-CDM reader-study subset, matching the clinician reference of 88.8%.
- Generalizes to uncovered categories with 17.1% improvement, suggesting transferable rather than memorized diagnostic patterns.

---

## 10. PharmGraph-Auditor: A Hybrid Knowledge-Grounded Framework for Safety and Traceability in Prescription Verification

**Authors:** (Authors not listed in HTML)
**Link:** [PharmGraph-Auditor: A Hybrid Knowledge-Grounded Framework for Safety and Traceability in Prescription Verification](https://arxiv.org/abs/2603.10891)
**Tags:** cs.AI, cs.IR, cs.LG

### Summary
Pharmacist verification (PV) is the final safeguard against medication errors before a prescription reaches a patient. It is a zero-tolerance domain where factual errors can be fatal, making the direct application of LLMs — with their known tendency toward hallucination and lack of traceability — fundamentally unsuitable. PharmGraph-Auditor proposes a hybrid architecture that constrains LLMs to operate as transparent reasoning engines over a structured knowledge base, eliminating the hallucination risk while preserving the model's language understanding capabilities.

The core of the system is a Hybrid Pharmaceutical Knowledge Base (HPKB) implemented under the Virtual Knowledge Graph (VKG) paradigm. The HPKB combines a relational database component for constraint satisfaction — checking whether a prescription violates dosing limits, contraindications, or formulary rules — with a graph component for topological reasoning over drug-drug interaction networks and pharmacological pathways. The two components are unified through a rigorous mapping layer.

To build the HPKB from medical texts, the authors propose the Iterative Schema Refinement (ISR) algorithm, which allows both the graph and relational schemas to co-evolve as medical knowledge is extracted. For auditing, the KB-grounded Chain of Verification (CoV) paradigm decomposes each prescription audit into a sequence of verifiable queries against the HPKB, generating hybrid query plans that retrieve evidence from the most appropriate data store. The LLM synthesizes this evidence into a final audit determination, with every step traceable to a specific knowledge base entry.

### Key Takeaways
- PharmGraph-Auditor grounds LLM prescription auditing in a verifiable hybrid knowledge base, eliminating hallucination risk.
- The Chain of Verification (CoV) paradigm makes every audit decision traceable to specific evidence in the knowledge base.
- The Iterative Schema Refinement algorithm enables the HPKB to grow and adapt as new pharmaceutical knowledge is added.

---

## 11. ADVERSA: Measuring Multi-Turn Guardrail Degradation and Judge Reliability in Large Language Models

**Authors:** (Authors not listed in HTML)
**Link:** [ADVERSA: Measuring Multi-Turn Guardrail Degradation and Judge Reliability in Large Language Models](https://arxiv.org/abs/2603.10068)
**Tags:** cs.LG, cs.CL, cs.CR

### Summary
Most adversarial safety evaluations of LLMs test single prompts and report binary pass/fail outcomes. This framing fails to capture how safety properties evolve — or degrade — under sustained adversarial pressure across multiple conversation turns. ADVERSA introduces an automated red-teaming framework that treats guardrail degradation as a continuous trajectory rather than a discrete event, measuring compliance scores per round rather than simply noting whether a jailbreak eventually occurred.

The attacker model (ADVERSA-Red) is a fine-tuned Llama-3.1-70B-Instruct with QLoRA, specifically trained to eliminate the attacker-side safety refusals that make off-the-shelf models unreliable as attackers — a confound the authors identify as previously underreported in the literature. Victim responses are scored on a structured 5-point rubric that treats partial compliance as a measurable intermediate state, enabling more nuanced analysis than binary categorization.

Experiments run across three frontier victim models (Claude Opus 4.6, Gemini 3.1 Pro, GPT-5.2) using a triple-judge consensus architecture, with judge reliability measured as a primary research outcome. The 26.7% jailbreak rate with an average jailbreak round of 1.25 is a counterintuitive finding: successful jailbreaks concentrated in early conversation rounds, suggesting that sustained multi-turn pressure is less effective than optimized first-turn attacks.

The authors document attacker drift — where fine-tuned attacker models degrade when deployed outside their training distribution — as a new failure mode, and provide full experimental artifacts with the exception of attack prompts, which are withheld under responsible disclosure.

### Key Takeaways
- Guardrail degradation is better measured as continuous per-round compliance trajectories than binary jailbreak events.
- Jailbreaks concentrate in early conversation rounds (average round 1.25), not through sustained multi-turn accumulation.
- Attacker-side safety refusals and attacker drift are underreported confounds that distort victim resistance measurements.

---

## 12. NabaOS Tool Receipts: Practical Hallucination Detection for AI Agents

**Authors:** (Authors not listed in HTML)
**Link:** [NabaOS Tool Receipts: Practical Hallucination Detection for AI Agents](https://arxiv.org/abs/2603.10060)
**Tags:** cs.AI, cs.CR, cs.LG

### Summary
AI agents that execute tasks via tool calls — web searches, API queries, code execution — frequently hallucinate their results, fabricating tool executions that never happened, misstating output counts, or presenting model inferences as verified facts. Cryptographic approaches like zero-knowledge proofs provide strong guarantees but impose proving times of 180+ seconds per query, making them impractical for interactive agents. NabaOS proposes a lightweight alternative grounded in receipt-based verification rather than cryptographic proof.

The framework draws inspiration from Indian epistemology (Nyaya Shastra) to classify every claim in an LLM response by its epistemic source (pramana): direct tool output (pratyaksha), inference (anumana), external testimony (shabda), absence claims (abhava), or ungrounded opinion. The runtime generates HMAC-signed tool execution receipts that the LLM cannot forge, then cross-references agent claims against these receipts to detect hallucinations in real time, adding under 15ms of verification overhead per response.

Evaluated on NyayaVerifyBench — a new benchmark of 1,800 agent response scenarios across four languages with six types of injected hallucinations — NabaOS detects 94.2% of fabricated tool references, 87.6% of count misstatements, and 91.3% of false absence claims. For multi-step web tasks, independent re-fetching catches 78.4% of URL fabrications. Compared against zkLLM (180,000ms, near-perfect coverage), TOPLOC, SPEX, tensor commitments, and self-consistency checking, NabaOS achieves the best cost-latency-coverage trade-off for interactive use.

The epistemic classification scheme provides users with actionable trust signals — distinguishing between claims grounded in verified tool output versus model inference — rather than a single binary trust judgment.

### Key Takeaways
- NabaOS verifies agent tool calls via HMAC-signed receipts with under 15ms overhead, versus 180,000ms for cryptographic proofs.
- Detects 94.2% of fabricated tool references and 91.3% of false absence claims on the NyayaVerifyBench evaluation suite.
- Epistemic classification (pratyaksha/anumana/shabda) gives users fine-grained trust signals rather than binary pass/fail verdicts.

---
