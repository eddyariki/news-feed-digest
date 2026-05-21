# Research Paper Summaries — 2026-05-21

Papers selected from today's digest for in-depth review.

---

## 1. POLAR-Bench: A Diagnostic Benchmark for Privacy-Utility Trade-offs in LLM Agents

**Authors:** Qiaoyuan Zheng, Yiqu Yang, Qi Gao, Imanol Schlag
**Link:** [POLAR-Bench: A Diagnostic Benchmark for Privacy-Utility Trade-offs in LLM Agents](https://arxiv.org/abs/2605.19127)
**Tags:** cs.AI

### Summary
POLAR-Bench tackles a concrete operational problem: when an LLM agent holds private user data and converses with a third-party model that may probe for it, can the trusted agent reliably honor the user's privacy policy while still completing its task? The authors construct a benchmark in which a policy-equipped trusted model interacts with an adversarial third-party model over 7,852 samples across 10 domains. They score privacy and utility via deterministic set-membership checks and systematically vary two orthogonal axes — the dimension of the privacy policy and the attack strategy — producing a 5×5 diagnostic surface for each evaluated model. The headline finding is a sharp capability split: frontier closed models withhold over 99% of protected attributes even under adversarial probing, while open-weight models in the 1–30B range — precisely the class users tend to run locally as their own "trusted" agents on-device or via private inference — perform far worse, with the weakest leaking more than half of the protected attributes. Because the benchmark localizes where each model's intent-following breaks down across policy/attack dimensions, it provides a structured target for privacy alignment work rather than a single aggregate score. The implication is that the self-hosting story for privacy-sensitive agents is currently undermined by the safety gap between frontier and open-weight models.

### Key Takeaways
- Frontier models exceed 99% protected-attribute withholding under adversarial third-party probing, but small open-weight (1–30B) models often leak over half.
- The 5×5 policy-dimension × attack-strategy diagnostic surface localizes specific failure modes rather than just ranking models.
- Privacy alignment is most urgent for the on-device / private-inference open-weight tier, since that is exactly where users assume their data is safest.

---

## 2. DecisionBench: A Benchmark for Emergent Delegation in Long-Horizon Agentic Workflows

**Authors:** Yuxuan Gao, Megan Wang, Yi Ling Yu, Zijian Carl Ma, Ao Qu
**Link:** [DecisionBench: A Benchmark for Emergent Delegation in Long-Horizon Agentic Workflows](https://arxiv.org/abs/2605.19099)
**Tags:** cs.AI, cs.CL, cs.MA

### Summary
DecisionBench introduces a benchmark substrate aimed at a question existing agent evaluations ignore: when an agent can call peer models, does it correctly decide *whether* and *to whom* to delegate? The authors fix a task suite (GAIA, tau-bench, BFCL multi-turn), an 11-model peer pool covering seven vendor families, a delegation interface (`call_model` plus optional `read_profile`), a deterministic skill-annotation layer, and a multi-axis metric suite covering quality, cost, latency, delegation rate, routing fidelity-at-k, vendor self-preference, and a counterfactual delegation ceiling. A five-condition reference sweep over 23,375 task instances yields three findings. First, end-task quality is statistically indistinguishable across four awareness conditions (|β| ≤ 0.010, p ≥ 0.21), so quality-only evaluation masks the orchestration signal entirely. Second, routing fidelity-at-1 swings from 7.5% to 29.5% across conditions at near-equal mean quality, with the delivery channel (on-demand tool vs. preloaded description) dominating description content. Third, a counterfactual upper bound places perfect delegation 15–31 points above measured performance on every suite, exposing substantial unrealized headroom. The substrate is deliberately agnostic to how peer information is produced, so learned routers, richer peer memories, adaptive profile construction, and multi-step delegation can all be evaluated against the same metrics — a useful piece of common infrastructure as multi-agent orchestration matures.

### Key Takeaways
- Quality-only metrics fail to surface delegation behavior; routing fidelity and counterfactual ceilings must be tracked separately.
- Delivery channel (on-demand tool vs. preloaded peer description) matters more than the content of the description itself.
- Current agents leave 15–31 points of potential performance on the table compared to a perfect-delegation oracle.

---

## 3. Attention-Guided Reward for Reinforcement Learning-based Jailbreak against Large Reasoning Models

**Authors:** Zheng Lin, Zhenxing Niu, Haoxuan Ji, Yuzhe Huang, Haichang Gao
**Link:** [Attention-Guided Reward for Reinforcement Learning-based Jailbreak against Large Reasoning Models](https://arxiv.org/abs/2605.19485)
**Tags:** cs.AI

### Summary
The paper studies why Large Reasoning Models (LRMs) — models that expose structured step-by-step reasoning content — appear to be more vulnerable to jailbreaks than standard LLMs, and converts that observation into a more effective attack. The authors first analyze attention patterns in successful versus failed jailbreak attempts and find a consistent signature: in successful attacks, the model assigns *lower* attention to the harmful tokens in the input prompt while assigning *higher* attention to those same tokens once they appear inside the chain-of-thought. In other words, the reasoning surface that makes LRMs powerful also gives an attacker a controllable internal state to steer. Building on this, they propose an RL-based jailbreak method whose reward function explicitly incorporates these attention signals, and they expand the action space with diverse persuasion strategies that consistently raise attack success rate (ASR). Across five open- and closed-source LRMs evaluated on three benchmarks, the attack delivers substantially higher ASR than prior approaches while also improving efficiency and transferability. The implication for defenders is twofold: visible reasoning is a new attack surface, not just a capability boost, and existing input-side moderation that does not also reason about how prompts are *processed* internally will continue to be bypassed.

### Key Takeaways
- LRM jailbreak success is empirically tied to a specific attention shift between input prompt and generated reasoning content.
- An RL reward built on this attention signature plus persuasion-strategy action expansion materially raises ASR across five LRMs.
- Reasoning-exposing models need defenses that consider internal processing dynamics, not just input/output content classification.

---

## 4. Backdooring Masked Diffusion Language Models

**Authors:** Daniel Yiming Cao, Chengzhong Wang, Sheng-Yen Chou, Chengyu Huang, Pin-Yu Chen, Shengwei An
**Link:** [Backdooring Masked Diffusion Language Models](https://arxiv.org/abs/2605.19262)
**Tags:** cs.LG, cs.CR

### Summary
Masked diffusion language models (MDLMs) are gaining traction as an alternative to autoregressive LMs, but their training-time security has been essentially unstudied. This is not academic: existing backdoor attacks on Gaussian diffusion or autoregressive models don't transfer cleanly, because MDLMs rely on discrete state corruption and iterative denoising rather than continuous noise or left-to-right prediction. The authors present the first systematic study of training-time backdoors on MDLMs and introduce SHADOWMASK, which modifies the forward corruption process by replacing the standard all-mask terminal distribution with a trigger-mask mixture prior. This carves out a dedicated denoising pathway from trigger-corrupted states to attacker-specified targets while leaving clean-input denoising effectively unchanged. They formalize the construction by defining the backdoored forward process, deriving the reverse-time posterior, and obtaining the continuous-time training objective. Empirical evaluation on a DiT-based MDLM and LLaDA-8B-Instruct across WikiText-103, OpenWebText, and Alpaca shows near-100% attack success, substantially outperforming standard data poisoning, with clean-task utility largely preserved. The backdoor remains effective under both full-model and parameter-efficient fine-tuning, and is robust against representative defenses. The takeaway is that any deployment pipeline assuming MDLMs inherit autoregressive-LM threat models is mis-specified; defenses need to be designed against the discrete-denoising surface specifically.

### Key Takeaways
- MDLMs have a distinct training-time backdoor surface that prior autoregressive/Gaussian-diffusion attacks don't capture.
- SHADOWMASK reaches near-100% attack success while preserving clean utility and surviving full-model and PEFT fine-tuning.
- Defenders treating MDLMs as drop-in replacements for autoregressive LMs inherit a hidden, currently-undefended attack surface.

---

## 5. Whispers of Wealth: Red-Teaming Google's Agent Payments Protocol via Prompt Injection

**Authors:** Tanusree Debi, Wentian Zhu, Pranjol Sen Gupta
**Link:** [Whispers of Wealth: Red-Teaming Google's Agent Payments Protocol via Prompt Injection](https://arxiv.org/abs/2601.22569)
**Tags:** cs.CR, cs.AI

### Summary
The Agent Payments Protocol (AP2) is Google's attempt to harden agent-led financial transactions through cryptographically verifiable mandates, but the authors argue that cryptographic binding of *mandates* does not address the upstream attack surface of *contextual reasoning*. They perform a hands-on AI red-team against AP2 using a functional shopping agent built on Gemini-2.5-Flash and the Google ADK framework, and identify two new attack techniques: the Branded Whisper Attack, which manipulates product ranking via injected instructions, and the Vault Whisper Attack, which extracts sensitive user data. Both rely on indirect and direct prompt injection rather than any cryptographic weakness — the mandate is still signed correctly, but the agent's *decisions about what to mandate* have already been subverted. The experimental section shows simple adversarial prompts reliably bend agent behavior in ways the protocol's signing layer cannot detect, because by the time the mandate is generated the harm is already encoded into it. The authors conclude that current agentic payment architectures need stronger isolation and additional defensive layers, and the work serves as a concrete case study for the broader pattern flagged in the digest's themes: identity-and-cryptography controls are insufficient for autonomous agents whose decision-making itself is the soft target.

### Key Takeaways
- Cryptographically verifiable AP2 mandates do not protect against prompt injection that corrupts the agent *before* the mandate is signed.
- Two new attack classes (Branded Whisper, Vault Whisper) reliably manipulate product ranking and exfiltrate sensitive data in a working Gemini-2.5-Flash + ADK agent.
- Agent-payment architectures need defense-in-depth at the reasoning/isolation layer, not just at the transaction-signing layer.

---

## 6. Learning Efficient Guardrails for Compliance

**Authors:** Xiaofei Wen, Wenjie Jacky Mo, Yanan Xie, Peng Qi, Muhao Chen
**Link:** [Learning Efficient Guardrails for Compliance](https://arxiv.org/abs/2510.03485)
**Tags:** cs.AI

### Summary
The paper targets a gap between standard safety guardrails (which focus on broad refusal categories) and the real-world need for autonomous web agents to follow specific, long-form *policies*. The authors introduce PolicyGuardBench, a 60k policy-trajectory pair benchmark that evaluates compliance through both full-trajectory analysis and, more importantly, a novel prefix-based violation detection task — the practical question of "is this trajectory *already* heading into a policy violation given what's happened so far?" rather than only the post-hoc question of "did the completed trajectory violate?" Prefix detection matters because it enables intervention before damage is done. They then train PolicyGuard, a lightweight classifier-style guardrail that achieves strong detection accuracy while remaining cheap to run inline. PolicyGuard generalizes well to unseen domains, which is critical because the space of real-world policies is unbounded — guardrails that only work on policies seen at training time are not deployable in practice. The contribution is two-fold: a benchmark structure that pushes the field toward early detection rather than post-hoc auditing, and evidence that compliance enforcement does not need to scale to giant models — small, fast guardrails can carry the load. For operators building agent products with bespoke usage policies, this is a more tractable enforcement story than wrapping a heavyweight safety model around every action.

### Key Takeaways
- PolicyGuardBench's 60k pairs include prefix-based violation detection, enabling early intervention rather than post-hoc auditing.
- A small, lightweight PolicyGuard classifier can detect policy violations efficiently without scaling to large model sizes.
- The model generalizes to unseen domains, addressing the unbounded-policy reality of production agent deployments.

---

## 7. Distributional AGI Safety

**Authors:** Nenad Tomašev, Matija Franklin, Julian Jacobs, Sébastien Krier, Simon Osindero
**Link:** [Distributional AGI Safety](https://arxiv.org/abs/2512.16856)
**Tags:** cs.AI

### Summary
The paper challenges a foundational assumption of much AI safety work: that AGI will arrive as a single monolithic system, and that aligning *it* is the central problem. The authors instead argue the "patchwork" or "distributional" hypothesis — that general capability is more likely to first manifest as coordinated behavior across groups of sub-AGI agents with complementary skills, tools, and affordances — deserves serious consideration, especially given the rapid deployment of tool-using agents that already communicate and coordinate. Under this hypothesis, alignment work targeted at individual systems is necessary but insufficient: safety must also be a property of *interactions* and *aggregate behavior* across agent populations. They propose a framework for distributional AGI safety centered on virtual agentic sandbox economies (impermeable or semi-permeable), where agent-to-agent transactions are governed by robust market mechanisms coupled with auditability, reputation management, and oversight to mitigate *collective* risks. This is a position/agenda paper rather than an empirical one, and its main contribution is reframing: the unit of safety analysis shifts from one model to an ecosystem, and the toolkit shifts from RLHF-style alignment toward mechanism design, market microstructure, and audit/reputation infrastructure. For practitioners building multi-agent systems today, the implication is that single-agent safety evaluations may systematically miss the most consequential failure modes.

### Key Takeaways
- The "monolithic AGI" assumption underlying most alignment work may not match the actual deployment trajectory of coordinated sub-AGI agents.
- Distributional safety calls for sandboxed agent economies with market mechanisms, reputation systems, and audit infrastructure — not just better per-model alignment.
- Single-agent safety evaluations risk missing failure modes that emerge only from agent-to-agent interaction at scale.

---

## 8. Measuring Safety Alignment Effects in Autonomous Security Agents

**Authors:** Isaac David, Arthur Gervais
**Link:** [Measuring Safety Alignment Effects in Autonomous Security Agents](https://arxiv.org/abs/2605.19722)
**Tags:** cs.CR, cs.AI

### Summary
The paper asks a question that single-turn refusal benchmarks structurally cannot answer: do stock safety-aligned models and their uncensored or abliterated derivatives actually behave differently when wrapped into autonomous security agents that inspect repositories, call tools, and produce vulnerability evidence inside authorized sandboxes? The authors build a trace-based benchmark of 30 local vulnerability-analysis tasks with fixed tools, deterministic success predicates, redaction rules, and grounding checks. They compare four stock models against their less-restricted derivatives — Gemma 4 31B, Gemma 4 26B A4B, Qwen2.5-Coder 7B, and Llama 3.1 8B — and release 1,500 security-agent traces plus 800 non-security control traces. The Gemma pairs show large gains for the less-restricted variant on security tasks (31B: 14.0% vs 0.7%; 26B: 10.7% vs 0.0%) with higher mean grounding scores and 0.0% refusal, suppressed-action, and unsafe-action rates in the 31B traces. But control conditions undermine any clean "less restriction = better security agent" narrative: Gemma gaps also appear on ordinary coding tasks, the less-restricted Qwen2.5-Coder is *worse* (2.0% vs 5.3%), and the abliterated Llama derivative breaks the tool protocol entirely. Across all families, hard proof-of-trigger and patch-verification tasks remain unsolved. The methodological point is that safety alignment in autonomous agents should be measured at the system level — separating refusal, unsafe action, tool reliability, and evidence grounding — rather than collapsed onto a single refusal-rate axis.

### Key Takeaways
- Single-turn refusal benchmarks fail to capture how safety alignment actually affects multi-step security-agent behavior.
- Uncensored Gemma variants gain substantially on security tasks but also on ordinary coding, while abliterated Llama breaks tool use — there is no universal "less-restricted = better agent" effect.
- System-level safety evaluation must separately track refusal, unsafe action, tool reliability, and evidence grounding.

---

## 9. Going PLACES: Participatory Localized Red Teaming for Text-to-Image Safety in the Global South

**Authors:** Charvi Rastogi, Mukul Bhutani, Minsuk Kahng, Shamsuddeen Hassan Muhammad, Evgeniia Razumovskaia, Priyanka Suresh, Ibrahim Said Ahmad, Charu Kalia, Yaaseen Mahomed, Madhurima Maji, Minjae Lee, Alicia Parrish, Jessica Quaye, Vijay Janapa Reddi, Aishwarya Verma, Lora Aroyo
**Link:** [Going PLACES: Participatory Localized Red Teaming for Text-to-Image Safety in the Global South](https://arxiv.org/abs/2605.19190)
**Tags:** cs.CY, cs.AI, cs.HC

### Summary
The paper confronts a structural blind spot in T2I safety: although these models are deployed globally, their safety frameworks are calibrated to Western-centric defaults, leaving users in the Global South exposed to harms the developers' evaluation pipelines were never set up to detect. The authors run community-centered, localized red-teaming studies in partnership with universities in Ghana, Nigeria, and two regions of India (Karnataka and Punjab), explicitly recruiting from secondary urban centers and running engagement and training workshops to contextualize local norms. The result is PLACES, a dataset of over 26,000 T2I model failure examples that, on analysis, exhibits substantially greater socio-cultural and linguistic diversity than existing geography-agnostic crowdsourced data. Beyond scale, the authors document attack patterns specifically enabled by local cultural and linguistic nuances, and identify distinct thematic clusters within regions — for example, religion-centered failures cluster sharply in India. They also surface novel harms grounded in "normative dissonance" — violations of religious norms, ignorance of local customs, ominous symbolism — that existing safety taxonomies miss entirely. The argument is methodological: scaling existing red-teaming pipelines is not enough; participatory, localized data collection is structurally required to build T2I safety frameworks that work outside the regions where they were designed.

### Key Takeaways
- Western-calibrated T2I safety frameworks systematically miss harms tied to local cultural, religious, and linguistic context.
- The PLACES dataset (>26k examples, four Global South regions) reveals adversarial patterns and harm categories not seen in geography-agnostic data.
- Scaling alone won't close the gap — participatory, localized methodologies are a structural requirement for T2I safety, not an optional extension.

---

## 10. ClinSeekAgent: Automating Multimodal Evidence Seeking for Agentic Clinical Reasoning

**Authors:** Juncheng Wu, Letian Zhang, Yuhan Wang, Haoqin Tu, Hardy Chen, Zijun Wang, Cihang Xie, Yuyin Zhou
**Link:** [ClinSeekAgent: Automating Multimodal Evidence Seeking for Agentic Clinical Reasoning](https://arxiv.org/abs/2605.20176)
**Tags:** cs.CL

### Summary
Most clinical-LLM work hands the model a pre-curated bundle of evidence and measures how well it reasons over it — a setup that overstates real-world readiness, because actual clinical workflows require the model to actively seek, plan, and synthesize evidence from messy heterogeneous sources. ClinSeekAgent reframes the problem as active evidence acquisition: given only a query and access to raw data, the agent queries medical knowledge bases, navigates raw EHRs, and invokes medical imaging tools, iteratively refining hypotheses as new evidence arrives, before producing a grounded clinical decision. The framework serves two roles — inference-time agent for frontier LLMs, and training-time pipeline for distilling high-quality trajectories into compact open models. To evaluate it fairly, the authors build ClinSeek-Bench, which pairs Curated Input reasoning (fixed pre-selected evidence) with Automated Evidence-Seeking (raw clinical data). On text-only EHR tasks ClinSeekAgent improves Claude Opus 4.6 from 60.0 to 63.2 F1 and MiniMax M2.5 from 43.1 to 47.3, with positive risk-prediction gains on 7 of 9 host models. On multimodal tasks the gain is much larger — Claude Opus 4.6 jumps from 47.5 to 62.6 (+15.1), with consistent gains across three CXR-related task groups. The distilled ClinSeek-35B-A3B model reaches 34.0 average F1 on AgentEHR-Bench, +11.9 over its Qwen3.5-35B-A3B baseline and approaching Claude Opus 4.6. The takeaway is that evidence acquisition, not reasoning quality, is the binding constraint for clinical agents.

### Key Takeaways
- Existing clinical-LLM benchmarks overstate readiness by pre-curating evidence; active evidence-seeking changes the difficulty profile materially.
- ClinSeekAgent delivers especially large multimodal gains (+15.1 F1 on Claude Opus 4.6) by acquiring imaging and EHR evidence on demand.
- The same framework distills into a compact ClinSeek-35B-A3B model that closes most of the gap to frontier closed models.

---

## 11. Robotics-Inspired Guardrails for Foundation Models in Socially Sensitive Domains

**Authors:** Rebecca Ramnauth, Drazen Brscic, Brian Scassellati
**Link:** [Robotics-Inspired Guardrails for Foundation Models in Socially Sensitive Domains](https://arxiv.org/abs/2605.19940)
**Tags:** cs.AI, cs.RO

### Summary
The paper argues that current guardrail approaches — training-time alignment, prompting, decoding constraints, post-hoc moderation — share two structural limits when foundation models are deployed in socially sensitive domains like education, mental health, and caregiving: they provide empirical risk reduction rather than enforceable behavioral guarantees, and they treat safety as a property of individual outputs rather than of interaction *trajectories*. In settings where harms are cumulative and context-dependent — a tutoring system that slowly drifts off-curriculum, a therapy assistant that gradually adopts an inappropriate stance — output-level moderation is the wrong unit of analysis. The authors reframe guardrails as a problem of runtime behavioral control over interaction trajectories, importing formal constructs from robotics for constraint enforcement in uncertain, closed-loop systems. They instantiate this in the Grounded Observer framework and apply it across three real deployments: small talk, in-home autism therapy, and behavioral de-escalation in schools. Across these settings, the framework enables runtime interventions that catch drift into undesirable interaction regimes while still adapting to context. They close by discussing extensions toward stronger formal guarantees. The implication is that "guardrails" should not be a single category — content classifiers and trajectory-level runtime controllers do qualitatively different jobs, and high-stakes social deployments need the latter.

### Key Takeaways
- Per-output moderation is the wrong unit of analysis for cumulative, context-dependent harms in education, mental health, and caregiving.
- The Grounded Observer framework imports robotics-style runtime constraint enforcement over interaction trajectories, validated across three real deployments.
- Foundation-model safety in socially sensitive domains needs enforceable behavioral guarantees, not just empirical risk reduction.

---

## 12. From Refusal to Recovery: A Control-Theoretic Approach to Generative AI Guardrails

**Authors:** Ravi Pandya, Madison Bland, Duy P. Nguyen, Changliu Liu, Jaime Fernández Fisac, Andrea Bajcsy
**Link:** [From Refusal to Recovery: A Control-Theoretic Approach to Generative AI Guardrails](https://arxiv.org/abs/2510.13727)
**Tags:** cs.AI

### Summary
The authors argue that as generative AI moves from chat assistants into agents that act on a user's behalf — shopping bots, autonomous vehicles — the safety problem shifts from "block harmful content" to "preempt downstream financial or physical harm," and existing guardrails are mismatched for this new problem. Today's guardrails rely on output classification using labeled datasets and human-specified criteria, making them brittle to novel hazardous situations; and even when they correctly flag a problem, the only response on offer is refusal, which is not always a safe action (an autonomous car refusing to act is itself dangerous). The paper reframes agentic AI safety as a sequential decision problem and formalizes it through safety-critical control theory operating within the AI's latent representation of the world. The resulting predictive guardrails (i) monitor the AI's outputs/actions in real time and (ii) proactively correct risky outputs into safe ones, doing so in a model-agnostic way that wraps around any underlying AI model. They also provide a practical training recipe using safety-critical reinforcement learning to compute these guardrails at scale. Experiments in simulated driving and e-commerce show the control-theoretic guardrails reliably steer LLM agents clear of catastrophic outcomes — collisions in the driving setting, bankruptcy in e-commerce — while preserving task performance. This is a principled dynamic alternative to today's flag-and-block guardrails, and complements [Robotics-Inspired Guardrails](https://arxiv.org/abs/2605.19940) in moving the field toward runtime control rather than content classification.

### Key Takeaways
- Refusal is not always safe — autonomous agents need recovery actions, not just block decisions.
- Control-theoretic guardrails operating in the model's latent space monitor and proactively correct risky actions, model-agnostically.
- Empirical results in simulated driving and e-commerce show catastrophic outcomes (collisions, bankruptcy) can be averted without sacrificing task performance.

---
