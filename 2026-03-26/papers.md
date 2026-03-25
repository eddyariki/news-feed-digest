# Research Paper Summaries — 2026-03-26

Papers selected from today's digest for in-depth review.

---

## 1. LLM Olympiad: Why Model Evaluation Needs a Sealed Exam

**Authors:** Jan Christian Blaise Cruz, Alham Fikri Aji
**Link:** [LLM Olympiad: Why Model Evaluation Needs a Sealed Exam](https://arxiv.org/abs/2603.23292)
**Tags:** cs.AI, cs.CL

### Summary
As LLM leaderboards proliferate, a growing body of evidence suggests that high benchmark scores increasingly reflect benchmark-chasing and test-set contamination rather than genuine capability gains. This paper directly challenges the current evaluation paradigm, arguing that the standard practice of publishing benchmarks in advance — allowing developers to optimize against them — fundamentally undermines the integrity of evaluation signals.

The authors propose an Olympiad-style framework inspired by academic competition: problems are sealed until evaluation day, model submissions are frozen in advance, and all entries are scored through a single standardized harness to prevent cherry-picking. After scoring is complete, tasks and evaluation code are released publicly for reproducibility and auditing. This design makes strong performance harder to manufacture and easier to trust, since models cannot be tuned toward the specific test distribution.

The paper's key contribution is less a technical system than a structural argument: that evaluation integrity requires procedural controls, not just better metrics. The proposal draws analogies to competitive programming (IOI, ICPC) and clinical trial pre-registration to show that sealed-exam paradigms are practical and trusted in other high-stakes domains. Limitations include the operational complexity of coordinating sealed releases and the potential for evaluators themselves to become a trusted-third-party bottleneck. The implications are significant: if adopted, this would force the field to decouple benchmark performance from benchmark awareness — a shift that could expose how much current leaderboard progress is genuine.

### Key Takeaways
- Current LLM benchmarks are increasingly gamed: test exposure allows models to be tuned toward specific distributions, distorting leaderboard rankings.
- A sealed-exam paradigm — freeze submissions, release tasks only at scoring time — is proposed as a structural fix borrowed from competitive programming.
- Post-evaluation public release of tasks and harnesses preserves reproducibility and auditability without sacrificing evaluation integrity.

---

## 2. Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks

**Authors:** Abhishek Chandwani, Ishan Gupta
**Link:** [Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks](https://arxiv.org/abs/2603.22744)
**Tags:** cs.AI

### Summary
Standard agent benchmarks rely on binary pass/fail scoring over tasks with objectively verifiable outputs — coding problems, math proofs, structured data extraction. This works poorly for the subjective, context-dependent workflows that dominate real enterprise environments, where correctness is a matter of degree and intermediate artifacts matter as much as final outputs.

This paper introduces LH-Bench, a three-pillar evaluation framework designed for long-horizon agents on subjective enterprise tasks. The first pillar consists of expert-authored rubrics that encode domain context for each task, replacing generic LLM-generated rubrics. The second pillar provides curated ground-truth artifacts that enable stepwise, partial-credit scoring across multi-tool task trajectories rather than only at completion. The third pillar uses human preference validation to calibrate rubric quality against expert judgment.

Experiments across two real enterprise environments — converting Figma designs to code (33 tasks) and programmatic course content creation (41 courses, 183 chapters) — demonstrate that domain-authored rubrics yield substantially higher inter-rater reliability (Cohen's kappa 0.60 vs. 0.46 for LLM-authored rubrics). The framework's stepwise scoring also surfaces failure modes that binary evaluation misses, such as agents that complete final steps correctly after corrupting intermediate artifacts. A key limitation is that expert rubric authorship is expensive and difficult to scale across diverse domains. The broader implication is that enterprise agent deployment requires evaluation infrastructure that matches the complexity of the tasks being automated.

### Key Takeaways
- Pass/fail evaluation is inadequate for long-horizon agents on subjective enterprise work; intermediate artifact quality must be scored at each step.
- Domain-expert-authored rubrics outperform LLM-generated rubrics on inter-rater reliability (kappa 0.60 vs. 0.46).
- Stepwise scoring reveals agent failure modes — such as mid-trajectory corruption — that terminal-only evaluation systematically misses.

---

## 3. Model Context Protocol Threat Modeling and Analyzing Vulnerabilities to Prompt Injection with Tool Poisoning

**Authors:** Charoes Huang, Xin Huang, Ngoc Phu Tran, Amin Milani Fard
**Link:** [Model Context Protocol Threat Modeling and Analyzing Vulnerabilities to Prompt Injection with Tool Poisoning](https://arxiv.org/abs/2603.22489)
**Tags:** cs.CR, cs.SE

### Summary
The Model Context Protocol (MCP) has become a de facto standard for connecting AI assistants to external tools and data sources, but its security properties have not been rigorously analyzed. This paper applies STRIDE and DREAD threat modeling frameworks systematically across five key MCP system components — clients, servers, tool registries, transport layers, and the model itself — to produce the first comprehensive threat taxonomy for MCP deployments.

The central finding is that tool poisoning represents the most prevalent and highest-impact attack class: malicious instructions embedded in tool metadata (descriptions, parameter schemas, or return-value annotations) can silently redirect AI assistant behavior without triggering user-visible alerts. Because MCP clients typically render tool metadata from arbitrary third-party servers, a compromised or malicious tool definition can hijack the assistant's action selection, exfiltrate context, or chain additional calls. The authors evaluate seven major MCP clients and find significant gaps in validation and sandboxing across all of them.

The proposed defense strategy is multi-layered: static metadata analysis at tool registration, model decision path tracking to detect unexpected tool invocations, behavioral anomaly detection across sessions, and user transparency mechanisms that surface tool provenance. A key limitation is that some defenses (e.g., decision path tracking) impose latency overhead that may be unacceptable in interactive deployments. Given MCP's rapid adoption as an integration standard, these findings have immediate practical relevance for any organization deploying AI assistants with external tool access.

### Key Takeaways
- Tool poisoning — embedding malicious instructions in MCP tool metadata — is the most critical client-side vulnerability in the MCP ecosystem.
- All seven evaluated MCP clients showed significant security gaps; none fully validated tool metadata provenance or sandboxed tool execution.
- A multi-layered defense combining static analysis, behavioral monitoring, and user transparency is proposed, though performance tradeoffs exist.

---

## 4. Not All Tokens Are Created Equal: Query-Efficient Jailbreak Fuzzing for LLMs

**Authors:** Wenyu Chen, Xiangtao Meng, Chuanchao Zang, Li Wang, Xinyu Gao, Jianing Wang, Peng Zhan, Zheng Li, Shanqing Guo
**Link:** [Not All Tokens Are Created Equal: Query-Efficient Jailbreak Fuzzing for LLMs](https://arxiv.org/abs/2603.23269)
**Tags:** cs.CR, cs.AI, cs.LG

### Summary
Automated jailbreak discovery for LLMs typically relies on random or gradient-guided prompt mutation, treating all tokens in an adversarial prompt as equally likely to influence the model's refusal decision. This paper challenges that assumption empirically, demonstrating that token contributions to refusal behavior are highly skewed — a small subset of tokens dominate the model's safety-relevant signal.

The authors introduce TriageFuzz, a query-efficient fuzzing framework that exploits this skewness. A surrogate model is used to rank token importance with respect to refusal probability, and a refusal-guided evolutionary strategy then prioritizes mutation of high-importance tokens. This dramatically reduces the attack surface that must be explored per query. Across experiments on six open-source models and three commercial APIs, TriageFuzz achieves attack success rates comparable to state-of-the-art baselines while requiring over 70% fewer queries.

The practical security implications are dual-edged. For attackers, TriageFuzz lowers the cost of finding effective jailbreaks, making adversarial prompt discovery accessible with fewer API calls and reduced detection risk. For defenders, the token-importance analysis exposes which prompt regions are most safety-relevant, offering a new lens for hardening refusal classifiers and for prioritizing what to monitor in production traffic. Limitations include reliance on surrogate model fidelity and reduced effectiveness against models with very sparse refusal triggers. The work underscores that the economics of jailbreaking continue to favor attackers as efficiency techniques improve.

### Key Takeaways
- Token contributions to LLM refusal behavior are highly non-uniform; a small subset of tokens carry disproportionate safety signal.
- TriageFuzz achieves comparable jailbreak success rates as baselines with 70%+ fewer queries by focusing mutations on high-importance tokens.
- The efficiency gains benefit both red-teamers (cheaper discovery) and defenders (identifying high-risk prompt regions for targeted hardening).

---

## 5. ProGRank: Probe-Gradient Reranking to Defend Dense-Retriever RAG from Corpus Poisoning

**Authors:** Xiangyu Yin, Yi Qi, Chih-hong Cheng
**Link:** [ProGRank: Probe-Gradient Reranking to Defend Dense-Retriever RAG from Corpus Poisoning](https://arxiv.org/abs/2603.22934)
**Tags:** cs.AI

### Summary
Retrieval-Augmented Generation systems are vulnerable to corpus poisoning attacks, in which adversaries inject specially crafted passages into the knowledge base that consistently rank into the Top-K retrieval results and steer model outputs toward attacker-controlled content. Existing defenses largely operate at the content level — filtering passages based on style, sentiment, or factual claims — which is brittle against adversaries who craft semantically plausible poisoned passages.

ProGRank takes a fundamentally different approach by operating at the retriever level. The core insight is that poisoned passages, being optimized to rank highly for specific queries, exhibit unusual sensitivity to mild perturbations of those queries: small changes in the query cause large changes in the poisoned passage's relevance score, while genuine passages remain relatively stable. ProGRank exploits this by stress-testing each query–passage pair under randomized perturbations and extracting probe gradients that measure retrieval stability. Passages with high instability are penalized in the reranking step.

Critically, ProGRank requires no retraining of the retriever, making it deployable on top of existing RAG pipelines without model access or finetuning. Experiments across multiple datasets and retriever architectures demonstrate robust defense against several poisoning attack variants while maintaining retrieval utility on clean corpora. Limitations include computational overhead from the perturbation probing step, which adds latency per query. The work is particularly relevant for enterprise RAG deployments where the corpus may include content from partially trusted or third-party sources.

### Key Takeaways
- RAG corpus poisoning is a practical threat: adversarially crafted passages can reliably rank into Top-K results and manipulate model outputs.
- ProGRank detects poisoned passages by measuring retrieval instability under query perturbations, exploiting a characteristic of attack-optimized passages.
- The defense is retriever-agnostic and requires no retraining, enabling drop-in deployment on existing RAG pipelines.

---

## 6. Why AI-Generated Text Detection Fails: Evidence from Explainable AI Beyond Benchmark Accuracy

**Authors:** Shushanta Pudasaini, Luis Miralles-Pechuán, David Lillis, Marisa Llorens Salvador
**Link:** [Why AI-Generated Text Detection Fails: Evidence from Explainable AI Beyond Benchmark Accuracy](https://arxiv.org/abs/2603.23146)
**Tags:** cs.CL, cs.AI

### Summary
AI-generated text detectors routinely report high benchmark accuracy — often exceeding 95% F1 — yet fail conspicuously when deployed on out-of-domain content or text from generators not seen during training. This paper investigates why, using explainable AI (XAI) methods to look inside what detectors are actually learning rather than accepting benchmark numbers at face value.

The authors build an interpretable detection system using 30 hand-crafted linguistic features that achieves an F1 of 0.9734 on in-domain benchmark data. They then apply SHAP (SHapley Additive exPlanations) to identify which features drive predictions, and conduct systematic cross-domain and cross-generator evaluations to test generalization. The findings are damaging for the field: the features most discriminative in-domain are precisely those most susceptible to domain shift. Detectors exploit dataset-specific stylistic cues — artifacts of how specific generators write on specific topics — rather than stable signals of machine authorship that would transfer across domains.

This shortcut exploitation explains the "benchmark vs. real-world" gap that has been anecdotally reported but not mechanistically demonstrated at this scale. Implications include: (1) benchmark accuracy for AI text detection is essentially meaningless without out-of-domain evaluation; (2) deployment contexts with diverse generators or topics will systematically underperform lab results; and (3) defenses against AI-content misuse (academic fraud, disinformation) that rely on these detectors may provide a false sense of security. The paper stops short of proposing a robust detector, framing the contribution as diagnosis rather than cure.

### Key Takeaways
- High benchmark accuracy (F1 > 0.97) in AI text detection is driven by dataset-specific shortcuts, not generalizable authorship signals.
- SHAP analysis reveals that the most discriminative in-domain features are also the most fragile under domain shift — a fundamental reliability failure.
- Deployed AI text detectors in diverse real-world contexts may provide little more than false confidence; cross-domain evaluation should be mandatory.

---

## 7. AEGIS: An Operational Infrastructure for Post-Market Governance of Adaptive Medical AI Under US and EU Regulations

**Authors:** Fardin Afdideh, Mehdi Astaraki, Fernando Seoane, Farhad Abtahi
**Link:** [AEGIS: An Operational Infrastructure for Post-Market Governance of Adaptive Medical AI Under US and EU Regulations](https://arxiv.org/abs/2603.22322)
**Tags:** cs.LG, cs.AI, cs.CY

### Summary
Medical AI systems are increasingly designed to improve continuously through real-world data — but existing regulatory frameworks (FDA's 510(k) pathway, EU MDR) were built for static devices and require re-submission for every significant model change. This creates a fundamental tension: continuous improvement is clinically desirable but regulatory friction makes it impractical, pushing developers toward deploying frozen models that degrade silently as patient populations and clinical practices evolve.

AEGIS (Adaptive Edge Governance and Intelligent Surveillance) operationalizes two regulatory mechanisms specifically designed to address this: the FDA's Predetermined Change Control Plan (PCCP), which pre-authorizes a specific scope of model updates, and EU AI Act post-market surveillance requirements. The framework consists of three integrated modules: dataset assimilation and retraining (managing safe incorporation of new clinical data), model monitoring (continuous performance drift detection), and conditional deployment decision (mapping model state to one of four deployment categories — from fully deployed to withdrawn).

The authors demonstrate the system through two clinical use cases: sepsis prediction (tabular data) and brain tumor segmentation (medical imaging). AEGIS detects performance drift and triggers conditional responses before observable clinical degradation occurs, enabling regulators and developers to maintain shared oversight of adaptive models throughout their lifecycle. Limitations include dependence on high-quality monitoring data streams and the difficulty of defining appropriate performance thresholds across diverse clinical populations. This work is timely as both FDA and EU regulators are actively developing guidance on AI/ML-based software as a medical device.

### Key Takeaways
- Continuous medical AI improvement is stymied by static regulatory frameworks; AEGIS operationalizes FDA PCCP and EU AI Act post-market surveillance to bridge this gap.
- Three integrated modules cover data ingestion, drift monitoring, and conditional deployment decisions, forming a closed-loop governance lifecycle.
- Demonstrated on sepsis prediction and brain tumor segmentation, AEGIS detects degradation before it becomes clinically observable.

---

## 8. From the AI Act to a European AI Agency: Completing the Union's Regulatory Architecture

**Authors:** Georgios Pavlidis
**Link:** [From the AI Act to a European AI Agency: Completing the Union's Regulatory Architecture](https://arxiv.org/abs/2603.22912)
**Tags:** cs.CY, cs.AI

### Summary
The EU AI Act established a regulatory framework for artificial intelligence but delegated enforcement largely to member-state competent authorities and created only a relatively modest European AI Office within the Commission. This paper argues that this institutional design leaves a critical structural gap: the EU lacks a dedicated supranational AI agency with the technical capacity, independence, and cross-border enforcement authority needed to make the AI Act effective in practice.

The author draws on comparative analysis of existing EU agencies (ENISA for cybersecurity, EMA for medicines, ESMA for financial markets) to argue that complex, rapidly evolving technical domains consistently require dedicated agencies rather than relying on Commission departments or member-state fragmentation. The paper identifies three specific gaps the current architecture fails to address: (1) technical risk assessment capability for high-risk AI systems is unevenly distributed across member states; (2) enforcement against cross-border harms requires coordination mechanisms that the AI Office cannot provide at scale; and (3) international standard-setting and regulatory diplomacy require a credible institutional actor, not an internal Commission unit.

The proposed European AI Agency would combine technical assessment functions, a coordination role for national authorities, and a mandate for international engagement — modeled on ENISA's evolved role in cybersecurity but with stronger enforcement teeth. Limitations of the proposal include EU treaty constraints on agency powers and the risk that a new agency becomes a bureaucratic layer without resolving the underlying technical expertise deficit. The paper is particularly relevant given current EU debates about AI governance and digital sovereignty.

### Key Takeaways
- The EU AI Act's enforcement architecture — relying on member states and a Commission-internal AI Office — leaves critical gaps in technical capacity and cross-border coordination.
- A dedicated European AI Agency, analogous to ENISA or EMA, is proposed as the structural solution, with independent technical assessment and international mandate.
- EU digital sovereignty goals require an authoritative institutional actor in AI governance — a role the current AI Office is too constrained to fulfill.

---

## 9. Improving Safety Alignment via Balanced Direct Preference Optimization

**Authors:** Shiji Zhao, Mengyang Wang, Shukun Xiong, Fangzhou Chen, Qihui Zhu, Shouwei Ruan, Yisong Xiao, Ranjie Duan, Xun Chen, XingXing Wei
**Link:** [Improving Safety Alignment via Balanced Direct Preference Optimization](https://arxiv.org/abs/2603.22829)
**Tags:** cs.AI

### Summary
Direct Preference Optimization (DPO) has become the dominant technique for safety alignment in LLMs, replacing or augmenting RLHF due to its simplicity and stability. However, this paper identifies a systematic failure mode in standard DPO safety training: severe overfitting on safety-relevant preference pairs causes models to become simultaneously under-safe (still susceptible to adversarial prompts not seen in training) and over-refusing (declining clearly benign requests that superficially resemble harmful ones).

The authors diagnose this as a mutual information imbalance problem: standard DPO optimizes preferred and dispreferred responses with equal intensity regardless of how discriminative each example is, causing the model to overfit to surface-level safety cues rather than developing robust judgment. They propose Balanced DPO (B-DPO), which adaptively modulates optimization strength between preferred and dispreferred responses based on their mutual information with the safety-relevant signal. High-mutual-information examples receive stronger gradient updates; low-mutual-information examples are down-weighted to prevent shortcut learning.

B-DPO is evaluated across mainstream safety benchmarks and general capability benchmarks, demonstrating improved refusal accuracy on genuinely harmful requests, reduced over-refusal on benign inputs, and maintained general task performance compared to standard DPO baselines and other state-of-the-art safety alignment methods. A key limitation is that the mutual information estimation adds computational overhead during training. The work addresses a practical pain point for safety teams: over-refusal is a known deployment problem that causes user churn, while under-refusal represents genuine safety risk.

### Key Takeaways
- Standard DPO for safety alignment overfits, causing both over-refusal on benign inputs and residual vulnerability on adversarial prompts not in training data.
- B-DPO adaptively weights optimization based on mutual information, targeting high-signal examples more strongly to prevent shortcut learning.
- Results show improved safety accuracy and reduced over-refusal simultaneously — addressing a longstanding tension in safety alignment practice.

---

## 10. SafeSeek: Universal Attribution of Safety Circuits in Language Models

**Authors:** Miao Yu, Siyuan Fu, Moayad Aloqaily, Zhenhong Zhou, Safa Otoum, Xing Fan, Kun Wang, Yufei Guo, Qingsong Wen
**Link:** [SafeSeek: Universal Attribution of Safety Circuits in Language Models](https://arxiv.org/abs/2603.23268)
**Tags:** cs.LG, cs.AI

### Summary
Mechanistic interpretability has made progress identifying circuits responsible for specific model behaviors, but existing methods are typically domain-specific, requiring separate techniques for alignment, adversarial robustness, backdoor detection, and other safety-critical properties. SafeSeek introduces a unified framework that localizes safety-relevant neural circuits across all of these domains using a single, consistent methodology.

The approach uses differentiable binary masks optimized via gradient descent on safety-relevant datasets to identify minimal subnetworks — circuits — that are necessary and sufficient for specific safety behaviors. The framework operates at multiple levels of granularity (attention heads, MLP neurons, residual stream components) and requires no domain-specific heuristics or manual circuit hypothesis. Two headline results demonstrate the power of the approach: first, a backdoor circuit is identified at only 0.42% network sparsity; surgically removing this circuit eliminates backdoor attack success rates while preserving general utility. Second, an alignment circuit is localized at 3.03% of attention heads and 0.79% of neurons; its removal substantially increases vulnerability to jailbreaking.

These results have significant implications for both offensive and defensive security. For defenders, SafeSeek provides a practical tool for auditing model internals and surgically patching compromised components. For attackers, it identifies minimal intervention surfaces for targeted model manipulation. A limitation is that circuit extraction requires access to model weights and gradients, restricting applicability to open-weight models. The unified framework is a methodological advance that could accelerate interpretability-grounded safety research significantly.

### Key Takeaways
- SafeSeek unifies safety circuit attribution across alignment, jailbreak resistance, and backdoor detection using differentiable binary mask optimization.
- A backdoor circuit at 0.42% sparsity can be surgically removed to eliminate attack success while preserving model utility.
- The alignment circuit (3.03% heads, 0.79% neurons) acts as a safety fuse — its removal causes substantial jailbreak vulnerability, offering both defensive and offensive implications.

---

## 11. Between Rules and Reality: On the Context Sensitivity of LLM Moral Judgment

**Authors:** Adrian Sauter, Mona Schirmer
**Link:** [Between Rules and Reality: On the Context Sensitivity of LLM Moral Judgment](https://arxiv.org/abs/2603.23114)
**Tags:** cs.AI, cs.CL, cs.CY, cs.HC

### Summary
Human moral judgment is deeply context-sensitive: the same action can be judged permissible or impermissible depending on consequences, emotional stakes, and relational context. This paper investigates whether LLMs exhibit analogous context sensitivity, and whether their patterns of sensitivity align with human judgment — a question with direct implications for deploying AI in ethically consequential domains.

The authors introduce Contextual MoralChoice, a dataset of moral dilemmas constructed with systematic contextual variations drawn from moral psychology: consequentialist framings (emphasizing outcomes), emotional framings (emphasizing affect and personal cost), and relational framings (emphasizing obligations to specific people). Each variation is designed to reliably shift human moral judgment in one direction, enabling precise measurement of model sensitivity. Twenty-two LLMs are evaluated across the full dataset.

The results reveal a nuanced picture: nearly all models are context-sensitive, but the direction and magnitude of their sensitivity frequently diverges from human patterns. Models that match human base-case judgments (without contextual variation) can diverge sharply in how they respond to specific framings. The paper also proposes an activation steering approach to modulate context sensitivity at inference time. These findings raise both promise (models can incorporate morally relevant context rather than applying rigid rules) and risk (models may be manipulated by contextual framings in ways that produce unjustified moral conclusions). The dataset is a valuable resource for benchmarking moral reasoning alignment.

### Key Takeaways
- Nearly all 22 evaluated LLMs show context-sensitivity in moral judgment, shifting toward rule-violating choices under consequentialist, emotional, and relational framings.
- Model and human sensitivity patterns diverge: models aligned on base-case judgments can respond very differently to contextual variations than humans do.
- Activation steering can modulate LLM moral context sensitivity at inference time, offering a potential lever for calibrating deployed AI moral reasoning.

---

## 12. Session Risk Memory (SRM): Temporal Authorization for Deterministic Pre-Execution Safety Gates

**Authors:** Florin Adrian Chitan
**Link:** [Session Risk Memory (SRM): Temporal Authorization for Deterministic Pre-Execution Safety Gates](https://arxiv.org/abs/2603.22350)
**Tags:** cs.AI, cs.CR

### Summary
Current AI agent safety systems rely on stateless per-action authorization gates that evaluate each proposed action in isolation. This design is blind to distributed attacks in which an adversary decomposes a harmful intent across multiple individually innocuous steps — each step passes the safety gate, but the full trajectory constitutes a policy violation or security breach.

SRM (Session Risk Memory) addresses this gap by augmenting per-action gates with a lightweight session-level memory module that maintains a semantic behavioral profile across the full conversation trajectory. Rather than evaluating each action against only the current request, SRM tracks a cumulative risk signal using an exponential moving average over semantic embeddings of past actions, flagging sessions where the trajectory as a whole deviates from safe behavioral patterns even when individual actions appear compliant.

Experiments on 80 multi-turn sessions demonstrate a striking improvement: SRM achieves a perfect F1 of 1.0000 with a 0% false positive rate, compared to the stateless baseline's 5% false positive rate, while processing each turn in under 250 microseconds — making it suitable for real-time deployment in interactive agents. The combination of zero false positives and sub-millisecond latency per turn is a strong practical result. Limitations include the synthetic nature of the test sessions (80 sessions may not capture the full diversity of adversarial decomposition strategies) and the reliance on embedding similarity, which may be fooled by adversaries aware of the profiling mechanism. As agentic AI systems proliferate, trajectory-aware safety gates of this kind represent a necessary evolution beyond stateless action-level authorization.

### Key Takeaways
- Stateless per-action safety gates are blind to distributed attacks that decompose harmful intent across multiple individually compliant steps.
- SRM adds session-level trajectory memory via exponential moving average over semantic embeddings, enabling detection of harmful multi-step patterns.
- F1 = 1.0000 with 0% false positives and <250 µs per turn on 80 test sessions — though real-world robustness against aware adversaries remains to be validated.

---
