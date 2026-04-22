# Research Paper Summaries — 2026-04-23

Papers selected from today's digest for in-depth review.

---

## 1. Do Agents Dream of Root Shells? Partial-Credit Evaluation of LLM Agents in Capture The Flag Challenges

**Authors:** Ali Al-Kaswan, Maksim Plotnikov, Maxim Hájek, Roland Vízner, Arie van Deursen, Maliheh Izadi
**Link:** [Do Agents Dream of Root Shells?](https://arxiv.org/abs/2604.19354)
**Tags:** cs.AI

### Summary
Despite rapid deployment of LLM agents in cybersecurity contexts, their actual offensive capability in realistic settings has been poorly characterized. This paper introduces DeepRed, an open-source benchmark that places agents in isolated Kali Linux attacker environments connected to virtualized target machines over private networks — conditions designed to reflect real penetration testing, not sanitized CTF proxies. Agents have access to terminal tools and optional web search, and full execution traces are recorded for post-hoc analysis.

The key methodological contribution is a partial-credit scoring system. Rather than marking challenges as binary solved/unsolved, the authors define challenge-specific checkpoints derived from public writeups (e.g., initial foothold, lateral movement, privilege escalation), then use an automated summarize-then-judge pipeline to score checkpoint completion from agent logs. This granularity reveals where on the attack chain models actually stall.

Ten commercially accessible frontier LLMs were evaluated across ten VM-based CTF challenges spanning network exploitation, web vulnerabilities, binary exploitation, and cryptography. The headline result is sobering: the best-performing model achieves only 35% average checkpoint completion. Models are strongest on challenge types with well-represented training data (web/network) and weakest on tasks requiring non-standard discovery and longer-horizon planning — suggesting that apparent capability in isolated subtasks does not compound into end-to-end offensive proficiency.

The benchmark is open-source and MCP-compatible, making it directly usable by safety teams assessing dual-use risk before model deployment. The partial-credit framing is especially valuable: it tells developers specifically what capabilities to monitor, rather than relying on coarse pass/fail metrics that understate early-chain progress.

### Key Takeaways
- Current frontier LLMs max out at ~35% checkpoint completion on realistic CTF challenges — capability is far below what binary solve rates might imply.
- Partial-credit scoring reveals that models stall primarily on non-standard discovery and multi-step adaptation, not on known-technique execution.
- The open-source, containerized benchmark design enables safety teams to continuously re-evaluate models as capabilities improve.

---

## 2. AI Scientists Produce Results Without Reasoning Scientifically

**Authors:** Martiño Ríos-García, Nawaf Alampara, Chandan Gupta, Indrajeet Mandal, Sajid Mannan, Ali Asghar Aghajani, N. M. Anoop Krishnan, Kevin Maik Jablonka
**Link:** [AI Scientists Produce Results Without Reasoning Scientifically](https://arxiv.org/abs/2604.18805)
**Tags:** cs.AI

### Summary
As LLM-based systems are increasingly positioned as autonomous scientific researchers, this paper asks a deeper question than "can they produce plausible outputs" — it asks whether they reason in a way that makes those outputs epistemically trustworthy. Across 25,000+ agent runs spanning eight scientific domains (from computational workflows to hypothesis-driven inquiry), the authors apply two complementary lenses: a performance decomposition separating the contributions of the base model versus the agent scaffold, and a behavioral analysis of the epistemological structure of agent reasoning.

The findings are striking. The base model accounts for 41.4% of explained variance in both performance and behavior, while the scaffold contributes only 1.5% — meaning scaffold engineering is largely cosmetic. More importantly, agents fail to exhibit core epistemic norms: evidence is ignored in 68% of traces, refutation-driven belief revision occurs in only 26% of cases, and convergent multi-test evidence accumulation is rare. These patterns persist even when agents are given near-complete successful reasoning trajectories as context, and the resulting unreliability compounds across repeated trials.

Crucially, the same broken reasoning pattern appears whether the agent is executing a computational workflow or conducting hypothesis-driven inquiry — suggesting it is a property of the underlying models, not a scaffold or task design artifact. Outcome-based evaluation cannot detect these failures: an agent can produce a correct answer through epistemically invalid reasoning, passing benchmarks while being fundamentally untrustworthy as a scientific actor.

The implication is direct: until reasoning quality itself becomes a training target — not just outcome accuracy — the scientific knowledge produced by such agents cannot be justified by the process that generated it.

### Key Takeaways
- Evidence is ignored in 68% of agent reasoning traces; refutation-driven revision occurs in only 26% — core scientific reasoning norms are routinely violated.
- Base model is the primary driver (41.4% variance explained) while scaffold engineering is nearly irrelevant (1.5%) — better prompting won't fix this.
- Outcome-based benchmarks mask the epistemic failure entirely; reasoning quality must become a first-class training target.

---

## 3. Four-Axis Decision Alignment for Long-Horizon Enterprise AI Agents

**Authors:** Vasundra Srininvasan
**Link:** [Four-Axis Decision Alignment for Long-Horizon Enterprise AI Agents](https://arxiv.org/abs/2604.19457)
**Tags:** cs.AI

### Summary
Enterprise agents making high-stakes decisions — loan underwriting, insurance claims adjudication, clinical review, prior authorization — operate under conditions that single task-success metrics were never designed to handle: lossy memory across long reasoning chains, multi-step inference, and binding regulatory constraints. This paper argues that collapsing all of this into a single scalar conflates distinct failure modes and hides whether an agent meets the standards of its deployment environment.

The proposed solution is a four-axis decomposition, each independently measurable: Factual Precision (FRP) — does the agent retrieve and retain correct facts? Reasoning Coherence (RCS) — is the chain of inference logically consistent? Compliance Reconstruction (CRR) — can the agent reconstruct and adhere to applicable regulatory rules? Calibrated Abstention (CAR) — does the agent correctly identify when it lacks sufficient information to decide, rather than committing on every case?

CRR is the novel regulatory-grounded axis; CAR specifically targets the "always-decides" failure mode that the authors find in all six memory architectures tested on LongHorizon-Bench, a controlled benchmark covering loan qualification and insurance claims with deterministic ground truth. The results show that architecture choice has non-obvious tradeoffs: retrieval architectures collapse on factual precision; schema-anchored designs pay a scaffolding tax; plain summarization under a fact-preservation prompt is a surprisingly strong baseline. All six architectures commit on every case — a dangerous pattern in regulated domains where abstention is often the correct answer.

The framework requires only two steps to transfer to a new regulated domain: build a fact schema and calibrate a CRR auditor prompt — making it practically deployable.

### Key Takeaways
- All six tested memory architectures commit on every case — zero calibrated abstention — a critical failure mode in regulated enterprise decisions.
- Compliance Reconstruction (CRR) is a previously unmeasured alignment axis that determines whether agents can ground decisions in applicable regulations.
- Plain summarization with a fact-preservation prompt outperforms more sophisticated architectures on most axes — current complexity adds scaffolding tax without alignment benefit.

---

## 4. ARES: Adaptive Red-Teaming and End-to-End Repair of Policy-Reward Systems

**Authors:** Jiacheng Liang, Yao Ma, Tharindu Kumarage, Satyapriya Krishna, Rahul Gupta, Kai-Wei Chang, Aram Galstyan, Charith Peris
**Link:** [ARES: Adaptive Red-Teaming and End-to-End Repair of Policy-Reward Systems](https://arxiv.org/abs/2604.18789)
**Tags:** cs.AI

### Summary
RLHF is the dominant technique for aligning LLMs to human preferences and safety requirements, but it introduces a structural vulnerability: if the reward model (RM) fails to penalize an unsafe behavior, the policy model trained against it will learn to produce that behavior. Existing red-teaming approaches target only the policy — the LLM itself — and ignore this systemic weakness where both the base model and its reward model fail simultaneously at unsafe inputs.

ARES addresses this by targeting both components in a unified loop. Its core innovation is a "Safety Mentor" module that dynamically composes adversarial prompts by combining structured components — topics, personas, tactics, goals — to generate semantically coherent attacks with matched malicious and safe response pairs. By simultaneously eliciting failure from both the core LLM and the RM, ARES exposes dual vulnerabilities that policy-only red-teaming misses.

The repair process is two-stage: first fine-tune the RM on the discovered failure cases to improve its ability to detect harmful content; then use the improved RM to re-optimize the policy. This loop continues adaptively, with each repair cycle narrowing the attack surface. Experiments across multiple adversarial safety benchmarks demonstrate substantial safety improvements while preserving general model capabilities — unlike many safety interventions that degrade helpfulness.

The key insight is that RM-policy co-failure is a category of vulnerability that existing safety infrastructure was not designed to discover or fix. By formalizing it and introducing end-to-end repair, ARES establishes a new paradigm for comprehensive RLHF safety alignment that goes beyond patching surface-level refusals.

### Key Takeaways
- Reward model co-failure is a distinct and previously unaddressed vulnerability class in RLHF systems — the RM can learn to ignore the same unsafe behaviors as the policy it trains.
- Structured compositional adversarial prompts (topics × personas × tactics × goals) generate more semantically coherent attacks than heuristic templates.
- Two-stage RM-then-policy repair achieves strong safety gains without the capability regression common in safety fine-tuning interventions.

---

## 5. How Adversarial Environments Mislead Agentic AI

**Authors:** Zhonghao Zhan, Huichi Zhou, Zhenhao Li, Peiyuan Jing, Krinos Li, Hamed Haddadi
**Link:** [How Adversarial Environments Mislead Agentic AI?](https://arxiv.org/abs/2604.18874)
**Tags:** cs.AI

### Summary
Tool-integrated agents are deployed on the premise that external tools ground their reasoning in reality. But the reliance on tools creates an attack surface that current benchmarks entirely ignore: capability evaluations ask "can the agent use tools correctly?" but never "what if the tools lie?" This paper formalizes what the authors call the Trust Gap — agents are evaluated for performance in benign settings, not for skepticism under adversarial ones.

The core threat model is Adversarial Environmental Injection (AEI): adversaries compromise tool outputs to construct a "fake world" of poisoned search results and fabricated reference networks around unsuspecting agents. This is distinct from prompt injection (which targets the agent's input) — AEI targets the agent's perceived reality through tool channels.

The authors operationalize this via POTEMKIN, an MCP-compatible harness for plug-and-play robustness testing. POTEMKIN exposes two orthogonal attack surfaces: The Illusion (breadth attacks) poisons retrieval to induce epistemic drift toward false beliefs through many slightly wrong data points; The Maze (depth attacks) exploits structural traps like circular references to cause policy collapse into infinite loops.

Across 11,000+ runs on five frontier agents, the results reveal a stark robustness tradeoff: resistance to breadth attacks often increases vulnerability to depth attacks, and vice versa. Epistemic robustness and navigational robustness are distinct capabilities that models cannot simultaneously optimize. The MCP-compatible design means POTEMKIN can be integrated into existing agent evaluation pipelines without architectural changes.

### Key Takeaways
- Epistemic robustness (resistance to false beliefs) and navigational robustness (resistance to structural traps) are orthogonal — improving one demonstrably worsens the other across frontier agents.
- AEI is a formally distinct attack class from prompt injection, targeting the agent's perceived environment rather than its instructions.
- 11,000+ runs across five frontier agents confirm the Trust Gap is a systematic property of current architectures, not a model-specific bug.

---

## 6. Beyond Explicit Refusals: Soft-Failure Attacks on Retrieval-Augmented Generation

**Authors:** Wentao Zhang, Yan Zhuang, ZhuHang Zheng, Mingfei Zhang, Jiawen Deng, Fuji Ren
**Link:** [Beyond Explicit Refusals: Soft-Failure Attacks on Retrieval-Augmented Generation](https://arxiv.org/abs/2604.18663)
**Tags:** cs.CR

### Summary
Existing attacks on RAG systems typically aim to trigger explicit refusals or denial-of-service — behaviors that are conspicuous and relatively easy to detect with output monitors. This paper introduces a more dangerous attack class: soft failure, where the system continues to respond fluently and coherently, but the responses are non-informative — degrading the utility of the RAG system without raising any flags.

The proposed attack framework is DEJA (Deceptive Evolutionary Jamming Attack), an automated black-box method that generates adversarial documents designed to induce soft failure. The key insight is that safety-aligned LLMs can be exploited against themselves: their tendency to hedge and express uncertainty in ambiguous contexts becomes a lever for inducing uninformative responses when the retrieved context is carefully poisoned. DEJA uses an evolutionary optimization process guided by a fine-grained Answer Utility Score (AUS), computed by an LLM evaluator, to systematically push responses toward low-certainty outputs while maintaining high retrieval success.

The empirical results are strong: DEJA achieves a Soft Attack Success Rate (SASR) above 79% while keeping hard-failure rates below 15%, significantly outperforming prior attacks. The adversarial documents exhibit high stealth — they evade perplexity-based detection, resist query paraphrasing, and transfer across model families to proprietary systems without retargeting. This cross-model transferability is particularly concerning, as it means documents crafted against an open-weight model can degrade closed commercial RAG deployments.

The implications for enterprise RAG deployments are immediate: output monitoring for refusals is insufficient; utility-based scoring of responses is needed to detect this class of attack.

### Key Takeaways
- Soft failure is a new RAG attack class: responses remain fluent but non-informative, evading standard refusal-based detection entirely.
- DEJA achieves 79%+ SASR while keeping conspicuous hard failures below 15% — a stealthy, high-efficacy attack.
- Adversarial documents transfer across open and closed model families without retargeting, making the attack practical against real commercial deployments.

---

## 7. Owner-Harm: A Missing Threat Model for AI Agent Safety

**Authors:** Dongcheng Zhang, Yiqing Jiang
**Link:** [Owner-Harm: A Missing Threat Model for AI Agent Safety](https://arxiv.org/abs/2604.18658)
**Tags:** cs.CR

### Summary
Current AI agent safety benchmarks are built around a single threat category: generic criminal harm directed at third parties (cybercrime, harassment, weapon synthesis). This paper identifies a systematic blind spot: agents can harm their own deployers — the companies that built and operate them — in ways that existing benchmarks simply do not test for.

The authors ground the problem in documented real-world incidents: Slack AI credential exfiltration (August 2024), Microsoft 365 Copilot calendar-injection data leaks (January 2024), and a Meta agent posting unauthorized content to an external forum (March 2026). They propose Owner-Harm, a formal threat model with eight categories of deployer-directed harm including data exfiltration, reputational damage, unauthorized external communication, and financial harm.

The defense gap is quantified on two existing benchmarks: a compositional safety system achieves 100% TPR / 0% FPR on AgentHarm (generic criminal harm) but only 14.8% TPR on AgentDojo injection tasks (owner harm via prompt injection). A controlled baseline confirms this gap is not inherent to owner-harm as a category (62.7% vs. 59.3%), but arises from environment-bound symbolic rules that fail to generalize across tool vocabularies.

On a new 300-scenario owner-harm benchmark, the best system achieves 85.3% TPR when combining a semantic gate with a deterministic post-audit verifier — with particularly strong gains on Hijacking detection (43.3% → 93.3%). The authors introduce the Symbolic-Semantic Defense Generalization framework relating context coverage to detection rate, providing a theoretical grounding for why symbolic rules fail at tool-vocabulary boundaries.

### Key Takeaways
- Existing safety systems achieve 100% TPR on generic criminal harm but only 14.8% on owner-directed prompt-injection attacks — a fundamental coverage gap.
- A two-layer defense (semantic gate + deterministic post-audit verifier) recovers most of the gap, with layer complementarity providing significant additive benefit.
- Owner-harm is commercially critical and growing with agent deployment; the eight-category taxonomy gives security teams a structured checklist for deployment risk assessment.

---

## 8. Position: No Retroactive Cure for Infringement During Training

**Authors:** Satoru Utsunomiya, Masaru Isonuma, Junichiro Mori, Ichiro Sakata
**Link:** [Position: No Retroactive Cure for Infringement During Training](https://arxiv.org/abs/2604.18649)
**Tags:** cs.CR

### Summary
As AI copyright litigation intensifies, a consensus has emerged in the ML community that post-hoc techniques — machine unlearning, inference-time content filters, and output guardrails — can serve as compliance remedies. This position paper argues forcefully that this consensus is legally wrong: such techniques cannot retroactively cure liability from unlawful data acquisition and training, because legal compliance hinges on data lineage, not model outputs.

The argument proceeds in three parts. First, unauthorized copying and ingestion of training data may constitute legally complete acts of infringement at the moment they occur. Model weights may operate as fixed copies that retain training-derived expressive value — making later output filtering legally irrelevant to whether the original act was infringing. Second, contract and tort law — including licenses, terms of service, and anti-free-riding principles — can independently restrict access and use, often bypassing copyright defenses such as fair use or text-and-data-mining exceptions. These claims succeed independently of whether the model's outputs are filtered at inference time. Third, since value extracted from protected inputs can persist in model weights, remedies like unjust enrichment and disgorgement may reach the model itself — not just specific infringing outputs.

The paper's prescription is a shift from Post-Hoc Sanitization to verifiable Ex-Ante Process Compliance: documenting data sources, licensing, and acquisition methods before and during training, rather than attempting to remediate after the fact. This has direct implications for how AI labs should structure their data governance programs, and for how courts should evaluate the adequacy of post-training compliance claims.

### Key Takeaways
- Machine unlearning and output guardrails cannot cure pre-existing infringement liability — compliance is determined by data acquisition practices, not model outputs.
- Contract and ToS violations succeed independently of copyright defenses, making fair use arguments irrelevant to many training data disputes.
- The required shift is toward Ex-Ante Process Compliance — documented, auditable data lineage from the start of training, not retroactive filtering.

---

## 9. Detecting Data Contamination in Large Language Models

**Authors:** Juliusz Janicki, Savvas Chamezopoulos, Evangelos Kanoulas, Georgios Tsatsaronis
**Link:** [Detecting Data Contamination in Large Language Models](https://arxiv.org/abs/2604.19561)
**Tags:** cs.AI

### Summary
A core evidentiary challenge in AI copyright litigation is proving that specific copyrighted documents were included in a model's training corpus. Membership Inference Attacks (MIAs) are the primary technical tool for this — but they have typically been evaluated under unrealistic white-box assumptions. This paper studies state-of-the-art MIAs under strict black-box conditions, comparing their performance across a unified benchmark to determine whether any can reliably detect membership in current frontier LLMs.

The authors evaluate multiple SOTA MIAs and introduce a new method called Familiarity Ranking, designed to give models more freedom of expression and better characterize the reasoning behind outputs. The core finding is sobering: none of the tested methods can reliably detect membership, with AUC-ROC values hovering near 0.5 (random guessing) across several frontier LLMs. Higher TPR and FPR values on more advanced LLMs reflect their stronger generalization and reasoning capabilities — which make them appear "familiar" with text they may not have seen, not because they memorize more, but because they generalize better.

This creates a fundamental evidentiary problem: the better a model becomes at generalization, the harder it is to distinguish memorization from generalization using black-box methods — precisely as legal pressure to prove memorization increases. The paper effectively establishes that current MIA methodology is inadequate for the IP litigation context it is being called upon to serve.

The implication for compliance is clear: black-box auditing of what data is "in" a model is not currently a reliable method, reinforcing the argument for Ex-Ante Process Compliance (documented data lineage from the start) over post-hoc technical auditing.

### Key Takeaways
- All tested black-box MIA methods achieve AUC-ROC near 0.5 — essentially random performance at detecting training data membership in frontier LLMs.
- Advanced LLMs produce higher TPR and FPR simultaneously, reflecting generalization strength rather than memorization — making the detection problem harder as models improve.
- The results reinforce the case for data lineage documentation over technical post-hoc auditing, which is not currently fit for legal evidentiary purposes.

---

## 10. Reasoning Structure Matters for Safety Alignment of Reasoning Models

**Authors:** Yeonjun In, Wonjoong Kim, Sangwu Park, Chanyoung Park
**Link:** [Reasoning Structure Matters for Safety Alignment of Reasoning Models](https://arxiv.org/abs/2604.18946)
**Tags:** cs.AI

### Summary
Large reasoning models (LRMs) — models trained with extended chain-of-thought and reinforcement learning to produce multi-step reasoning — achieve impressive performance on complex tasks but exhibit distinctive safety failure modes. Understanding why is essential for aligning them. This paper argues that safety failures in LRMs are not caused by the content of unsafe responses, but by flaws in the reasoning structure that precedes those responses — specifically, patterns in how the model sets up its reasoning that predictably lead to harmful outputs.

Based on this structural insight, the authors propose AltTrain, a post-training method that targets the reasoning structure rather than just the output. AltTrain requires no complex RL training or reward design — it uses supervised fine-tuning on a deliberately small dataset of only 1,000 examples. The key is that these examples are curated to demonstrate structurally correct safe reasoning patterns, teaching the model to reason toward safety rather than just suppressing specific outputs.

Experiments across multiple LRM backbones and model sizes demonstrate strong safety alignment with robust generalization across diverse tasks — reasoning benchmarks, QA, summarization, and multilingual settings. Critically, the safety improvements do not come at the cost of reasoning quality, which is a common failure mode of safety interventions applied to reasoning models.

The practical significance is high: achieving safety alignment through 1K SFT examples rather than full RL re-training dramatically reduces the computational and engineering burden of aligning reasoning models — making it feasible to apply alignment interventions more frequently as model capabilities evolve.

### Key Takeaways
- Safety failures in reasoning models are structurally determined — the reasoning patterns that precede harmful outputs are the root cause, not just output-layer defects.
- AltTrain achieves strong alignment with only 1,000 SFT examples and no RL, making it practical for frequent re-application as models are updated.
- Structural reasoning alignment generalizes across reasoning, QA, summarization, and multilingual tasks — avoiding the brittleness of output-suppression approaches.

---

## 11. Human-Guided Harm Recovery for Computer Use Agents

**Authors:** Christy Li, Sky CH-Wang, Andi Peng, Andreea Bobu
**Link:** [Human-Guided Harm Recovery for Computer Use Agents](https://arxiv.org/abs/2604.18847)
**Tags:** cs.AI

### Summary
As LLM agents gain real computer-use capabilities — executing actions on actual filesystems, browsers, and applications — preventing harmful actions becomes insufficient as the sole safety strategy. When prevention fails, the agent may have already reached a harmful state: files modified, emails sent, credentials exposed. This paper formalizes a neglected problem: harm recovery, defined as the challenge of optimally steering an agent from a harmful state back to a safe one in alignment with human preferences.

The authors conduct a formative user study to ground what "recovery" means to real users, identifying key dimensions and producing a natural language rubric. Analysis of 1,150 pairwise judgments reveals that preferences are context-dependent: users prefer pragmatic, targeted recovery strategies over comprehensive long-term approaches — a finding that challenges the assumption that "more thorough" recovery is always better.

These learned preferences are operationalized in a reward model that re-ranks multiple candidate recovery plans generated by an agent scaffold at test time — combining the diversity of generation with the alignment of preference-based re-ranking. To systematically evaluate recovery, the authors introduce BackBench, a benchmark of 50 computer-use tasks that specifically test an agent's ability to recover from harmful states (rather than avoid them).

Human evaluation confirms that the reward model scaffold produces higher-quality recovery trajectories than base agents and rubric-based scaffolds. The work establishes harm recovery as a distinct class of agent safety intervention — complementary to prevention — and provides both the benchmark and reward model architecture needed for future research.

### Key Takeaways
- Harm recovery is a distinct safety problem from harm prevention — post-hoc remediation requires its own methods, benchmarks, and alignment criteria.
- Users prefer pragmatic, targeted recovery over comprehensive long-term remediation; ignoring this preference leads to over-engineered interventions that decrease user trust.
- BackBench provides the first systematic evaluation framework for post-harm recovery in real computer-use settings.

---

## 12. Towards Understanding the Robustness of Sparse Autoencoders

**Authors:** Ahson Saiyed, Sabrina Sadiekh, Chirag Agarwal
**Link:** [Towards Understanding the Robustness of Sparse Autoencoders](https://arxiv.org/abs/2604.18756)
**Tags:** cs.LG

### Summary
Gradient-based jailbreak attacks (such as GCG and BEAST) exploit LLMs' internal gradient structure to craft adversarial suffixes that bypass safety training. Sparse Autoencoders (SAEs) — bottleneck networks trained to produce sparse, interpretable decompositions of model activations — are widely used in mechanistic interpretability research, but their potential as a robustness mechanism has not been systematically studied.

This paper investigates whether integrating pretrained SAEs into transformer residual streams at inference time can defend against gradient-based jailbreaks without modifying model weights or blocking gradients. The core hypothesis is a representational bottleneck effect: sparse projection may reshape the optimization geometry that jailbreak attacks exploit, making adversarial perturbations less effective without explicitly filtering for safety.

The study tests across four model families (Gemma, LLaMA, Mistral, Qwen) using two strong white-box attacks (GCG, BEAST) and three black-box benchmarks. SAE-augmented models achieve up to a 5x reduction in jailbreak success rate relative to undefended baselines and also reduce cross-model attack transferability — meaning adversarial suffixes crafted for one model are less likely to transfer to the SAE-augmented version.

Two key findings emerge from parametric ablations: a monotonic dose-response relationship between L0 sparsity and attack success rate (sparser representations → more robust), and a layer-dependent defense-utility tradeoff where intermediate residual stream layers balance robustness improvement against clean task performance degradation. These findings provide the first empirical evidence that the representational bottleneck hypothesis is plausible and actionable for practitioners considering SAEs as a defense mechanism.

### Key Takeaways
- SAE integration achieves up to 5x reduction in jailbreak success rate without modifying weights — a surprising robustness benefit from an interpretability tool.
- Sparsity and defense strength follow a monotonic dose-response: higher L0 sparsity consistently reduces attack success, providing a tunable robustness knob.
- Intermediate residual stream layers offer the best defense-utility tradeoff — early and late layers either degrade task performance or provide insufficient protection.

---
