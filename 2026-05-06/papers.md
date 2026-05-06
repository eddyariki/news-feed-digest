# Research Paper Summaries — 2026-05-06

Papers selected from today's digest for in-depth review.

---

## 1. Using Large Language Models for Embodied Planning Introduces Systematic Safety Risks

**Authors:** Tao Zhang, Kaixian Qu, Zhibin Li, Jiajun Wu, Marco Hutter, Manling Li, Fan Shi
**Link:** [Using large language models for embodied planning introduces systematic safety risks](https://arxiv.org/abs/2604.18463)
**Tags:** cs.AI, cs.LG, cs.RO

### Summary
This paper addresses a critical gap in robotic AI deployment: while LLMs are increasingly used as planners for physical robotic systems, there has been no systematic evaluation of how safely they plan. The authors introduce DESPITE, a benchmark of 12,279 tasks spanning physical dangers (e.g., hazardous tool use) and normative dangers (e.g., privacy violations), with fully deterministic validation so results are reproducible and unambiguous.

Across 23 models, the core finding is that planning ability and safety awareness are effectively orthogonal capacities. The best-planning model in the study fails to produce a valid plan on only 0.4% of tasks — near-perfect planning — yet still generates dangerous plans on 28.3% of tasks. Among 18 open-source models ranging from 3B to 671B parameters, planning ability scales dramatically with model size (0.4–99.3%) while safety awareness remains stubbornly flat (38–57%). The authors characterize a multiplicative relationship between the two: larger models complete more tasks safely primarily because they plan better, not because they have stronger danger avoidance. Three proprietary reasoning models (e.g., o3-class) break from this trend, reaching 71–81% safety awareness — but standard proprietary non-reasoning models and open-source reasoning models stay below 57%.

The practical implication is stark: as planning ability saturates for frontier models, safety awareness becomes the binding constraint for deployment in real-world robotic systems. Current safety training appears largely decoupled from physical and normative danger recognition.

### Key Takeaways
- Near-perfect task planning does not imply safe planning — the two capabilities scale independently.
- Open-source model safety awareness plateaus around 57% regardless of scale; proprietary reasoning models are the exception.
- DESPITE provides a reproducible benchmark to track progress on robotic safety separately from planning competence.

---

## 2. Toward a Principled Framework for Agent Safety Measurement

**Authors:** Shuyi Lin, Anshuman Suri, Alina Oprea, Cheng Tan
**Link:** [Toward a Principled Framework for Agent Safety Measurement](https://arxiv.org/abs/2605.01644)
**Tags:** cs.CR

### Summary
Today's agent safety evaluations run a handful of sampled or greedy rollouts and report a single safe/unsafe rate. This paper argues that approach is structurally blind to the long-tail trajectories where unsafe behavior actually emerges — low-probability but non-negligible action sequences that any production deployment will eventually hit. The authors propose measuring agent safety by search rather than sampling.

Their framework, BOA, takes a deployment configuration (model, decoder, prompt, environment, judger, likelihood budget) and searches the space of in-budget trajectories to report a safety score: the probability that the agent stays safe under that configuration. BOA operates both within a single LLM generation round and across the full agent-environment interaction tree, and uses batched decoding/judging, prefix caching, and chunked tree expansion to make search computationally practical. On agent-safety workloads, BOA discovers unsafe trajectories that greedy and sampled evaluations entirely miss.

Beyond discovery, BOA enables apples-to-apples comparison of models, defenses, and attacks all on the same scale — a capability current evaluation practice lacks. The authors also demonstrate that the framework can rank competing defenses quantitatively, giving developers a principled way to choose between mitigations.

The key limitation is computational: exhaustive search requires meaningful GPU budget, which may constrain adoption for smaller teams. But the authors argue this cost is justified given that single safe/unsafe rates give false assurance.

### Key Takeaways
- Greedy/sampled rollouts systematically miss rare but real unsafe trajectories in deployed agents.
- Safety should be treated as a search problem over a likelihood-weighted trajectory space, not a point estimate.
- BOA enables unified, quantitative ranking of models, attacks, and defenses on the same evaluation scale.

---

## 3. SRTJ: Self-Evolving Rule-Driven Training-Free LLM Jailbreaking

**Authors:** Jindong Li, Ying Liu, Yali Fu, Jinjing Zhu, Leyao Wang, Menglin Yang, Rex Ying
**Link:** [SRTJ: Self-Evolving Rule-Driven Training-Free LLM Jailbreaking](https://arxiv.org/abs/2605.00974)
**Tags:** cs.CR, cs.CL

### Summary
Automated jailbreak research has proliferated, but existing methods share a fundamental weakness: they fail to systematically accumulate and reuse knowledge from prior attack attempts. Each run starts roughly from scratch, and there is no principled mechanism for composing reusable attack rules across different target models or evolving safety mechanisms. SRTJ addresses this with a Self-Evolving Rule-Driven framework that accumulates transferable attack knowledge over time without updating any model parameters.

The core innovation is coupling experience-driven attack generation with Answer Set Programming (ASP) for rule selection and constraint-aware composition. After each attempt, an iterative verifier provides feedback that jointly refines successful strategies and analyzes failure patterns. The resulting rule memory organizes distilled attack knowledge into three temporal tiers — long-term (stable transferable strategies), medium-term (model-specific adaptations), and short-term (transient exploratory behaviors) — explicitly balancing exploitation of known-good strategies with exploration of new attack surfaces.

Evaluated on HarmBench, SRTJ achieves strong and stable attack performance across diverse target LLMs, with improved robustness and generalization compared to prior methods. The framework's design means that attack capability compounds over time as the rule memory grows, a dynamic not present in one-shot or fixed-template approaches.

From a defensive perspective, SRTJ highlights that safety mechanisms must be evaluated against attacks that learn from interaction rather than static templates — a higher bar than most current red-teaming protocols impose.

### Key Takeaways
- Attack knowledge can compound over time via hierarchical rule memory, making SRTJ increasingly effective with experience.
- ASP-based rule composition allows principled constraint-aware selection among attack strategies.
- Defenses evaluated only against static attack templates underestimate real-world adversarial adaptability.

---

## 4. ContextualJailbreak: Evolutionary Red-Teaming via Simulated Conversational Priming

**Authors:** Mario Rodríguez Béjar, Francisco J. Cortés-Delgado, S. Braghin, Jose L. Hernández-Ramos
**Link:** [ContextualJailbreak: Evolutionary Red-Teaming via Simulated Conversational Priming](https://arxiv.org/abs/2605.02647)
**Tags:** cs.CL, cs.CR

### Summary
Research has consistently shown that multi-turn conversational priming — where earlier turns covertly bias a model's later responses — outperforms single-turn prompt injection on capable models. Yet automated red-teaming has remained almost entirely in the single-turn setting, unable to reason about which forms of conversational scaffolding induce compliance. ContextualJailbreak closes this gap with a black-box evolutionary search over simulated multi-turn primed dialogues.

The method uses five semantically defined mutation operators — roleplay, scenario, expand, troubleshooting, and mechanistic (the latter two are novel to this paper) — to evolve multi-turn conversational scaffolds. A graded 0–5 harm score from a two-level judge serves as the in-loop fitness signal, meaning partially harmful responses guide search rather than being discarded as failures. This graded signal is key: it lets the optimizer work with partial progress toward harmful compliance rather than treating every non-100% response as equivalent to failure.

Results across 50 representative HarmBench behaviors are striking: 100% attack success rate (ASR) on gpt-oss:20B, qwen3-8B, and llama3.1:70B; 90% on gpt-oss:120B. The 40 maximally harmful attacks discovered against gpt-oss:120B transfer without adaptation to closed frontier models — 90% on gpt-4o-mini, 70% on gpt-5 and gemini-3-flash — but only 17.5% on claude-opus-4-7 and 15% on claude-sonnet-4-6, revealing a pronounced provider-level asymmetry in alignment robustness.

### Key Takeaways
- Multi-turn priming attacks, when automated via evolutionary search, achieve near-100% ASR on many open models.
- Graded harm scoring as a fitness signal is a meaningful methodological advance over binary pass/fail red-teaming.
- Claude models show substantially stronger resistance to transferred attacks than other frontier providers.

---

## 5. Trojan Hippo: Weaponizing Agent Memory for Data Exfiltration

**Authors:** Debeshee Das, Julien Piet, Darya Kaviani, Luca Beurer-Kellner, Florian Tramèr, David Wagner
**Link:** [Trojan Hippo: Weaponizing Agent Memory for Data Exfiltration](https://arxiv.org/abs/2605.01970)
**Tags:** cs.CR, cs.AI

### Summary
Memory systems that let LLM agents persist user information across sessions are increasingly common — and this paper shows they introduce a severe new attack class. Trojan Hippo is a persistent memory attack in which an attacker plants a dormant payload via a single untrusted tool call (e.g., a crafted incoming email). The payload lies dormant in the agent's long-term memory until the user later discusses sensitive topics such as finance, health, or personal identity, at which point it activates and exfiltrates high-value personal data to the attacker.

The authors evaluate the attack across four memory backends — explicit tool memory, agentic memory, RAG, and sliding-window context — achieving 85–100% ASR against current frontier models from OpenAI and Google. Critically, planted memories successfully activate even after 100 benign sessions, meaning the payload can survive extended normal use before triggering.

Four defenses inspired by basic security principles (isolation, sanitization, access control, and detection) are evaluated. They substantially reduce ASR — in some configurations to 0–5% — but at significant utility costs that vary widely depending on task requirements. This security-utility tradeoff means no single defense is clearly deployable across all use cases, and the effective real-world deployment of memory-system defenses remains an open problem. The paper introduces a dynamic evaluation framework using OpenEvolve-based adaptive red-teaming to stress-test defenses against continuously refined attacks.

### Key Takeaways
- A single crafted tool call can plant a persistent payload that survives 100+ benign sessions before activating.
- The attack achieves 85–100% ASR against GPT and Gemini frontier models across multiple memory backends.
- Available defenses reduce risk significantly but impose utility costs that complicate real-world deployment.

---

## 6. Autonomous LLM Agent Worms: Cross-Platform Propagation, Automated Discovery and Temporal Re-Entry Defense

**Authors:** Mingming Zha, Xiaofeng Wang
**Link:** [Autonomous LLM Agent Worms: Cross-Platform Propagation, Automated Discovery and Temporal Re-Entry Defense](https://arxiv.org/abs/2605.02812)
**Tags:** cs.CR

### Summary
LLM agents that run as long-lived processes with persistent workspaces, memory files, scheduled task state, and messaging integrations create a novel propagation risk: attacker-influenced content written into persistent state can re-enter the LLM decision context via scheduled autoloading and drive high-risk actions including configuration changes and cross-agent transmission. This paper presents the first systematic framework for analyzing and defending against persistent worm propagation in file-backed multi-agent LLM ecosystems.

Two analysis tools are introduced. SSCGV is an automated source-code graph analyzer that traces data flow from file I/O to LLM context injection points and ranks carriers by their context injection position without manual analysis. SRPO is a summary-resilient payload optimizer that generates worm payloads robust to LLM-mediated summarization and paraphrasing across multi-hop communication — a critical capability since LLM agents often summarize external content before processing it.

Evaluated on three production agent frameworks, the authors demonstrate zero-click autonomous propagation, 3-hop cross-platform transmission without platform-specific adaptation, inter-agent privilege escalation, and data exfiltration. Two empirical insights emerge: user prompt carriers achieve higher attack compliance than system prompt carriers, and read operations are the primary integrity threat. The defense, RTW-A, is formally proven under a No Persistent Worm Propagation theorem and covers write-before-exposed-read re-entry, sealed configuration, typed memory promotion, and capability attenuation. Affected systems are anonymized pending coordinated disclosure.

### Key Takeaways
- LLM agent worms can propagate across platforms in three hops with no platform-specific payload adaptation.
- Scheduled autoloading of persistent state is the primary re-entry mechanism enabling zero-click propagation.
- RTW-A provides a formally verified defense that preserves ordinary workflows while blocking the worm propagation chain.

---

## 7. GPU Fingerprinting for Location Verification

**Authors:** Wayne Tee, Jonathan Happel
**Link:** [GPU Fingerprinting for Location Verification](https://arxiv.org/abs/2605.01930)
**Tags:** cs.CR

### Summary
Governing where AI training occurs — particularly for frontier models — has become a live policy concern, and current technical mechanisms rely on cryptographic keys stored on-chip to verify GPU location. This paper identifies a fundamental vulnerability: those keys can be extracted by adversaries with physical access to the hardware, compromising the entire location verification protocol. Once a key is copied, an adversary can present a GPU as being wherever needed while it is actually elsewhere.

The authors propose an alternative: use hardware fingerprints derived from measurable physical characteristics of the GPU rather than extractable cryptographic keys. Physical fingerprints are inherently bound to the specific piece of hardware and cannot be copied or replicated, providing a location verification guarantee that survives physical access by attackers.

As a proof of concept, the authors develop a GPU fingerprinting methodology and achieve up to 100% re-identification accuracy in small-scale tests. The approach is framed explicitly within AI chip governance contexts — detecting unauthorized deployment, enforcing export controls, and verifying compliance with data-residency requirements for AI model training.

The primary limitation is scale: results come from small-scale controlled tests, and the methodology has not been demonstrated on the large heterogeneous GPU fleets present in production data centers. Fingerprint stability over time (as chips age or are modified) and adversarial robustness against fingerprint cloning attacks also remain open questions. Nevertheless, the paper provides an important proof of concept for a governance mechanism that is structurally harder to subvert than cryptographic key storage.

### Key Takeaways
- On-chip cryptographic keys for GPU location verification can be extracted by physical attackers, undermining the entire governance mechanism.
- Hardware fingerprinting provides a copy-resistant alternative that is bound to specific physical silicon.
- 100% re-identification accuracy demonstrated at small scale; production-scale validation is the critical next step.

---

## 8. RefusalGuard: Geometry-Preserving Fine-Tuning for Safety in LLMs

**Authors:** Sadia Asif, Mohammad Mohammadi Amiri
**Link:** [RefusalGuard: Geometry-Preserving Fine-Tuning for Safety in LLMs](https://arxiv.org/abs/2605.01913)
**Tags:** cs.LG, cs.AI, cs.CL, cs.CR

### Summary
A well-established but poorly understood problem in LLM deployment is that fine-tuning safety-aligned models for downstream tasks often substantially degrades their refusal behavior, leaving them vulnerable to adversarial misuse. Prior work has shown safety-relevant features are encoded in structured representations in the model's activation space, but the mechanisms by which fine-tuning disrupts these representations have not been characterized.

This paper investigates the representation-level mechanics of alignment degradation. The authors find that standard fine-tuning induces three specific failure modes: systematic drift in safety-relevant representations, distortion of their geometric structure, and interference between task optimization and safety features. These effects collectively increase harmful compliance even when the downstream task has no apparent connection to safety.

Motivated by these findings, REFUSALGUARD introduces a representation-level fine-tuning framework that constrains updates in hidden representation space to keep safety-mediating components stable while allowing task-specific learning to proceed in orthogonal directions. The approach is model-agnostic and evaluated across LLaMA, Gemma, and Qwen model families on adversarial safety benchmarks (AdvBench, DirectHarm4, JailbreakBench) as well as standard downstream utility tasks.

REFUSALGUARD achieves attack success rates comparable to base safety-aligned models — essentially recovering the pre-fine-tuning safety level — while maintaining competitive performance on downstream tasks. It significantly outperforms existing baselines on this safety-utility tradeoff. The implication is that safety alignment can be structurally preserved during fine-tuning through geometric constraints rather than requiring separate safety fine-tuning afterward.

### Key Takeaways
- Fine-tuning causes geometric drift in activation space that degrades safety representation even for unrelated tasks.
- Constraining updates to preserve safety-relevant activation geometry recovers pre-fine-tuning refusal behavior.
- The approach is model-family agnostic, validated across LLaMA, Gemma, and Qwen.

---

## 9. Logit-Gap Steering: A Forward-Pass Diagnostic for Alignment Robustness

**Authors:** Tung-Ling Li, Hongliang Liu
**Link:** [Logit-Gap Steering: A Forward-Pass Diagnostic for Alignment Robustness](https://arxiv.org/abs/2506.24056)
**Tags:** cs.CR, cs.CL, cs.LG

### Summary
RLHF alignment trains models to refuse unsafe requests, but it provides no direct quantification of how robust that refusal is on any given prompt. This paper introduces the refusal-affirmation logit gap — the difference between the top refusal-token logit and the top affirmative-token logit at the first decoding step — as a single scalar that quantifies the per-prompt safety margin alignment provides.

Empirically, alignment widens this gap on 97.5–99.8% of toxic prompts across three model families, confirming the metric is a reliable signal of alignment influence. Median gap closure co-varies with True-ASR ranking across suffix strategies, providing an internal consistency check. The authors then introduce logit-gap steering: a gradient-free, forward-pass-only method that discovers short in-distribution suffixes (fewer than 10 tokens per component) whose cumulative effect closes the refusal-affirmation gap. The method requires approximately 26,000 forward-pass equivalents per model family — about 2 minutes on a single A100 — which is roughly 125× more efficient than a single GCG search.

Suffixes discovered on 0.5B–2B models transfer without modification to 72B models within the same family. An 8-suffix ensemble achieves 38–96% True ASR across 13 models on AdvBench and HarmBench. Most critically, the discovered suffixes have 10³–10⁴× lower perplexity than GCG outputs, which means published perplexity-filter defenses that collapse GCG from 64.7% to 1.0% leave these suffixes nearly intact (76.9%→76.0%). This demonstrates that perplexity filtering is not a robust defense against in-distribution adversarial prompts.

### Key Takeaways
- Alignment margins, while consistently present, are thin and efficiently measurable via the refusal-affirmation logit gap.
- Logit-gap steering is 125× more efficient than GCG and transfers across model scales within a family.
- Perplexity-filter defenses fail against in-distribution suffixes discovered by this method.

---

## 10. AgenticVM: Agentic AI for Adaptive Software Vulnerability Management

**Authors:** Asrul Arifin, Hussain Ahmad, Yiyao Zhang, Diksha Goel
**Link:** [AgenticVM: Agentic AI for Adaptive Software Vulnerability Management](https://arxiv.org/abs/2605.01739)
**Tags:** cs.CR

### Summary
Security Operations Centers (SOCs) face a chronic mismatch between alert volumes and analyst capacity. Modern software systems generate thousands of vulnerability findings per scan, but manual triage is slow, inconsistent, and cannot scale. AgenticVM proposes a multi-agent LLM framework that automates the full vulnerability management pipeline: detection, assessment, prioritization, and reporting.

The architecture combines three components: rule-based processing for initial filtering, a BERT-based CVSS prediction module that fills in missing severity attributes, and specialized LLM-driven agents for complex reasoning about context and priority. Data is ingested from both the National Vulnerability Database (NVD) and the European Union Vulnerability Database (EUVD), giving broad coverage of known CVEs across jurisdictions.

The headline result is a 98% alert reduction — in one evaluation scenario, reducing raw scanner output from 3,983 findings to 82 high-priority items requiring analyst attention — while predicting missing CVSS attributes with 89.3% accuracy. These results suggest that agentic automation can dramatically reduce the signal-to-noise ratio in vulnerability management without proportionate loss in risk visibility.

The paper also provides practical design insights for real-world deployment: agent decomposition strategies (how to split responsibilities across specialized agents), patterns for integrating security tools with LLM reasoning, and recommendations for human-in-the-loop governance. The latter is particularly important for compliance contexts where automated triage decisions may need auditable justification.

### Key Takeaways
- Multi-agent LLM automation reduces raw vulnerability alerts by 98% while maintaining risk visibility.
- BERT-based CVSS prediction achieves 89.3% accuracy on missing severity attributes, reducing manual assessment overhead.
- Human-in-the-loop governance hooks are designed in from the start, addressing SOC compliance requirements.

---

## 11. LocalAlign: Enabling Generalizable Prompt Injection Defense via Generation of Near-Target Adversarial Examples for Alignment Training

**Authors:** Yuyang Gong, Zihao Wang, Jiawei Liu, XiaoFeng Wang
**Link:** [LocalAlign: Enabling Generalizable Prompt Injection Defense via Generation of Near-Target Adversarial Examples for Alignment Training](https://arxiv.org/abs/2605.01462)
**Tags:** cs.CR

### Summary
Prompt injection — where malicious commands embedded in untrusted data (retrieved web content, tool outputs, emails) override trusted instructions — is a foundational threat to LLM agent deployment. Existing defenses train models to maintain an explicit boundary between trusted commands and untrusted data, teaching the model to prioritize the trusted field. However, these defenses generalize poorly when the injected command produces a response that is close to, but not identical to, the correct response. The model's trust boundary is loose around the correct answer, leaving nearby deviations exploitable.

LocalAlign addresses this via adversarial training with near-target examples. The key insight is that generating adversarial examples where the injected command induces a response that is near-but-wrong to the correct response enforces a tighter robustness boundary than training against fixed hand-crafted targets. Near-target examples are generated efficiently using prompting and a single inference step — no gradient-based search is required.

The additional challenge is that near-target adversarial examples vary substantially in quality across samples: some examples land very close to the correct response (high training value) while others do not. LocalAlign addresses this with a margin-aware alignment algorithm that quantifies each sample's distance to the correct response and assigns proportionally larger training weight to nearer examples, focusing learning budget on the hardest cases.

The result is a defense that generalizes better to realistic injection scenarios than prior fine-tuning-based approaches, particularly when the attacker has crafted an injection that produces plausible-but-wrong model outputs.

### Key Takeaways
- Existing prompt injection defenses fail when injected commands produce near-correct responses — a common real-world scenario.
- Near-target adversarial examples generated in a single inference step enforce tighter robustness boundaries than static attack templates.
- Margin-aware weighting focuses alignment training on adversarial examples closest to the correct response.

---

## 12. Architectural Obsolescence of Unhardened Agentic-AI Runtimes

**Authors:** Alfredo Metere
**Link:** [Architectural Obsolescence of Unhardened Agentic-AI Runtimes](https://arxiv.org/abs/2605.01740)
**Tags:** cs.CR, cs.AI, cs.MA

### Summary
Agentic AI runtimes issue tool calls, send messages, and actuate devices on behalf of LLMs. A load-bearing safety property of any such runtime is detecting the four ways an action can diverge from its audit record: F1 gate-bypass (action taken without authorization), F2 audit-forgery (record altered after the fact), F3 silent host failure (action not recorded), and F4 wrong-target (action sent to incorrect recipient). This paper tests OpenClaw — described as the most engineered single-user agentic-AI gateway in public release — against all four patterns.

The result is stark: OpenClaw achieves 0.000 recall on every cell of every confusion matrix across a 1,600-sample baseline and a ten-LLM cross-model generalization run. The runtime catches none of the four divergence patterns. The author identifies seven structural security mechanisms absent from OpenClaw's source tree that would be required: a biconditional checker, hash-chained audit log, extension admission gate, two-layer egress guard, Bell-LaPadula classification policy, module-signing trust root, and bootstrap seal.

An MIT-licensed drop-in fork, enclawed-oss, ships all seven mechanisms and achieves P = R = F₁ = accuracy = 1.000 on the same input. The performance gap is structural, not parametric: a six-line append-only widening of enclawed-oss's DLP regex catalog raises per-channel F3 detection by 14.6% net at unchanged precision, while the same edit on OpenClaw has no structural component to land in.

The paper argues this constitutes architectural obsolescence — a strictly better alternative exists, is adoptable today, and the gap requires re-architecture rather than configuration tuning.

### Key Takeaways
- The most-engineered public agentic-AI gateway catches zero instances of all four action-audit divergence patterns.
- Missing safety is architectural: seven specific structural mechanisms are absent and cannot be added through configuration.
- A drop-in fork with these seven mechanisms achieves perfect detection across all divergence patterns on the same evaluation harness.

---

*Generated from [digest-2026-05-06.md](digest-2026-05-06.md)*
