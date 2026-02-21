# AI News Digest — February 20, 2026

> **501 articles** curated from ArXiv, TechCrunch, The Verge, MIT Technology Review, The Hacker News, Schneier on Security, and OpenAI Blog. Coverage includes 421 research papers, 22 news articles, and 58 security items.

---

## Highlights

- **Cline CLI supply chain attack** — The popular AI coding assistant was compromised via a hijacked npm token, silently installing autonomous agent "OpenClaw" on developer systems
- **Amazon's AI coding agent causes 13-hour AWS outage** — Kiro, Amazon's AI coding assistant, triggered a prolonged outage; Amazon blames human employees for not catching the mistake
- **OpenAI's first hardware product revealed** — A ChatGPT-powered smart speaker with camera, expected at $200–$300
- **Benchmark saturation crisis** — New systematic study shows AI benchmarks are plateauing faster than ever, challenging how we measure progress
- **Agents under attack** — Multiple papers this week on agent hijacking, safety gaps in tool-calling, and the fundamental limits of black-box safety evaluation
- **Reasoning efficiency breakthroughs** — Papers on early exiting via entropy after `</Think>`, speculative drafts for test-time scaling, and progressive thought encoding for training
- **India AI investment surge** — G42/Cerebras deploy 8 exaflops in India; Peak XV raises $1.3B; General Catalyst commits $5B over 5 years; Nvidia deepens startup engagement

---

## News

### Industry & Products

- **[OpenAI's first ChatGPT gadget could be a smart speaker with a camera](https://www.theverge.com/ai-artificial-intelligence/882077/openai-chatgpt-smart-speaker-camera-glasses-lamp)** — OpenAI's first hardware release will be a smart speaker with a camera ($200–$300) that can recognize items and conversations nearby. *(The Verge)*

- **[Amazon blames human employees for an AI coding agent's mistake](https://www.theverge.com/ai-artificial-intelligence/882005/amazon-blames-human-employees-for-an-ai-coding-agents-mistake)** — AWS suffered a 13-hour outage in December caused by AI coding assistant Kiro's actions. Amazon blamed human employees for not catching the error. *(The Verge)*

- **[Great news for xAI: Grok is now pretty good at answering questions about Baldur's Gate](https://techcrunch.com/2026/02/20/great-news-for-xai-grok-is-now-pretty-good-at-answering-questions-about-baldurs-gate/)** — High-level xAI engineers were pulled off projects to ensure Grok could answer detailed questions about the video game Baldur's Gate. *(TechCrunch)*

- **[Google's new Gemini Pro model has record benchmark scores — again](https://techcrunch.com/2026/02/19/googles-new-gemini-pro-model-has-record-benchm)** — Google's latest Gemini Pro model sets new benchmark records. *(TechCrunch)*

- **[Our First Proof submissions](https://openai.com/index/first-proof-submissions)** — OpenAI shares its AI model's proof attempts for the First Proof math challenge, testing research-grade reasoning on expert-level problems. *(OpenAI Blog)*

### AI & Society

- **[Trump is making coal plants even dirtier as AI demands more energy](https://www.theverge.com/science/882288/trump-ai-data-center-power-plant-pollution-mercury-mats)** — The Trump administration repealed Mercury and Air Toxics Standards (MATS) just as AI data center electricity demand rises. *(The Verge)*

- **[Anthropic-funded group backs candidate attacked by rival AI super PAC](https://techcrunch.com/2026/02/20/anthropic-funded-group-backs-candidate-attacked-by-rival-ai-super-pac/)** — Dueling pro-AI PACs have centered around one New York congressional bid: Alex Bores, whose RAISE Act requires AI developers to disclose safety protocols. *(TechCrunch)*

- **['Toy Story 5' takes aim at creepy AI toys: 'I'm always listening'](https://techcrunch.com/2026/02/20/toy-story-5-takes-aim-at-creepy-ai-toys-im-always-listening/)** — The new Toy Story film tackles addictive, AI-enabled tablets and toys. Out June 19. *(TechCrunch)*

- **[AI's promise to indie filmmakers: Faster, cheaper, lonelier](https://techcrunch.com/2026/02/20/ais-promise-to-indie-filmmakers-faster-cheaper-lonelier/)** — AI expands access to filmmaking but risks overwhelming creativity with low-effort generated content. *(TechCrunch)*

- **[Exclusive eBook: The great AI hype correction of 2025](https://www.technologyreview.com/2026/02/20/1133368/exclusive-ebook-the-great-al-hype-correction-of-2025/)** — MIT Technology Review reflects on how top AI company leaders made promises they couldn't keep in 2025. *(MIT Technology Review)*

- **[OpenAI says 18- to 24-year-olds account for nearly 50% of ChatGPT usage in India](https://techcrunch.com/2026/02/20/openai-says-18-to-24-year-olds-account-for-nearly-50-of-chatgpt-usage-in-india/)** — Users under 30 account for 80% of ChatGPT usage in India. *(TechCrunch)*

### Funding & Investment

- **[General Catalyst commits $5B to India over five years](https://techcrunch.com/2026/02/19/general-catalyst-commits-5b-to-india-over-five-years/)** — A sharp jump from GC's earlier $500M–$1B India earmark. *(TechCrunch)*

- **[Peak XV raises $1.3B, doubles down on AI](https://techcrunch.com/2026/02/20/peak-xv-raises-1-3b-doubles-down-on-ai-as-global-vc-rivalry-in-india-heats-up/)** — The former Sequoia India prioritizes AI, fintech, and cross-border bets. *(TechCrunch)*

- **[UAE's G42 teams up with Cerebras to deploy 8 exaflops of compute in India](https://techcrunch.com/2026/02/20/uaes-g42-teams-up-with-cerebras-to-deploy-8-exaflops-of-compute-in-india/)** — A major compute infrastructure play for the Indian AI ecosystem. *(TechCrunch)*

- **[Nvidia deepens early-stage push into India's AI startup ecosystem](https://techcrunch.com/2026/02/19/nvidia-deepens-early-stage-push-into-indias-ai-startup-ecosystem/)** — Nvidia expands engagement with Indian AI startups. *(TechCrunch)*

- **[InScope nabs $14.5M to solve the pain of financial reporting](https://techcrunch.com/2026/02/20/inscope-nabs-14-5m-to-solve-the-pain-of-financial-reporting/)** — Founded by accountants from Flexport, Miro, and Hopin, InScope automates financial statement preparation. *(TechCrunch)*

---

## Security

### Threat Intelligence & Incidents

- **[Cline CLI 2.3.0 Supply Chain Attack Installed OpenClaw on Developer Systems](https://thehackernews.com/2026/02/cline-cli-230-supply-chain-attack.html)** — A compromised npm publish token was used to push a malicious update to the AI coding assistant Cline CLI, silently installing the autonomous AI agent OpenClaw on developer machines. *(The Hacker News)*

- **[BeyondTrust Flaw Used for Web Shells, Backdoors, and Data Exfiltration](https://thehackernews.com/2026/02/beyondtrust-flaw-used-for-web-shells.html)** — CVE-2026-1731 (CVSS 9.9) in BeyondTrust Remote Support and Privileged Remote Access is being actively exploited to deploy VShell and execute OS commands. *(The Hacker News)*

- **[ClickFix Campaign Abuses Compromised Sites to Deploy MIMICRAT Malware](https://thehackernews.com/2026/02/clickfix-campaign-abuses-compromised.html)** — A sophisticated campaign leverages compromised legitimate sites across multiple industries to deliver the new MIMICRAT (AstarionRAT) remote access trojan. *(The Hacker News)*

- **[FBI Reports 1,900 ATM Jackpotting Incidents Since 2020, $20M Lost in 2025](https://thehackernews.com/2026/02/fbi-reports-1900-atm-jackpotting.html)** — 700 ATM jackpotting incidents in 2025 alone, with over $40M in total collective losses since 2020. *(The Hacker News)*

- **[Former Google Engineers Indicted Over Trade Secret Transfers to Iran](https://thehackernews.com/2026/02/three-former-google-engineers-indicted.html)** — Two former Google engineers and a spouse indicted for stealing trade secrets and transferring them to unauthorized locations including Iran. *(The Hacker News)*

- **[Ukrainian National Sentenced to 5 Years in North Korea IT Worker Fraud Case](https://thehackernews.com/2026/02/ukrainian-national-sentenced-to-5-years.html)** — Oleksandr Didenko sentenced for wire fraud conspiracy and identity theft, facilitating North Korea's fraudulent IT worker scheme. *(The Hacker News)*

### Privacy & Surveillance

- **[Ring Cancels Its Partnership with Flock](https://www.schneier.com/blog/archives/2026/02/ring-cancels-its-partnership-with-flock.html)** — Amazon's Ring drops surveillance-tech company Flock, signaling how toxic Flock has become. Bruce Schneier advises removing Ring doorbells. *(Schneier on Security)*

- **[Identity Cyber Scores: The New Metric Shaping Cyber Insurance in 2026](https://thehackernews.com/2026/02/identity-cyber-scores-new-metric.html)** — With 1 in 3 cyber-attacks involving compromised accounts, insurers are placing greater emphasis on identity posture metrics. *(The Hacker News)*

### Security Research (Notable ArXiv Papers)

- **[SoK: DARPA's AI Cyber Challenge (AIxCC)](https://arxiv.org/abs/2602.07666)** — Comprehensive analysis of DARPA's AIxCC competition (2023–2025), the largest competition for building autonomous cyber reasoning systems.

- **[Systems Security Foundations for Agentic Computing](https://arxiv.org/abs/2512.01295)** — Establishes security foundations for increasingly widespread agentic AI systems and their tool-use patterns.

- **[Patch-to-PoC: Agentic LLM Systems for Linux Kernel N-Day Reproduction](https://arxiv.org/abs/2602.07287)** — Systematic study of autonomous LLM-based systems for reproducing Linux kernel vulnerabilities from patches.

- **[What Makes a Good LLM Agent for Real-world Penetration Testing?](https://arxiv.org/abs/2602.17622)** — Analyzes 28 LLM-based penetration testing systems to identify what drives performance variation.

- **[Privacy in Theory, Bugs in Practice: Grey-Box Auditing of Differential Privacy Libraries](https://arxiv.org/abs/2602.17454)** — Finds subtle bugs in differential privacy implementations that frequently invalidate theoretical guarantees.

- **[NESSiE: The Necessary Safety Benchmark](https://arxiv.org/abs/2602.16756)** — Introduces a benchmark focused on minimal test cases for information and access security in LLMs — errors that should never exist.

---

## Research Papers (~30 Notable Selections)

### Agents & Tool Use

- **[Mobile-Agent-v3.5: Multi-platform Fundamental GUI Agents](https://arxiv.org/abs/2602.16855)** — Introduces GUI-Owl-1.5, a native GUI agent model (2B–235B parameters) supporting desktop, mobile, and browser platforms with cloud-edge collaboration.

- **[OpenSage: Self-programming Agent Generation Engine](https://arxiv.org/abs/2602.16891)** — An agent development kit that generates agents through self-programming, addressing limitations in current agent topology, tools, and memory systems.

- **[IntentCUA: Intent-level Representations for Computer-Use Agents](https://arxiv.org/abs/2602.17049)** — Proposes skill abstraction and multi-agent planning for computer-use agents operating over long horizons with noisy perception.

- **[KLong: Training LLM Agent for Extremely Long-horizon Tasks](https://arxiv.org/abs/2602.17547)** — Open-source LLM agent trained via trajectory-splitting SFT followed by progressive RL to handle extremely long task horizons.

- **[Dynamic System Instructions and Tool Exposure for Efficient Agentic LLMs](https://arxiv.org/abs/2602.17046)** — Proposes Instruction-Tool compression to reduce cost and latency of re-ingesting long system instructions each agent turn.

- **[Web Verbs: Typed Abstractions for Reliable Task Composition on the Agentic Web](https://arxiv.org/abs/2602.17245)** — Defines typed abstractions for web agents, moving beyond brittle prompt-based approaches to structured, reliable task composition.

- **[Beyond Reactivity: Measuring Proactive Problem Solving in LLM Agents](https://arxiv.org/abs/2510.19771)** — New benchmark for evaluating whether LLM agents can anticipate user needs and solve problems autonomously, rather than just reacting.

- **[Overseeing Agents Without Constant Oversight](https://arxiv.org/abs/2602.16844)** — Three user studies on designing informative but not overwhelming trace logs for human oversight of agentic AI systems.

- **[How AI Coding Agents Communicate: Pull Request Descriptions and Human Review](https://arxiv.org/abs/2602.17084)** — Studies how AI coding agents differ in PR description characteristics and how human reviewers respond.

- **[Wink: Recovering from Misbehaviors in Coding Agents](https://arxiv.org/abs/2602.17037)** — Framework for detecting and recovering from misbehaviors in autonomous coding agents (deviation from spec, incorrect edits, etc.).

### Safety & Alignment

- **[Fundamental Limits of Black-Box Safety Evaluation](https://arxiv.org/abs/2602.16984)** — Formalizes information-theoretic and computational barriers to safety evaluation via latent context-conditioned policies — models that behave differently based on unobservable context.

- **[DeepContext: Stateful Real-Time Detection of Adversarial Intent Drift](https://arxiv.org/abs/2602.16935)** — Addresses the safety gap where stateless guardrails miss multi-turn adversarial tactics. Proposes temporal-aware detection of evolving threats.

- **[Automating Agent Hijacking via Structural Template Injection](https://arxiv.org/abs/2602.16958)** — Demonstrates how adversaries can automate agent hijacking by injecting malicious instructions into retrieved content — a top OWASP LLM threat.

- **[Mind the GAP: Text Safety Does Not Transfer to Tool-Call Safety](https://arxiv.org/abs/2602.16943)** — Shows that safety training on text generation does not protect LLM agents when making tool calls with real-world consequences.

- **[Defining and Evaluating Physical Safety for Large Language Models](https://arxiv.org/abs/2411.02317)** — Addresses the unexplored risk of LLMs causing physical harm when controlling robotic systems like drones.

- **[Learning to Stay Safe: Adaptive Regularization Against Safety Degradation during Fine-Tuning](https://arxiv.org/abs/2602.17546)** — Proposes adaptive regularization to prevent safety behavior deterioration during both benign and adversarial fine-tuning.

- **[Fail-Closed Alignment for Large Language Models](https://arxiv.org/abs/2602.16977)** — Identifies that current LLM refusal mechanisms are fail-open and proposes fail-closed alignment as an alternative.

- **[Intent Laundering: AI Safety Datasets Are Not What They Seem](https://arxiv.org/abs/2602.16729)** — Systematic evaluation revealing quality problems in widely used AI safety datasets.

### Reasoning & Test-Time Compute

- **[Entropy After `</Think>` for Reasoning Model Early Exiting](https://arxiv.org/abs/2509.26522)** — Quantitatively confirms that reasoning LLMs overthink (continuing to revise after finding the correct answer) and proposes entropy-based early exit.

- **[SPECS: Faster Test-Time Scaling through Speculative Drafts](https://arxiv.org/abs/2506.15733)** — Uses speculative drafts to reduce the cost of test-time compute scaling for LLM reasoning.

- **[Training Large Reasoning Models Efficiently via Progressive Thought Encoding](https://arxiv.org/abs/2602.16839)** — Addresses the RL training bottleneck for large reasoning models by replacing autoregressive decoding of long rollouts with progressive encoding.

- **[WS-GRPO: Weakly-Supervised Group-Relative Policy Optimization](https://arxiv.org/abs/2602.17025)** — Makes GRPO more rollout-efficient by addressing the problem of extended deliberation creating misleading relative comparisons.

- **[On the Design of KL-Regularized Policy Gradient Algorithms for LLM Reasoning](https://arxiv.org/abs/2505.17508)** — Deep analysis of the design space for KL regularization in policy gradient methods for LLM reasoning (forward vs. reverse KL, normalization, etc.).

- **[Escaping the Cognitive Well: Efficient Competition Math with Off-the-Shelf Models](https://arxiv.org/abs/2602.16793)** — Achieves near-IMO-gold performance using publicly available models at dramatically lower inference cost.

- **[Better Think Thrice: Causal Reasoning with Double Counterfactual Consistency](https://arxiv.org/abs/2602.16787)** — Reveals brittleness of LLMs on counterfactual questions and proposes double counterfactual consistency training.

### Interpretability & Mechanistic Understanding

- **[Quantifying LLM Attention-Head Stability: Implications for Circuit Universality](https://arxiv.org/abs/2602.16740)** — Tests whether mechanistic interpretability "circuits" are stable under perturbation — finding concerning fragility.

- **[The Anxiety of Influence: Bloom Filters in Transformer Attention Heads](https://arxiv.org/abs/2602.17526)** — Identifies attention heads functioning as membership testers ("has this token appeared before?") across GPT-2 and Llama models, analogous to Bloom filters.

- **[On the Existence and Behavior of Secondary Attention Sinks](https://arxiv.org/abs/2512.22213)** — Discovers a class of attention sinks beyond the BOS token — secondary sinks that receive disproportionate attention despite limited relevance.

- **[Formal Mechanistic Interpretability: Automated Circuit Discovery with Provable Guarantees](https://arxiv.org/abs/2602.16823)** — Moves beyond heuristic circuit discovery to methods with formal provable guarantees.

- **[A Residual-Aware Theory of Position Bias in Transformers](https://arxiv.org/abs/2602.16837)** — Explains the architectural origins of position bias in transformers, where prior theory predicted inevitable bias toward initial tokens.

- **[Mechanistic Interpretability of Cognitive Complexity in LLMs via Bloom's Taxonomy](https://arxiv.org/abs/2602.17229)** — Uses linear probing to map LLM internal representations to Bloom's Taxonomy cognitive levels.

- **[Biases in the Blind Spot: Detecting What LLMs Fail to Mention](https://arxiv.org/abs/2602.10117)** — Identifies "unverbalized biases" hidden in chain-of-thought reasoning — biases the model acts on but never states.

- **[Understanding LLM Failures: A Multi-Tape Turing Machine Analysis](https://arxiv.org/abs/2602.15868)** — Formalizes LLM interaction using a multi-tape Turing machine to explain systematic failure modes on trivial tasks.

### Benchmarks & Evaluation

- **[When AI Benchmarks Plateau: A Systematic Study of Benchmark Saturation](https://arxiv.org/abs/2602.16763)** — Comprehensive study of how quickly AI benchmarks saturate and can no longer differentiate between top models.

- **[RFEval: Benchmarking Reasoning Faithfulness under Counterfactual Intervention](https://arxiv.org/abs/2602.17053)** — Framework for evaluating whether LLM rationales actually reflect the model's true decision process.

- **[DeepVision-103K: Multimodal Reasoning Dataset](https://arxiv.org/abs/2602.16742)** — 103K visually diverse, verifiable math problems for training multimodal models with reinforcement learning from verifiable rewards.

- **[AI Gamestore: Scalable Evaluation of Machine General Intelligence](https://arxiv.org/abs/2602.17594)** — Uses human games as an open-ended, scalable benchmark for machine general intelligence, going beyond narrow benchmarks.

- **[When to Trust the Cheap Check: Weak and Strong Verification for Reasoning](https://arxiv.org/abs/2602.17633)** — Framework for deciding when cheap verification (self-consistency, proxy rewards) suffices vs. when strong external verification is needed.

### Applied AI & Models

- **[Arcee Trinity Large Technical Report](https://arxiv.org/abs/2602.17004)** — Technical report for a sparse MoE model with 400B total parameters (13B activated per token), plus smaller Trinity Nano and Mini variants.

- **[Adam Improves Muon: Adaptive Moment Estimation with Orthogonalized Momentum](https://arxiv.org/abs/2602.17080)** — Combines Adam's adaptive moment estimation with Muon's orthogonalized momentum for improved optimization.

- **[Predictive Batch Scheduling: Accelerating LM Training via Loss-Aware Prioritization](https://arxiv.org/abs/2602.17066)** — Dynamically prioritizes high-loss samples during batch construction to accelerate language model convergence.

- **[One-step Language Modeling via Continuous Denoising](https://arxiv.org/abs/2602.16813)** — Addresses the quality degradation of discrete diffusion language models in the few-step regime.

- **[Phase-Aware Mixture of Experts for Agentic RL](https://arxiv.org/abs/2602.17038)** — Uses phase-aware MoE to prevent simplicity bias where easy tasks dominate parameters in single-policy RL for agents.

- **[Efficient RL for LLMs with Intrinsic Exploration](https://arxiv.org/abs/2511.00794)** — Reduces wasted computation in RLVR training by using intrinsic exploration to generate more informative rollouts.

- **[Proof-RM: A Scalable Reward Model for Math Proof](https://arxiv.org/abs/2602.02377)** — Tackles reward modeling for proof-based math problems where correctness can't be verified by simple answer matching.

### Human-AI Interaction

- **[MedClarify: Information-seeking AI Agent for Medical Diagnosis](https://arxiv.org/abs/2602.17308)** — AI agent that asks case-specific follow-up questions rather than attempting immediate diagnosis from incomplete information.

- **[Capturing Individual Human Preferences with Reward Features](https://arxiv.org/abs/2503.17338)** — Argues that single reward functions in RLHF are insufficient; proposes reward features to capture individual preference differences.

- **[Large Language Models Persuade Without Planning Theory of Mind](https://arxiv.org/abs/2602.17045)** — Demonstrates that LLMs can be persuasive without actually modeling the other person's mental state — raising questions about ToM evaluations.

- **[HiVAE: Hierarchical Latent Variables for Scalable Theory of Mind](https://arxiv.org/abs/2602.16826)** — Scales theory of mind from small gridworlds to larger environments using hierarchical variational architecture.

- **[Discovering Multiagent Learning Algorithms with LLMs](https://arxiv.org/abs/2602.16928)** — Uses LLMs to discover new multi-agent RL algorithms, moving beyond manual iterative refinement of baselines.

---

## Key Themes

1. **Agent safety is the new frontier** — This week saw an explosion of papers on agent security: hijacking via template injection, the gap between text and tool-call safety, stateful adversarial detection, and fundamental limits of black-box evaluation. The Cline CLI supply chain attack and Amazon's Kiro outage show these aren't just theoretical concerns.

2. **Reasoning efficiency matters as much as reasoning capability** — Multiple papers tackle the cost of test-time compute: entropy-based early exiting, speculative drafts, progressive thought encoding, and efficient GRPO. The field is shifting from "can models reason?" to "can they reason affordably?"

3. **Mechanistic interpretability is maturing** — Formal circuit discovery with provable guarantees, Bloom filter analogies in attention heads, secondary attention sinks, and position bias theory show the field moving from ad-hoc probing to rigorous understanding.

4. **India as the next AI compute frontier** — G42/Cerebras (8 exaflops), General Catalyst ($5B), Peak XV ($1.3B), Nvidia ecosystem push, and 50% of ChatGPT India usage from 18–24 year olds paint a picture of massive AI investment and adoption in India.

5. **The alignment design space is wide open** — Papers on fail-closed vs. fail-open alignment, KL regularization design choices, adaptive safety regularization during fine-tuning, and individual preference modeling show alignment is far from a solved problem.

6. **Benchmarks need benchmarking** — Saturation studies, faithfulness evaluation under counterfactual intervention, and the distinction between weak and strong verification suggest the field is reckoning with whether current evaluation methods actually measure what matters.

---

*Generated from 501 articles collected on February 20, 2026.*
