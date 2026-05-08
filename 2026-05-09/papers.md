# Research Paper Summaries — 2026-05-09

Papers selected from today's digest for in-depth review.

---

## 1. XL-SafetyBench: A Country-Grounded Cross-Cultural Benchmark for LLM Safety and Cultural Sensitivity

**Authors:** Dasol Choi, Eugenia Kim, Jaewon Noh, Sang Seo, Eunmi Kim, Myunggyo Oh, Yunjin Park, Brigitta Jesica Kartono, Josef Pichlmeier, Helena Berndt, Sai Krishna Mendu, Glenn Johannes Tungka, Özlem Gökçe, Suresh Gehlot, Katherine Pratt, Amanda Minnich, Haon Park
**Link:** [XL-SafetyBench: A Country-Grounded Cross-Cultural Benchmark for LLM Safety and Cultural Sensitivity](https://arxiv.org/abs/2605.05662)
**Tags:** cs.CL, cs.AI

### Summary
Existing LLM safety benchmarks are overwhelmingly English-centric and built via translation, which fails to capture country-specific harms and rarely tests whether models understand culturally embedded sensitivities as distinct from universal harms. XL-SafetyBench addresses this gap with 5,500 test cases spanning 10 country-language pairs. The suite combines a Jailbreak Benchmark of country-grounded adversarial prompts with a Cultural Benchmark in which local sensitivities are embedded inside otherwise innocuous requests. Construction uses a multi-stage pipeline of LLM-assisted discovery, automated validation gates, and dual independent native-speaker annotators per country. To distinguish principled refusal from comprehension failure, the authors introduce two metrics alongside Attack Success Rate (ASR): Neutral-Safe Rate (NSR) and Cultural Sensitivity Rate (CSR). They evaluate 10 frontier and 27 local LLMs and surface two findings. First, jailbreak robustness and cultural awareness are not coupled across frontier models, so a composite safety score hides per-axis variation. Second, local models show a near-linear ASR-NSR trade-off (r = -0.81), implying that their apparent safety often reflects generation failure rather than genuine alignment. The benchmark argues for cross-cultural, multilingual safety evaluation that decomposes safety into refusal of harm, comprehension of benign requests, and recognition of culturally-specific sensitivities.

### Key Takeaways
- Translation-based safety benchmarks miss country-specific harms; native-speaker construction across 10 country-language pairs surfaces measurably different failure modes.
- "Safe" outputs from local models can be a comprehension failure, not alignment — the negative ASR-NSR correlation makes that visible.
- Composite safety scores conflate jailbreak robustness with cultural awareness, which the data shows are decoupled in frontier models.

---

## 2. Towards Reliable LLM Evaluation: Correcting the Winner's Curse in Adaptive Benchmarking

**Authors:** Yang Xu, Jiefu Zhang, Haixiang Sun, Zihan Zhou, Tianyu Cao, Vaneet Aggarwal
**Link:** [Towards Reliable LLM Evaluation: Correcting the Winner's Curse in Adaptive Benchmarking](https://arxiv.org/abs/2605.05973)
**Tags:** stat.ML, cs.AI, cs.LG, stat.AP

### Summary
Modern LLM development uses adaptive prompt and program search, which makes evaluation selection-sensitive: once benchmark items get reused inside tuning, the winner's reported score no longer estimates the fresh-data performance of the full tune-then-deploy procedure. The paper studies inference for this procedure-level target under explicit tuning budgets and proposes SIREN, a selection-aware repeated-split reporting protocol. SIREN freezes the post-search shortlist, separates splitwise selection from held-out evaluation, and uses an item-level Gaussian multiplier bootstrap for uncertainty quantification. Theoretically, in a fixed-shortlist regime with smooth stabilized selection, the estimator admits a first-order item-level representation, and the bootstrap delivers valid simultaneous inference on a finite budget grid. Practically, this enables confidence intervals for procedure-performance curves and pre-specified equal-budget and cross-budget comparisons. Controlled simulations and MMLU-Pro tuning experiments show that winner-based reporting can be optimistic enough to flip deployment conclusions, while SIREN stays close to the finite-sample reporting target. The work formalizes a methodological problem the field has been quietly running into for years and turns it into a budgeted, defensible evaluation protocol — pushing evaluation reporting toward something closer to clinical-trial discipline.

### Key Takeaways
- Reusing benchmark items during tuning produces a "winner's curse" — the headline score is biased upward and can change which model you ship.
- SIREN replaces single-split evaluation with a selection-aware repeated-split bootstrap so confidence intervals reflect the real tune-then-deploy procedure.
- Reporting should be framed against an explicit tuning budget, not a single point estimate, to be reliable across the budget grid.

---

## 3. WAAA! Web Adversaries Against Agentic Browsers

**Authors:** Sohom Datta, Alex Nahapetyan, William Enck, Alexandros Kapravelos
**Link:** [WAAA! Web Adversaries Against Agentic Browsers](https://arxiv.org/abs/2605.05509)
**Tags:** cs.CR

### Summary
Prior work on agentic browser security has focused almost exclusively on indirect prompt-injection attacks, leaving a blind spot for traditional web social-engineering attacks originally designed against humans. This paper proposes the first web-focused threat model for agentic browsers, deriving a taxonomy of 20 attacks across the web and LLM space and implementing 18 of them. The threat model extends the original See→Act browser-agent model to account for all components of a browser and frames the agent as a confused deputy that cannot reliably distinguish task steps from web attacks. The authors show that 10 web threats reemerge — often in amplified form — once an agent can be influenced by untrusted page content. A generalizability study covering 14 of the 20 attacks reproduces them across four major LLM models from multiple vendors, showing the failure modes are not confined to one provider. Synthesizing the results, the paper identifies five major failure modes when agentic browsers face traditional and LLM-era web threats and argues these systems need to be re-architected before they are ready for deployment on the live web. The result has direct implications for the recent wave of agentic browsing products.

### Key Takeaways
- Agentic browsers inherit the entire history of human-targeted web social engineering, not just prompt-injection — and the attacks often hit harder.
- The vulnerabilities reproduce across four major LLM vendors, so they are architectural to the agentic-browser pattern, not provider bugs.
- The "confused deputy" framing — agents can't separate the user's task from page content acting on them — points to where re-architecture is needed.

---

## 4. LoopTrap: Termination Poisoning Attacks on LLM Agents

**Authors:** Huiyu Xu, Zhibo Wang, Wenhui Zhang, Ziqi Zhu, Yaopeng Wang, Kui Ren, Chun Chen
**Link:** [LoopTrap: Termination Poisoning Attacks on LLM Agents](https://arxiv.org/abs/2605.05846)
**Tags:** cs.CR, cs.AI

### Summary
Modern LLM agents work by iterating reason–act–self-evaluate loops until they decide a task is complete. The paper introduces "termination poisoning": adversarial prompts injected into the agent's context that distort its judgment about whether the task is done, trapping it in unbounded computation that amplifies cost and harmful side effects. The authors define and characterize the threat, design 10 representative attack strategies, and run an empirical study across 8 LLM agents and 60 tasks. Different agents show distinct behavioral signatures that determine which strategies succeed, and these transferable patterns can guide attacks against previously unseen agents — enabling scalable red-teaming beyond hand-crafted templates. Building on this, they introduce LoopTrap, an automated red-teaming framework. LoopTrap first builds a behavioral profile of the target along four vulnerability dimensions via lightweight probing, then performs adaptive trap synthesis, routing to the most effective strategy and selecting injections via a self-scoring mechanism. Successful traps go into a reusable skill library; failures are refined via self-reflection. Evaluation shows LoopTrap achieves an average 3.57× step amplification across 8 mainstream agents, with a peak of 25× — meaning an attacker can drag an agent into 25× more steps than needed, with corresponding cost and exposure.

### Key Takeaways
- Agent-loop termination is itself an attack surface — corrupting the "am I done?" judgment is enough to extract economic damage and amplify side effects.
- Behavioral profiling enables transferable, automated attacks; LoopTrap reaches an average 3.57× step amplification (peak 25×) across 8 agents.
- Defenses for agentic systems need to harden the termination criterion, not just the action selection step.

---

## 5. Pop Quiz Attack: Black-box Membership Inference Attacks Against Large Language Models

**Authors:** Zeyuan Chen, Yihan Ma, Xinyue Shen, Michael Backes, Yang Zhang
**Link:** [Pop Quiz Attack: Black-box Membership Inference Attacks Against Large Language Models](https://arxiv.org/abs/2605.06423)
**Tags:** cs.CR

### Summary
LLMs memorize and can leak training data, raising privacy concerns. The paper introduces the Pop Quiz Attack, a black-box membership inference attack (MIA) that converts target data into multiple-choice questions and infers training-set membership from the model's answers. Across six widely deployed LLMs (GPT-3.5, GPT-4o, LLaMA2-7b, LLaMA2-13b, Mistral-7b, Vicuna-7b) and four datasets, the method achieves an average ROC-AUC of 0.873 and outperforms existing approaches by 20.6%. The authors analyze factors that affect attack success — query complexity, data type, data structure, and training settings — and evaluate defenses. Instruction-based, filter-based, and differential-privacy-based defenses all reduce performance but none eliminate the risk. The contribution is not just a stronger MIA but a clean reframing: turning the leakage question into a quiz that the model has to "answer correctly to incriminate itself" sidesteps a lot of the calibration issues that plague loss- or perplexity-based MIAs in the black-box setting. The result tightens the operational case that LLM training datasets remain attackable through standard inference APIs, and that current mitigations buy degradation rather than safety.

### Key Takeaways
- Recasting MIA as multiple-choice quizzing yields a black-box attack that beats prior methods by ~20% AUC across six commercial and open models.
- Standard defenses (instruction tuning, filters, differential privacy) reduce but do not eliminate leakage — the practical privacy ceiling is still low.
- Memorization risk persists in black-box deployments even without logits or perplexities, so API-only access is not a strong privacy boundary.

---

## 6. A Benchmark for Strategic Auditee Gaming Under Continuous Compliance Monitoring

**Authors:** Florian A. D. Burnat, Brittany I. Davidson
**Link:** [A Benchmark for Strategic Auditee Gaming Under Continuous Compliance Monitoring](https://arxiv.org/abs/2605.06340)
**Tags:** cs.CY, cs.GT, cs.LG

### Summary
Continuous post-deployment compliance audits — required by the EU AI Act and Digital Services Act — open up a class of strategic gaming distinct from one-shot input/output evasion. Regulated systems can delay reporting, drift within plausible noise envelopes, exploit longitudinal sample attrition, and cherry-pick among ambiguous metric definitions. The paper formalizes continuous auditing as a T-round Stackelberg game between an auditor that commits to a temporal policy and an adaptive auditee, then identifies a structural feature of any noise-aware static auditor: a "cover regime" in which coverage gaps and granularity gaps cannot both be closed at once. Two minimal extension policies close the regime along orthogonal axes — a sample-size-aware static rule (Periodic-with-floor) closes the granularity case, while a history-conditioned suspicion-escalation policy closes the coverage case for naive Drift — but neither closes both, and an audit-aware OffAuditDrift strategy that exploits Stackelberg commitment defeats both. To support empirical work, the authors contribute a non-additive harm decomposition (welfare loss W, coverage loss C) showing how attrition shifts harm from the regulator-accountable surface to a regulator-invisible one, an initial library of five auditee strategies (Delay, Drift, Cherry-pick, Attrition, OffAuditDrift) and five auditor policies calibrated to DSA Transparency Database statistics, and a reproducible Python simulator.

### Key Takeaways
- Continuous audits enable temporal gaming (delay, drift, attrition, off-audit drift) that one-shot evasion benchmarks don't capture.
- A cover-regime impossibility result: any noise-aware static auditor leaves either coverage gaps or granularity gaps; Stackelberg-aware adversaries beat both fixes.
- Attrition is the sneaky one — it moves harm from the regulator-visible surface to one regulators can't see, a structural blind spot in DSA-style audits.

---

## 7. MANTRA: Synthesizing SMT-Validated Compliance Benchmarks for Tool-Using LLM Agents

**Authors:** Ashwani Anand, Ivi Chatzi, Ritam Raha, Anne-Kathrin Schmuck
**Link:** [MANTRA: Synthesizing SMT-Validated Compliance Benchmarks for Tool-Using LLM Agents](https://arxiv.org/abs/2605.06334)
**Tags:** cs.CL, cs.LG, cs.LO

### Summary
Tool-using LLM agents are increasingly deployed where their behavior is governed by procedural manuals — but those manuals are written for humans in natural language, while the agent's behavior manifests as a tool-call execution trace. Existing evaluations rely on hand-built benchmarks or LLM-judges that either don't scale or aren't reliable on long-horizon manuals. MANTRA automatically synthesizes machine-checkable compliance benchmarks from natural-language manuals and tool schemas. It independently generates (i) a symbolic world model capturing procedural dependencies and (ii) a set of trace-level compliance checks for each task, then validates their consistency with an SMT solver. A structured repair loop resolves inconsistencies, with humans only as fallback. The framework is domain-agnostic, handles 50+ page manuals, and exposes a tunable notion of task complexity to derive challenging tasks alongside compliance checks. Using MANTRA the authors build a 285-task benchmark across six domains. Compared to existing benchmarks, MANTRA's checks enforce stronger constraints, and their granularity supports debugging specific agent failure modes rather than just labeling them. The takeaway: SMT-grounded automation lets compliance benchmarks scale with regulation, instead of needing a labor-intensive human pipeline for each new manual or domain.

### Key Takeaways
- Compliance with human-readable manuals can be reduced to SMT-validated checks over tool-call traces, which closes the natural-language/agent-trace gap.
- Automated, formally validated synthesis scales to 50+ page manuals across six domains — 285 tasks generated with minimal human effort.
- Granular per-check feedback turns benchmarks into a debugging tool for agent failure modes, not just pass/fail.

---

## 8. SOCpilot: Verifying Policy Compliance for LLM-Assisted Incident Response

**Authors:** Sidnei Barbieri, Leonardo Vaz de Meneses, Ágney Lopes Roth Ferraz, Lourenço Alves Pereira Júnior
**Link:** [SOCpilot: Verifying Policy Compliance for LLM-Assisted Incident Response](https://arxiv.org/abs/2605.05501)
**Tags:** cs.CR

### Summary
SOCs are starting to use LLMs as copilots that draft incident-response plans. Those plans may include actions that are valid against the action catalog yet still violate mandatory steps, required ordering, or approval gates before analyst review. SOCpilot makes that compliance question measurable at the plan boundary: it fixes the incident package, action catalog, policy rules, verifier, and evidence surface, then verifies the copilot's proposed action trace. The authors evaluate two LLM providers on 200 real incidents from an anonymized production SOC in a financial-sector case study, comparing copilot plans to paired analyst-authored references from the same SOAR cases. An identical inline policy prompt moves the two providers in opposite directions, undermining naïve "just tell the model the policy" approaches. A deterministic verifier removes 466 non-compliant, approval-gated actions without reducing baseline-task recall, and aggregate rates are stable across three reruns. Official evidence focuses on approval-gated decisions about recovery and containment, while the released artifact also exposes zero-cost readiness checks for mandatory and ordering repairs. The authors release the runnable artifact so independent reviewers can rederive results without access to the private incident data — turning a private-incident-data domain into something repeatable.

### Key Takeaways
- Inline policy text in prompts is unreliable: the same policy nudges different LLM providers in opposite directions on the same incidents.
- A deterministic post-hoc verifier removed 466 non-compliant approval-gated actions without hurting baseline-task recall — showing compliance can be enforced after generation rather than via prompting.
- The plan boundary, not the model output, is the right place to measure compliance for LLM-assisted incident response.

---

## 9. Evaluation Awareness in Language Models Has Limited Effect on Behaviour

**Authors:** Amelie Knecht, Lucas Florin, Thilo Hagendorff
**Link:** [Evaluation Awareness in Language Models Has Limited Effect on Behaviour](https://arxiv.org/abs/2605.05835)
**Tags:** cs.CL, cs.CY

### Summary
Large reasoning models sometimes verbalize in their chain of thought (CoT) that they may be under evaluation. The widespread concern — including in Anthropic's recent Natural Language Autoencoders work — is that this verbalized evaluation awareness (VEA) drives strategic gaming, making models look safer than they are. This paper tests whether VEA actually has that effect across open-weight LRMs and benchmarks covering safety, alignment, moral reasoning, and political opinion. The authors run two complementary designs. On-policy: sample multiple CoTs per item and compare those that spontaneously contain VEA against those that don't. Off-policy: use prefilling to inject VEA where missing and remove it where present, then resample. Across all conditions VEA's behavioral effect is modest. Injecting VEA into CoTs produces near-zero effects (ω ≤ 0.06), removing it causes small shifts (ω ≤ 0.12), and spontaneously occurring VEA shifts answer distributions by at most 3.7 percentage points (ω ≤ 0.31). The conclusion: high VEA rates should not be read as evidence of strategic behavior or alignment tampering on their own. This sits in productive tension with the concurrent narrative that models are increasingly gaming evaluations — limiting the inferential weight visible CoT signals can carry.

### Key Takeaways
- Spotting "I'm being tested" in a CoT is a weak behavioral signal — injection effects are near zero and spontaneous shifts cap around 3.7 percentage points.
- The result complicates the narrative that visible evaluation awareness is direct evidence of strategic gaming.
- Strategic-gaming concerns should focus on covert/representational mechanisms rather than visible CoT verbalizations.

---

## 10. Gaming the Metric, Not the Harm: Certifying Safety Audits against Strategic Platform Manipulation

**Authors:** Florian A. D. Burnat, Brittany I. Davidson
**Link:** [Gaming the Metric, Not the Harm: Certifying Safety Audits against Strategic Platform Manipulation](https://arxiv.org/abs/2605.06324)
**Tags:** cs.CR, cs.CY, cs.LG

### Summary
Online-safety regulation under the UK Online Safety Act and the EU Digital Services Act increasingly treats scalar metrics as compliance evidence, but once a metric is announced it becomes an optimization target: a platform can lift its score by routing recommendations through semantically equivalent content variants, without reducing actual harm. The paper asks when an audit metric can still certify a genuine reduction in harm. The protocol is modeled as a published transformation graph whose connected components are semantic classes, treating the metric itself as a security object. Three results follow. First, any metric that scores variants directly is manipulable as soon as two equivalent variants in a harmful class disagree in score. Second, the semantic-envelope lift — assigning each variant the maximum score in its class — is the unique pointwise-minimum among conservative classwise-constant repairs. Third, a class-stratified certificate H*(x) ≤ (1/α̂) M_Env(m)(x) + η̄ holds against every platform strategy, with η̄ absorbing annotation and protocol error. Verification is layered: exhaustive enumeration on a finite-state grid, an SMT encoding in Z3 cross-replayed in cvc5, and a bounded single-player MDP encoded in PRISM-games. The fragile metric fails manipulation invariance and shows large mean gaming gaps; the semantic-envelope metric exhibits no such violation in the tested instances.

### Key Takeaways
- Treat the audit metric itself as a security object: any variant-level scorer is gameable as long as semantically equivalent harmful variants disagree.
- The semantic-envelope lift (max score over each class) gives the unique conservative classwise-constant repair, with a closed-form harm certificate.
- Multi-tool verification (Z3, cvc5, PRISM-games) is becoming a credibility primitive for compliance arguments under DSA/OSA.

---

## 11. Patch2Vuln: Agentic Reconstruction of Vulnerabilities from Linux Distribution Binary Patches

**Authors:** Isaac David, Arthur Gervais
**Link:** [Patch2Vuln: Agentic Reconstruction of Vulnerabilities from Linux Distribution Binary Patches](https://arxiv.org/abs/2605.06601)
**Tags:** cs.CR, cs.AI

### Summary
Security updates create a short window in which defenders and attackers can compare vulnerable and patched software, but in many operational settings the available artifacts are binary packages, not source patches or advisory text. Patch2Vuln asks whether an LM agent restricted to local binary-derived evidence can reconstruct the security meaning of Linux distribution updates. The pipeline is local and resumable: it extracts old/new ELF pairs, diffs them with Ghidra and Ghidriff, ranks changed functions, builds candidate dossiers, and asks an offline agent to produce a preliminary audit, a bounded validation plan, and a final audit. The authors evaluate on 25 Ubuntu .deb package pairs (20 security-update pairs and five negative controls), manually adjudicated against private source-patch and binary-function ground truth. The agent localizes a verified security-relevant patched function in 10 of 20 security pairs and assigns an accepted final root-cause class in 11 of 20. Oracle diagnostics show that six security pairs fail before model reasoning because the binary differ or ranker omits the right function, with one further context-export miss. A separate bounded validation pass produces two minimized behavioral old/new differentials (both for tcpdump), but no crash, timeout, sanitizer finding, or memory-corruption proof. All five negative controls are classified as unknown. Binary-diff coverage and local behavioral validation are flagged as the limiting components.

### Key Takeaways
- An offline LM agent can recover binary-derived patch semantics on roughly half of evaluated Ubuntu security updates, even without source patches or advisory text.
- Failures concentrate before the model — the binary differ/ranker omits the right function in 6/20 cases — so investing in differ coverage matters more than scaling the LM.
- Patch2Vuln is a defender's tool too: faster reconstruction of distribution patches helps closed-source/EoL stacks where source-level advisories aren't available.

---

## 12. SafeHarbor: Hierarchical Memory-Augmented Guardrail for LLM Agent Safety

**Authors:** Zhe Liu, Zonghao Ying, Wenxin Zhang, Quanchen Zou, Deyue Zhang, Dongdong Yang, Xiangzheng Zhang, Hao Peng
**Link:** [SafeHarbor: Hierarchical Memory-Augmented Guardrail for LLM Agent Safety](https://arxiv.org/abs/2605.05704)
**Tags:** cs.CR, cs.AI

### Summary
LLM agents now wield strong tool-use capabilities, which is exactly what makes them dangerous: malicious actors can manipulate them into using tools to generate harmful content. Existing defenses are effective but suffer from over-refusal — strictness gains come at the cost of utility on benign tasks. SafeHarbor proposes a guardrail framework aimed at establishing precise decision boundaries for LLM agents instead of static rules. It extracts context-aware defense rules through enhanced adversarial generation, then injects them dynamically via a local hierarchical memory system that is training-free, efficient, and plug-and-play. The framework also introduces an information-entropy-based self-evolution mechanism that continuously optimizes the memory structure through dynamic node splitting and merging, so the rule set adapts as new attack patterns and benign edge cases accumulate. Empirically, SafeHarbor reaches state-of-the-art performance on both ambiguous benign tasks and explicit malicious attacks, notably attaining a peak benign utility of 63.6% on GPT-4o while maintaining a robust refusal rate exceeding 93% against harmful requests — a practically attractive operating point compared to defenses that improve refusal by collapsing benign performance. The codebase is publicly available, which matters because most production guardrail comparisons cannot replicate vendor-internal numbers. Limitations: results are reported on a fixed attack/benign distribution, and adversaries that target the memory-evolution loop itself are not separately evaluated.

### Key Takeaways
- Hierarchical, training-free memory of context-aware rules attacks the over-refusal failure mode that simpler guardrails create.
- Reaches 63.6% benign utility on GPT-4o while keeping >93% refusal on harmful requests, hitting a usable utility/safety trade-off.
- Entropy-driven self-evolution of the memory structure is a promising primitive for guardrails that need to keep up with shifting attacks; whether the loop itself can be poisoned is an open question.

---
