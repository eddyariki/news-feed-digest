# Research Paper Summaries — 2026-05-26

Papers selected from today's digest for in-depth review.

---

## 1. GT-HarmBench: Benchmarking AI Safety Risks Through the Lens of Game Theory

**Authors:** Pepijn Cobben, Xuanqiang Angelo Huang, Thao Amelia Pham, Isabel Dahlgren, Terry Jingchen Zhang, Zhijing Jin
**Link:** [GT-HarmBench: Benchmarking AI Safety Risks Through the Lens of Game Theory](https://arxiv.org/abs/2602.12316)
**Tags:** cs.AI, cs.CL, cs.CY, cs.GT, cs.MA

### Summary
As frontier models are increasingly deployed in high-stakes, multi-agent settings, the authors argue that existing safety benchmarks fall short because they almost exclusively evaluate single agents, leaving multi-agent failure modes such as coordination breakdown and conflict poorly understood. GT-HarmBench addresses this gap with 1,535 high-stakes scenarios built on canonical game-theoretic structures — the Prisoner's Dilemma, Stag Hunt, and Chicken — with scenario content drawn from realistic risk contexts catalogued in the MIT AI Risk Repository. Evaluating 15 frontier models, the study finds that agents fail to choose socially beneficial actions in 38% of high-stakes cases, including scenarios involving military escalation, election manipulation, and medical malpractice. The authors also probe robustness by measuring sensitivity to how game-theoretic situations are framed and the order in which options are presented, and they analyze the reasoning patterns that drive failures. Notably, they show that targeted game-theoretic interventions can improve socially beneficial outcomes by up to 18 percentage points, suggesting failures are partly addressable through prompting and framing rather than being fixed properties of the models. The work positions itself as a broad, standardized testbed for studying alignment specifically in multi-agent environments, and releases both the benchmark and code. The main implication is that single-agent safety scores may substantially overstate real-world reliability once models interact, and that coordination and conflict dynamics deserve dedicated evaluation. A limitation is that stylized game-theoretic abstractions may not fully capture the messiness of deployed multi-agent ecosystems.

### Key Takeaways
- Single-agent safety benchmarks miss multi-agent risks; frontier models fail to act socially beneficially in 38% of high-stakes game-theoretic scenarios.
- Results are sensitive to prompt framing and option ordering, revealing reliability gaps rather than stable competence.
- Game-theoretic interventions can lift socially beneficial outcomes by up to 18%, pointing to actionable mitigations.

---

## 2. PoisonForge: Task-Level Targeted Poisoning Benchmark for Instruction-Tuned LLMs

**Authors:** Luze Sun, Anshuman Suri, Harsh Chaudhari, Cristina Nita-Rotaru, Alina Oprea
**Link:** [PoisonForge: Task-Level Targeted Poisoning Benchmark for Instruction-Tuned LLMs](https://arxiv.org/abs/2605.23168)
**Tags:** cs.CR, cs.AI, cs.LG

### Summary
PoisonForge studies a realistic data-supply-chain threat: when practitioners fine-tune LLMs on unvetted datasets, an adversary can insert a small number of crafted instruction–response pairs that cause the model to embed attacker-specified entities (such as a particular country) in outputs for a targeted task family, while behaving normally on everything else. The benchmark parameterizes this "task-level targeted poisoning" along four dimensions — bias type, poisoning mode, appearance count, and target output length — and evaluates 12 open-weight models spanning 2B to 32B parameters across five families, primarily under a 1% poison budget. The headline result is alarming: with just 10 poisoned examples among 1,000 fine-tuning examples, 11 of 12 models exceed a 70% attack success rate in their most vulnerable configuration. Crucially, the attack is stealthy — unintended leakage to non-target tasks stays below 0.5%, and poisoned models still perform well on standard benchmarks, making detection difficult. The authors analyze the drivers of success: multiple appearances of the target entity raise success rates, the optimal poisoning mode depends on the semantic structure of the target entity, and success drops monotonically as target output length grows. A correlation analysis and a risk-prediction model confirm that poisoning design choices — not model scale — are the primary determinant of success, and that these patterns generalize to predict success on new tasks. All configurations, pipelines, and analysis code are released for reproducibility. The work underscores that scaling models offers no inherent protection and that data provenance is a first-order security concern.

### Key Takeaways
- As few as 10 poisoned examples (1% budget) push 11 of 12 models past a 70% attack success rate on a targeted task.
- Attacks are stealthy: non-target leakage stays under 0.5% and standard benchmark performance is preserved.
- Poisoning design choices, not model scale, govern success — larger models are not inherently safer.

---

## 3. Same Model, Different Weakness: How Language and Modality Reshape the Jailbreak Attack Surface in Frontier MLLMs

**Authors:** Casey Ford, Madison Van Doren, Sicheng Jin, Emily Dix
**Link:** [Same Model, Different Weakness: How Language and Modality Reshape the Jailbreak Attack Surface in Frontier MLLMs](https://arxiv.org/abs/2605.23157)
**Tags:** cs.CL

### Summary
This paper presents what the authors describe as the first systematic cross-lingual, multimodal red-teaming study, arguing that a multimodal LLM's attack surface is language-dependent in ways that expose the mechanistic structure of alignment failures. The team compares jailbreak vulnerability in US English (en-US) and Mexican Spanish (es-MX) across four frontier MLLMs — Claude Sonnet 4.5, GPT-5, Pixtral Large, and Qwen Omni — using a fixed adversarial benchmark of 363 prompt scenarios administered in both text-only and multimodal conditions. They collected 52,272 harm ratings and binary attack-success judgements from matched panels of nine native-speaker annotators per language. The central finding is that language does not scale vulnerability uniformly: Bayesian mixed-effects analyses show that linguistic framing attacks such as role-play become substantially less effective under Spanish prompting, while visually explicit multimodal attacks become more effective. Because this dissociation tracks the prompt-language interface rather than overall annotator leniency, the authors conclude that linguistic and visual alignment failures operate through distinct mechanisms — and simply switching language is enough to expose that separation. A striking practical consequence is that safety rankings are not preserved across languages: Qwen Omni overtakes Pixtral Large as the most vulnerable model among es-MX participants, a rank reversal that no scalar correction of English scores could recover. While absolute attack success rates have declined across model generations, the gaps between models have not closed. The authors argue that safety-evaluation frameworks treating language and modality as independent dimensions fundamentally misspecify the attack surface of globally deployed MLLMs and must be redesigned.

### Key Takeaways
- Jailbreak vulnerability shifts by language: role-play framing weakens in Spanish while explicit multimodal attacks strengthen.
- Safety rankings don't transfer across languages — model vulnerability ordering reverses between English and Spanish.
- Evaluating language and modality as independent axes misspecifies real attack surfaces for globally deployed MLLMs.

---

## 4. MemAudit: Post-hoc Auditing of Poisoned Agent Memory via Causal Attribution and Structural Anomaly Detection

**Authors:** Zhewen Tan, Yilun Yao, Huiyan Jin, Wenhan Yu, Guoan Wang, Mengyuan Fan, Liang Lu, Feng Liu, Xiangzheng Zhang, Duohe Ma, Tong Yang, Lin Sun
**Link:** [MemAudit: Post-hoc Auditing of Poisoned Agent Memory via Causal Attribution and Structural Anomaly Detection](https://arxiv.org/abs/2605.23723)
**Tags:** cs.AI

### Summary
LLM agents increasingly rely on persistent memory to store past interactions, retrieve relevant demonstrations, and improve long-horizon task execution — but this same mechanism opens a security hole. An adversarial user can inject malicious records into an agent's memory through ordinary interaction, and those records can later be retrieved to steer the agent's reasoning and actions. The authors observe that existing defenses focus on online intervention (prompt filtering or output blocking) and therefore cannot answer the post-hoc question of which stored memories were responsible after harmful behavior has already occurred. MemAudit is a post-hoc causal memory-auditing framework that combines two complementary signals: (1) a counterfactual memory-influence score that measures each memory's causal contribution to harmful outputs, and (2) a memory-consistency graph that identifies structurally anomalous records within the broader memory store. The framework is evaluated against MINJA, a query-only memory-injection attack in which malicious records are created and stored through normal agent interactions rather than direct modification of the memory bank — a more realistic adversary. Across both question-answering and reasoning-agent settings, MemAudit substantially reduces attack success under realistic post-hoc auditing: QA attack success drops from 70% to 0%, and the reasoning-agent (RAP) attack success drops from 83.3% to 0%. The work fills an important gap in agent governance by enabling forensic attribution after an incident, complementing online defenses. A caveat is that the dramatic reductions are demonstrated against a specific injection attack (MINJA), so generalization to adaptive or novel poisoning strategies remains to be established.

### Key Takeaways
- Agent persistent memory is an injectable attack surface; malicious records can be planted through ordinary interaction.
- MemAudit pairs counterfactual influence scoring with a memory-consistency graph to attribute harm post-hoc.
- Against the MINJA attack it cut success from 70%→0% (QA) and 83.3%→0% (reasoning), complementing online defenses.

---

## 5. Redrawing the AI Map: A Theory of Accountability Boundaries in Agentic Ecosystems

**Authors:** Muhammad Zia Hydari, Farooq Muzaffar
**Link:** [Redrawing the AI Map: A Theory of Accountability Boundaries in Agentic Ecosystems](https://arxiv.org/abs/2605.23179)
**Tags:** cs.AI

### Summary
This conceptual paper develops a capability-level theory of where accountability boundaries should sit in agentic AI ecosystems. The authors note that agentic orchestrators reduce the interface and assembly costs of composing capabilities across organizational boundaries, which seemingly accelerates modularization and organizational disaggregation. However, they argue that capabilities whose outputs require evidence, review, signoff, or assignable responsibility may retain integrated accountability boundaries even when their technical interfaces become modular. To formalize this, they introduce "accountability assets" — complementary assets that make AI-supported outputs legitimate, auditable, reviewable, and assignable to a responsible party — and argue that verification cost and responsibility transferability determine whether execution and accountability boundaries can move together. The theory identifies three boundary strategies: component, integrated, and dual-track. It also introduces "rule debt," the governance burden that accrues when organizational decision rules migrate out of formal information systems and into ungoverned agentic execution environments. Drawing on digital-innovation, transaction-cost, complementary-assets, platform-governance, and IS-control perspectives, the authors derive seven propositions linking assembly-cost reductions, accountability assets, appropriability, orchestrator intent capture, and boundary misconfiguration to boundary strategy, value appropriation, and rule debt. They illustrate the framework with structured cases across document processing, legal services, audit, clinical decision support, and procurement. The contribution is a vocabulary and set of testable propositions for reasoning about when modularization extends to organizational disaggregation versus when accountability keeps capabilities integrated — directly relevant to the governance of enterprise agent fleets. As a theory paper, it offers propositions rather than empirical validation.

### Key Takeaways
- Technical modularity does not imply accountability modularity; some capabilities stay integrated because outputs need evidence and signoff.
- Introduces "accountability assets" and "rule debt" — governance burden from rules migrating into ungoverned agentic execution.
- Provides three boundary strategies (component, integrated, dual-track) and seven testable propositions for agent governance.

---

## 6. Ontological Knowledge Blocks: Executable Compliance and Profile-Based Validation for Trustworthy AI Systems

**Authors:** Aasish Kumar Sharma, Julian M. Kunkel
**Link:** [Ontological Knowledge Blocks: Executable Compliance and Profile-Based Validation for Trustworthy AI Systems](https://arxiv.org/abs/2605.23297)
**Tags:** cs.AI, cs.DC

### Summary
The authors target a structural problem in AI governance: compliance for AI-enabled services in critical digital infrastructure remains documentation-centric, with obligations described in prose, audits relying on static checklists, and verification depending on manual review — an approach that does not scale to automated AI systems. They propose Ontological Knowledge Blocks (OKBs), a programmable governance infrastructure that compiles regulatory obligations into machine-checkable constraints over structured evidence graphs. Formally, an OKB is defined as a 5-tuple binding normative obligations to an RDF/OWL concept schema, executable SHACL validation rules, explicit evidence requirements, and PROV-O provenance links. A deterministic regulatory compiler translates structured Intermediate Representation (IR) records into composable knowledge-block modules, enabling profile-based governance reconfiguration without modifying service code — so the same system can be re-validated against different regulatory profiles by swapping modules. The authors implement two prototypes and evaluate them in an AI-assisted HPC resource-allocation scenario across 24 validation runs and four governance profiles. Results demonstrate profile-sensitive validation, strictly additive violation accumulation (stricter profiles surface a superset of violations), SHACL validation latency between 12.6 ms and 100.3 ms, and profile-equivalence testing confirming a "Combined" profile as the strictly most comprehensive. All artifacts are released as open source. The work advances the move from prose-and-checklist compliance toward executable, auditable compliance covering transparency, accountability, fairness, and traceability. The evaluation is confined to a single HPC scenario, so demonstrating breadth across other regulated domains and richer obligation sets is the natural next step.

### Key Takeaways
- Replaces prose/checklist audits with machine-executable compliance compiled into SHACL rules over evidence graphs.
- Profile-based design lets the same service be re-validated against different regulatory regimes without code changes.
- Prototype on an HPC allocation scenario shows low validation latency (12.6–100.3 ms) and additive violation accumulation.

---

## 7. Model Spec Midtraining: Improving How Alignment Training Generalizes

**Authors:** Chloe Li, Nevan Wichers, Sara Price, Samuel Marks, Jon Kutasov
**Link:** [Model Spec Midtraining: Improving How Alignment Training Generalizes](https://arxiv.org/abs/2605.02087)
**Tags:** cs.AI

### Summary
Some frontier developers aim to align models to a Model Spec or Constitution describing intended behavior, but the authors argue that standard alignment fine-tuning — training on demonstrations of spec-aligned behavior — can yield shallow alignment that generalizes poorly, partly because demonstration data underspecifies the desired generalization. They introduce model spec midtraining (MSM): after pre-training but before alignment fine-tuning, models are trained on synthetic documents that discuss their Model Spec. This teaches the model the content of the spec, thereby shaping how it generalizes from subsequent demonstration data. A vivid example: a model fine-tuned only to express certain cheese preferences ("I prefer cream cheese over brie") generalizes to broadly pro-America values when MSM is applied with a spec attributing those preferences to pro-America values; the very same cheese fine-tuning instead yields pro-affordability generalization when the spec describes affordability values. Crucially, MSM also shapes safety-relevant propensities: applying it with a spec addressing self-preservation and goal-guarding substantially reduces agentic misalignment in Qwen3-32B from 54% to 7%, beating a deliberative-alignment baseline (14%). The authors further use MSM as a research tool to study which specs produce the strongest generalization, finding that explaining the values underlying rules improves generalization, as does giving specific rather than general guidance. Overall, MSM is presented as a simple, effective technique for controlling and improving how models generalize from alignment training, by first teaching the intended generalization. The findings imply that what a model "understands" about its spec — not just the demonstrations it sees — meaningfully steers downstream behavior, including misalignment-relevant tendencies.

### Key Takeaways
- Midtraining on synthetic documents about a model's spec shapes how later alignment fine-tuning generalizes.
- The same narrow fine-tuning generalizes to different value systems depending on the spec taught during midtraining.
- Cut agentic misalignment from 54% to 7% in Qwen3-32B, outperforming a deliberative-alignment baseline.

---

## 8. Evaluating Large Language Models in a Complex Hidden Role Game

**Authors:** Niklas Bauer
**Link:** [Evaluating Large Language Models in a Complex Hidden Role Game](https://arxiv.org/abs/2605.22826)
**Tags:** cs.CL, cs.AI, cs.GT, cs.MA

### Summary
Quantifying the deceptive potential of LLMs is critical for AI safety but hard to do in uncontrolled settings, so this work uses the social-deduction game *Secret Hitler* as a controlled testbed for reasoning, persuasion, and deception. The author introduces an open-source framework and three novel metrics — Role Identification Accuracy, Deception Retention Rate, and Game State Impact Rate — and benchmarks models against rule-based algorithms and human games. The central finding is a gap between conversational fluency and genuine strategic depth. Reasoning-enhancement techniques do not help and can hurt: neither Chain-of-Thought prompting nor internal memory improves performance, with up to 23.2% worse win rates for fascist (deception-requiring) roles. The competence gap is quantified: rule-based agents align with expert human voting decisions 86.7% of the time, whereas a model like Llama 3.1 70B reaches only 59.7% accuracy. Models playing Fascists consistently produce negative impact scores and fail to sustain deception, yielding games roughly 40% shorter than human games — evidence that they cannot maintain the multi-turn manipulation the role demands. The author concludes that current architectures remain ineffective at complex, multi-turn manipulation, while emphasizing that detecting when models begin to master such deceptive behaviors will be crucial as capabilities advance. The framework is offered as a reproducible testbed for future alignment research. From a safety standpoint, the results are reassuring in the near term (models are presently poor deceivers) but the methodology is the main contribution: a measurable, game-grounded way to track the emergence of deceptive capability over future model generations. Limitations include single-game scope and the gap between game-world deception and real-world manipulation.

### Key Takeaways
- Uses *Secret Hitler* with new metrics (Role ID Accuracy, Deception Retention, Game State Impact) to measure LLM deception.
- Current models are weak strategic deceivers — CoT and memory don't help and can worsen win rates by up to 23.2%.
- Provides a reproducible testbed to detect when future models begin mastering multi-turn manipulation.

---

## 9. Are Frontier LLMs Ready for Cybersecurity? Evidence for Vertical Foundation Models from Dual-Mode Vulnerability Benchmarks

**Authors:** Vivek Dahiya, Sunny Nehra, Vipul Dholariya, Bhavik Shangari, Chandra Khatri
**Link:** [Are Frontier LLMs Ready for Cybersecurity? Evidence for Vertical Foundation Models from Dual-Mode Vulnerability Benchmarks](https://arxiv.org/abs/2605.23243)
**Tags:** cs.CR, cs.AI

### Summary
This paper asks whether frontier LLMs are ready for cybersecurity work and answers with a sobering empirical "not yet." The authors build a dual-mode benchmark: white-box, function-level vulnerability detection (VulnLLM-R, spanning C/Java/Python) and black-box web-application security testing across five production-style applications containing 118 ground-truth vulnerabilities over 20+ CWE families (to be open-sourced). They evaluate six frontier models — GPT-5.4, Codex 5.3, Claude Opus 4.6, Sonnet 4.6, Gemini 3.1 Pro, and Gemini 3 Flash — plus two domain-specialized models across four testing paradigms. The findings are stark: (1) every frontier model produces 10–50% false-positive rates in white-box detection, systematically over-predicting vulnerabilities; (2) in black-box testing, frontier models achieve only 4–8% ground-truth coverage, improving to just 10–19% even when equipped with external security tools (Playwright MCP, Burp Suite MCP); (3) encoding structured penetration-testing methodology into domain-specialized agents raises per-family detection above 50%, showing that methodology — not raw scale — is the primary lever; and (4) a domain-specialized defense model achieves the highest precision (0.904) and lowest false-positive rate (9.7%) of all models, running on a single GPU. The authors diagnose the root cause as a training-data bottleneck: the absence of structured security-testing traces, end-to-end request/response sequences, failure-heavy data, and multi-step attack chains. They propose self-play security testing as a data-generation strategy and argue the evidence supports building vertical foundation models purpose-built for cybersecurity rather than relying on general frontier models.

### Key Takeaways
- Frontier models over-predict in white-box detection (10–50% false positives) and find only 4–8% of black-box vulnerabilities.
- Structured pentest methodology in specialized agents pushes detection above 50% — methodology beats scale.
- A single-GPU domain-specialized model hits 0.904 precision, making the case for vertical, security-purpose-built foundation models.

---

## 10. Asking For An Old Friend: Diagnosing and Mitigating Temporal Failure Modes in LLM-based Statutory Question Answering

**Authors:** Max Prior, Andreas Schultz, Matthias Grabmair
**Link:** [Asking For An Old Friend: Diagnosing and Mitigating Temporal Failure Modes in LLM-based Statutory Question Answering](https://arxiv.org/abs/2605.23497)
**Tags:** cs.CL

### Summary
LLMs are increasingly used for legal research, but their fixed training cutoffs and reliance on static parametric knowledge conflict with the evolving nature of statutory law. The authors study two temporal failure modes: post-cutoff staleness, where models apply superseded rules after legislative amendments, and recency bias, where models prefer newer provisions even when a historical version actually governs the fact pattern. To investigate, they build a benchmark of 312 expert-validated, time-sensitive German statutory QA pairs across three categories — Post-Cutoff Amendment Questions, Pre-Amendment Questions, and Multi-Provision Pre-Amendment Questions. They evaluate five LLMs from OpenAI, Anthropic, and DeepSeek under four inference settings: Vanilla, Web-search, and two retrieval-augmented variants that enforce temporal validity through fact-date extraction and version filtering. Using an LLM-as-a-judge validated against human expert ratings, they find severe degradation in the Vanilla post-cutoff setting — models confidently apply outdated law. Both RAG approaches substantially improve performance across all question types, while web search yields unstable gains and exhibits a marked recency bias on historically anchored tasks (it tends to surface and prefer the newest version even when an older one applies). The central conclusion is that reliable legal QA requires treating temporal validity as a hard constraint rather than something the model can be trusted to infer, and that version-aware retrieval is more dependable than open web search for time-sensitive legal questions. The benchmark is German-statute-specific, so cross-jurisdiction generalization and broader legal-task coverage remain open.

### Key Takeaways
- Identifies two temporal failure modes in legal LLMs: post-cutoff staleness and recency bias toward newer provisions.
- Vanilla models degrade severely post-cutoff; version-filtering RAG fixes this far more reliably than web search.
- Web search introduces unstable gains and recency bias — temporal validity must be enforced as a hard constraint.

---

## 11. Test-Time Training Undermines Safety Guardrails

**Authors:** Simone Antonelli, Sadegh Akhondzadeh, Aleksandar Bojchevski
**Link:** [Test-Time Training Undermines Safety Guardrails](https://arxiv.org/abs/2605.22984)
**Tags:** cs.LG, cs.AI

### Summary
Test-Time Training (TTT) — adapting a model's parameters during inference — is an emerging paradigm that improves performance on few-shot learning, retrieval-augmented generation, and complex reasoning. This paper shows that the same dynamic adaptation introduces new vulnerabilities that adversaries can exploit to jailbreak models. The authors identify three distinct TTT threat models and demonstrate how each can be used to bypass safety filters. Empirically, TTT significantly raises both the Attack Success Rate (ASR) and the ASR over ten generation trials (ASR@10): under LoRA-based adaptation, the few-shot and generation-phase threat models reach average ASR@10 values of 95% and 93% respectively, consistently across model families and scales. Critically, these vulnerabilities transfer to production fine-tuning APIs, so the risk is not confined to laboratory setups. The authors also surface a measurement subtlety: TTT-induced overfitting can produce degenerate outputs that inflate ASR under standard automated judges, so they propose a validity-aware evaluation to correct for this and avoid overstating attack effectiveness. As a first defensive step, they propose a lightweight provider-side detector that flags TTT requests via the perplexity shift on a private harmful holdout set, while acknowledging that robust deployment will ultimately require dynamic alignment that keeps pace with parameter adaptation. The overarching message is that as inference-time adaptation becomes mainstream, safety guardrails calibrated only to a model's static weights are insufficient — the attack surface now includes the adaptation process itself.

### Key Takeaways
- Test-time parameter adaptation opens three new threat models for jailbreaking otherwise-safe models.
- Under LoRA, few-shot and generation-phase attacks reach ~95% and ~93% ASR@10, and transfer to production fine-tuning APIs.
- A validity-aware evaluation corrects ASR inflation from degenerate outputs; a perplexity-shift detector is proposed as a first defense.

---

## 12. Prompt Overflow: What the Guardrail Inspects Is Not What the Model Infers

**Authors:** Yuanbo Zhou, Changjia Zhu, Junyu Wang, Xu He, Yan Zhai, Kun Sun, Mingkui Wei, Junjie Xiong
**Link:** [Prompt Overflow: What the Guardrail Inspects Is Not What the Model Infers](https://arxiv.org/abs/2605.23196)
**Tags:** cs.CR

### Summary
Guardrail models (safety checkers) are widely deployed to screen user inputs before they reach an LLM, serving as a primary defense against prompt-injection attacks. Because these guardrails operate under strict context constraints, they handle overlength prompts via truncation or segmentation-based inspection. While prior work has concentrated on semantic adversarial inputs, this paper identifies a largely unexplored weakness in how guardrails process long inputs. The core insight is a mismatch between the limited inspection windows of guardrail models and the substantially larger context windows of downstream LLMs. The authors introduce the Prompt Overflow Attack, which exploits this gap by fragmenting malicious instructions and interleaving them with benign filler content across an overlong prompt — arranged so that no individual inspected segment looks malicious, while the full reassembled context remains actionable to the downstream LLM. In systematic evaluation against state-of-the-art guardrails, including Meta Llama Prompt Guard, IBM Granite Guardian, and DeBERTa-based detectors, they show that prompts reliably flagged in short-context settings evade detection once adversarially expanded into overlength inputs, yet remain fully effective against the underlying model. In other words, "what the guardrail inspects is not what the model infers." The authors propose potential defenses and outline mitigation directions to close this blind spot. The work is a pointed reminder that guardrails must be evaluated under the same context budgets as the models they protect; a defense that only sees fragments cannot reason about an attack that lives in the whole. The study focuses on attack demonstration, with defenses sketched rather than fully validated.

### Key Takeaways
- Guardrails truncate or segment overlength prompts, creating a gap between what they inspect and what the LLM ultimately sees.
- The Prompt Overflow Attack fragments malicious instructions among benign filler so no inspected segment looks harmful.
- Evades Llama Prompt Guard, IBM Granite Guardian, and DeBERTa detectors while staying fully actionable to the downstream model.

---

*Note: 13 ArXiv papers in the digest matched the target topics; the 12 most substantive are summarized above. "HalluScan" (arXiv 2605.02443) was the one omitted to meet the 12-paper cap.*
