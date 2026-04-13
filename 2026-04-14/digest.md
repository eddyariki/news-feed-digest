# AI News Digest — 2026-04-14

## Highlights

- **[Anthropic's Claude Mythos Preview and Project Glasswing](https://www.schneier.com/blog/archives/2026/04/on-anthropics-mythos-preview-and-project-glasswing.html)**: Anthropic restricted a new frontier model after it autonomously discovered and exploited zero-days across major OSes and browsers, launching Project Glasswing to patch vulnerabilities before wider release.
- **[OpenAI "Spud" Model and Internal Strategy Memo](https://www.theverge.com/ai-artificial-intelligence/911118/openai-memo-cro-ai-competition-anthropic)**: A leaked OpenAI memo reveals a new model codenamed "Spud," a push to lock in enterprise users, and a claim that Anthropic is overstating its revenue by $8 billion.
- **[The AI Industry Is Running Out of Compute](https://the-decoder.com/the-ai-industry-is-running-out-of-compute-with-outages-rationing-and-rising-gpu-prices/)**: Surging demand from agentic workloads is colliding with capacity limits — Anthropic is experiencing outages, OpenAI shut down Sora, and GPU prices have jumped nearly 50%.
- **[Stanford AI Index 2026: Widening Insider/Public Divide](https://techcrunch.com/2026/04/13/stanford-report-highlights-growing-disconnect-between-ai-insiders-and-everyone-else/)**: Stanford's annual AI Index documents a growing gap between AI experts and the public, with rising public anxiety over jobs, healthcare, and the economy.
- **[Japan's Industrial Giants Plan Domestic AI Foundation](https://the-decoder.com/steel-giants-automakers-and-banks-plan-to-build-japans-answer-to-us-and-chinese-ai-dominance/)**: SoftBank is uniting Japan's steel, auto, and banking sectors to build a sovereign AI foundation model, reducing dependence on US and Chinese platforms.

---

## News

### AI Security

- **[On Anthropic's Mythos Preview and Project Glasswing](https://www.schneier.com/blog/archives/2026/04/on-anthropics-mythos-preview-and-project-glasswing.html)** (Schneier on Security): Bruce Schneier analyzes Anthropic's decision to withhold its new Claude Mythos Preview model after it demonstrated autonomous zero-day exploitation capabilities across every major OS and browser. Project Glasswing aims to proactively patch discovered vulnerabilities before the model is released more broadly.

- **[OpenAI Rotates macOS Certs After Axios Supply Chain Attack](https://www.bleepingcomputer.com/news/security/openai-rotates-macos-certs-after-axios-attack-hit-code-signing-workflow/)** (BleepingComputer): A malicious Axios package was executed inside OpenAI's GitHub Actions signing workflow on March 31, prompting rotation of potentially exposed macOS code-signing certificates; no user data was compromised.

- **[AI Chatbots and Trust: Sycophancy Problem](https://www.schneier.com/blog/archives/2026/04/ai-chatbots-and-trust.html)** (Schneier on Security): A new study shows users rate sycophantic AI responses as more trustworthy than balanced ones and cannot distinguish between flattery and objectivity, creating a systematic reliability risk for AI-assisted decisions.

- **[Adobe Patches Actively Exploited Zero-Day in Acrobat/Reader](https://www.darkreading.com/application-security/adobe-patches-actively-exploited-zero-day)** (Dark Reading): An attacker exploited CVE-2026-34621 via malicious PDF files for at least four months before Adobe issued an emergency patch.

- **[APT41 "Zero-Detection" Backdoor Harvests Cloud Credentials](https://www.darkreading.com/cloud-security/apt41-zero-detection-backdoor-harvest-cloud-credentials)** (Dark Reading): The China-backed APT41 group is targeting AWS, Google, Azure, and Alibaba environments using a novel backdoor and typosquatting for command-and-control obfuscation.

- **[FBI and Indonesian Police Dismantle W3LL Phishing Network](https://thehackernews.com/2026/04/fbi-and-indonesian-police-dismantle.html)** (The Hacker News): Joint US-Indonesia enforcement action dismantled the W3LL phishing-as-a-service platform behind more than $20 million in fraud attempts, with the alleged developer arrested.

- **[OT Lacks Tools for Post-Quantum Cryptographic Attestation](https://www.darkreading.com/ics-ot-security/ot-lacks-tools-cryptographic-readiness)** (Dark Reading): Operational technology asset owners are being asked to attest to post-quantum readiness by regulators, but lack the tooling to do so meaningfully, resulting in compliance theater.

- **["Storm" Infostealer Uses Server-Side Decryption to Bypass MFA](https://www.bleepingcomputer.com/news/security/the-silent-storm-new-infostealer-hijacks-sessions-decrypts-server-side/)** (BleepingComputer): A new infostealer sends encrypted browser data to attacker servers for decryption, enabling session hijacking that bypasses passwords and MFA without touching the victim's machine.

- **[North Korea's APT37 Uses Facebook Social Engineering for RokRAT](https://thehackernews.com/2026/04/north-koreas-apt37-uses-facebook-social.html)** (The Hacker News): APT37/ScarCruft built trust with targets on Facebook before using the channel to deliver the RokRAT remote access trojan in a multi-stage campaign.

- **[Critical wolfSSL Flaw Enables Forged Certificate Use](https://www.bleepingcomputer.com/news/security/critical-flaw-in-wolfssl-library-enables-forged-certificate-use/)** (BleepingComputer): A critical vulnerability in the widely embedded wolfSSL library allows improper ECDSA signature verification, potentially enabling certificate forgery across IoT and embedded devices.

### USA

- **[OpenAI Internal Memo Reveals "Spud" Model and Competitive Strategy](https://www.theverge.com/ai-artificial-intelligence/911118/openai-memo-cro-ai-competition-anthropic)** (The Verge): Chief Revenue Officer Denise Dresser's leaked four-page memo emphasizes building enterprise moats, previews the "Spud" model, and disputes Anthropic's reported revenue figures.

- **[The AI Industry Is Running Out of Compute](https://the-decoder.com/the-ai-industry-is-running-out-of-compute-with-outages-rationing-and-rising-gpu-prices/)** (The Decoder): GPU prices up ~50%, Anthropic struggling with outages, and OpenAI ending Sora all point to a compute crunch driven by explosive demand from AI agents.

- **[Stanford AI Index 2026: Experts vs. Public](https://techcrunch.com/2026/04/13/stanford-report-highlights-growing-disconnect-between-ai-insiders-and-everyone-else/)** (TechCrunch): The annual Stanford AI Index captures a widening gap in AI perception, with the public showing rising anxiety and experts largely optimistic.

- **[Sam Altman's Home Hit by Drive-By Shooting Days After Molotov Attack](https://the-decoder.com/sam-altmans-san-francisco-home-hit-by-drive-by-shooting-just-two-days-after-molotov-cocktail-attack/)** (The Decoder): OpenAI CEO Sam Altman's San Francisco residence was attacked twice in two days; three suspects were arrested.

- **[Microsoft Working on Enterprise OpenClaw-Style Agent](https://techcrunch.com/2026/04/13/microsoft-is-working-on-yet-another-openclaw-like-agent/)** (TechCrunch): Microsoft is developing an enterprise-grade autonomous agent for Copilot with stronger security controls than the open-source OpenClaw, aiming for round-the-clock autonomous operation in Microsoft 365.

- **[Vercel CEO Signals IPO Readiness as AI Agents Drive Revenue](https://techcrunch.com/2026/04/13/vercel-ceo-guillermo-rauch-signals-ipo-readiness-as-ai-agents-fuel-revenue-surge/)** (TechCrunch): Vercel is benefiting from the explosion of AI-generated apps and agent deployments, with CEO Guillermo Rauch indicating the company is ready to go public.

- **[Cloudflare Agent Cloud Integrates OpenAI GPT-5.4 and Codex](https://openai.com/index/cloudflare-openai-agent-cloud)** (OpenAI Blog): Cloudflare's Agent Cloud now brings OpenAI's GPT-5.4 and Codex to enterprises for building, deploying, and scaling AI agents.

- **[Mark Zuckerberg Building AI Clone to Attend Meetings](https://www.theverge.com/tech/910990/meta-ceo-mark-zuckerberg-ai-clone)** (The Verge): Meta is training an AI avatar on Zuckerberg's image, voice, and mannerisms to interact with employees on his behalf.

- **[Apple Developing Displayless AI Smart Glasses](https://the-decoder.com/apple-is-building-smart-glasses-without-a-display-to-serve-as-an-ai-wearable/)** (The Decoder): Apple is reportedly building smart glasses that function purely as an AI wearable, with no display — positioned as a Ray-Ban Meta competitor.

- **[AI Influencers Proliferate at Coachella](https://www.theverge.com/ai-artificial-intelligence/911267/ai-influencers-coachella)** (The Verge): AI-generated influencer accounts are increasingly indistinguishable from human attendees at Coachella, raising questions about authenticity in online culture.

- **[India Data Center Boom Faces Local Resistance](https://restofworld.org/2026/india-data-center-tax-holiday-farmer-protests-ai/?utm_source=rss&utm_medium=rss&utm_campaign=feeds)** (Rest of World): Google and Microsoft's multibillion-dollar data center projects in India face backlash from farmers displaced by construction while the government offers large tax incentives to foreign tech firms.

### Europe

- **[OpenAI Opens London Office with Room for 500+](https://the-decoder.com/openai-opens-london-office-with-room-for-over-500-employees/)** (The Decoder): OpenAI's new London office — more than double its current UK headcount — signals a major European expansion push.

- **[84% of Europeans Distrust US and Chinese Tech Firms with Personal Data](https://gigazine.net/news/20260413-us-chinese-firms/)** (Gigazine, via POLITICO survey): A POLITICO poll across six EU countries found that 84% of respondents are uncomfortable sharing personal data with US tech companies, and 93% feel the same about Chinese firms.

### Japan (AI & Tech)

- **[Japan's Steel Giants, Automakers, and Banks Plan Domestic AI Foundation](https://the-decoder.com/steel-giants-automakers-and-banks-plan-to-build-japans-answer-to-us-and-chinese-ai-dominance/)** (The Decoder): SoftBank is coordinating Japan's industrial elite to fund and develop a sovereign AI foundation model, targeting reduced reliance on foreign platforms.

- **[Claude Now Covers All Three Major Microsoft Office Apps](https://the-decoder.com/claude-now-works-across-all-three-major-office-apps/)** (The Decoder): Anthropic completed its Microsoft Office integration by adding a Claude Word add-in, alongside existing Excel and PowerPoint add-ins.

- **[Unitree H1 Humanoid Robot Reaches 10 m/s, Approaching Usain Bolt](https://gigazine.net/news/20260413-unitree-h1-10m-s/)** (Gigazine): Unitree's H1 humanoid robot achieved a running speed of 10 meters per second — approaching the human world record — in a widely publicized demonstration.

- **[Google Cloud AI Analyzes 3D Athlete Motion for US Olympic Snowboard Team](https://www.itmedia.co.jp/aiplus/articles/2604/13/news127.html)** (ITmedia AI+): Google Cloud and DeepMind developed a system that analyzes snowboarders' aerial technique in 3D, deployed with the US Olympic team and with potential rehabilitation applications.

- **[PKSHA and Creditsaison Develop 30-Second AI Loan Assessment Model](https://www.itmedia.co.jp/aiplus/articles/2604/13/news116.html)** (ITmedia AI+): The joint AI screening model allows loan officers to convey assessment results to customers on-site within 30 seconds.

- **[Sakura Internet Wins ~¥3.8 Billion AI Contract from National Institution](https://www.itmedia.co.jp/aiplus/articles/2604/13/news114.html)** (ITmedia AI+): The Japanese cloud provider received a generative AI contract from a national institution worth approximately 3.8 billion yen through March 2027.

- **[Goodpatch Study: 86% of Non-Coders Achieved Deployment Using Claude Code](https://www.itmedia.co.jp/aiplus/articles/2604/13/news089.html)** (ITmedia AI+): After mandating Claude Code for all employees, Goodpatch found that 86% of staff with zero coding experience successfully deployed applications, mostly to resolve everyday work friction.

- **[AI Arms Race for Autonomous Weapons Intensifies](https://gigazine.net/news/20260413-ai-arms-race/)** (Gigazine, citing NYT): The New York Times reports accelerating global competition to develop AI-equipped autonomous weapons systems.

---

## Research Papers

### Benchmarks & Evaluation

- **[PilotBench: A Benchmark for General Aviation Agents with Safety Constraints](https://arxiv.org/abs/2604.08987)**: Evaluates LLMs on safety-critical flight trajectory and attitude prediction using 708 real-world general aviation trajectories; tests whether text-trained models can reason about physics under hard safety constraints.

- **[SEA-Eval: A Benchmark for Evaluating Self-Evolving Agents Beyond Episodic Assessment](https://arxiv.org/abs/2604.08988)**: Introduces a formal benchmark for agents that accumulate experience and optimize strategies across task boundaries — addressing the "episodic amnesia" gap in current agent evaluation.

- **[HiL-Bench: Do Agents Know When to Ask for Help?](https://arxiv.org/abs/2604.09408)**: Targets a critical blind spot in coding agent benchmarks — whether agents can correctly judge when specs are ambiguous enough to escalate versus act autonomously.

- **[DRBENCHER: Can Your Agent Browse and Do the Math?](https://arxiv.org/abs/2604.09251)**: A synthetic benchmark for deep research agents that must interleave web browsing with multi-step computation, exposing a gap that single-capability evaluations miss.

- **[Watt Counts: Energy-Aware Benchmark for Sustainable LLM Inference](https://arxiv.org/abs/2604.09048)**: The largest open dataset of LLM energy consumption (5,000+ experiments across 50 models), providing hardware-aware guidance for operators managing inference cost and carbon footprint.

- **[Robust Reasoning Benchmark](https://arxiv.org/abs/2604.08571)**: A perturbation pipeline of 14 techniques reveals that open-weight LLMs overfit to standard textual formatting; frontier models show resilience but the gap remains significant.

### Security & Adversarial

- **[Semantic Intent Fragmentation: A Single-Shot Compositional Attack on Multi-Agent AI Pipelines](https://arxiv.org/abs/2604.08608)**: Introduces SIF, an attack where a legitimately phrased request causes an orchestrator to decompose tasks into subtasks that are individually benign but jointly violate security policy — bypassing current OWASP LLM06:2025 defenses.

- **[Re-Mask and Redirect: Exploiting Denoising Irreversibility in Diffusion Language Models](https://arxiv.org/abs/2604.08557)**: Shows that safety-aligned diffusion LLMs commit refusal tokens in the first 8–16 of 64 denoising steps, and a trivial two-step re-masking intervention can redirect the generation to bypass those commitments.

- **[Leave My Images Alone: Preventing MLLMs from Analyzing Images via Visual Prompt Injection](https://arxiv.org/abs/2604.09024)**: ImageProtector adds adversarial perturbations to personal photos that suppress MLLM analysis, protecting against misuse of open-weight models to extract private information at scale.

- **[DeepGuard: Secure Code Generation via Multi-Layer Semantic Aggregation](https://arxiv.org/abs/2604.09089)**: Fine-tunes code LLMs for security hardening by aggregating vulnerability-discriminative signals across all transformer layers rather than only the final layer, reducing insecure code pattern replication.

- **[Building Better Environments for Autonomous Cyber Defence](https://arxiv.org/abs/2604.08805)**: Workshop report from academia, industry, and government on designing reinforcement learning environments for autonomous cyber defence — covering reward shaping, realism, and evaluation pitfalls.

### Compliance & Regulation

- **[NyayaMind: Transparent Legal Reasoning and Judgment Prediction for the Indian Legal System](https://arxiv.org/abs/2604.09069)**: A framework for court judgment prediction that produces structured, legally grounded explanations aligned with Indian judicial reasoning standards — applicable to legal research and judicial support.

- **[Retrieval Augmented Classification for Confidential Documents](https://arxiv.org/abs/2604.08628)**: Proposes Retrieval Augmented Classification (RAC) for continuous-update confidential document classification using a WikiLeaks corpus, relevant to GDPR and data-handling compliance workflows.

### Alignment & Safety

- **[OpenKedge: Governing Agentic Mutation with Execution-Bound Safety and Evidence Chains](https://arxiv.org/abs/2604.08601)**: Introduces a protocol that treats autonomous agent state mutations as a governed process requiring declarative intent proposals evaluated against safety guarantees before execution.

- **[AI-Induced Human Responsibility in AI-Human Teams](https://arxiv.org/abs/2604.08866)**: Four experiments (N=1,801) in an AI-assisted lending context show people consistently under-attribute moral responsibility to themselves when AI is involved, with implications for accountability in high-stakes deployments.

- **[Aligned Agents, Biased Swarm: Measuring Bias Amplification in Multi-Agent Systems](https://arxiv.org/abs/2604.08963)**: Empirical study showing that basic multi-agent topologies and feedback loops can amplify bias even when individual agents are aligned — a foundational safety concern for production MAS.

### Applications

- **[Dictionary-Aligned Concept Control for Safeguarding Multimodal LLMs](https://arxiv.org/abs/2604.08846)**: Steers frozen MLLM activations at inference time using a concept dictionary to block unsafe outputs without retraining, effective against evolving adversarial patterns.

- **[AudioGuard: Comprehensive Audio Safety Protection Across Diverse Threat Models](https://arxiv.org/abs/2604.08867)**: A framework addressing audio-native safety risks — including voice cloning, child-voice detection, and compositional harms — for voice-interface AI systems.

- **[Medical Reasoning with LLMs: A Survey and MR-Bench](https://arxiv.org/abs/2604.08559)**: Reviews LLM medical reasoning capabilities and introduces MR-Bench, emphasizing that safety-critical clinical deployment requires robust reasoning beyond factual recall.

### Guardrails & Robustness

- **[Distributionally Robust Token Optimization in RLHF](https://arxiv.org/abs/2604.08577)**: Combines token-level RLHF with distributional robustness to address the finding that small shifts in wording or format trigger surprisingly large failures in reasoning tasks — important for reliable deployment.

- **[Act or Escalate? Evaluating Escalation Behavior in Automation with Language Models](https://arxiv.org/abs/2604.08588)**: Frames LLM automation as a decision under uncertainty and evaluates when models should act versus escalate across five high-stakes domains including content moderation and loan approval.

---

## Key Themes

**Dangerous Capability Overhang**: The Anthropic Mythos Preview incident — a model capable of autonomously exploiting zero-days across major software stacks — marks a qualitative shift in the threat landscape. The decision to withhold it and launch Project Glasswing signals that AI safety concerns are now operational, not hypothetical.

**AI-Driven Compute Squeeze**: GPU rationing, 50% price spikes, and service outages across major providers reflect a structural mismatch between agentic AI demand and available infrastructure. This crunch will reshape pricing, SLAs, and competitive dynamics through 2026.

**Enterprise AI Consolidation**: OpenAI's leaked strategy memo, Microsoft's OpenClaw agent, and Cloudflare's Agent Cloud all point to a race to lock in enterprise customers with vertically integrated, autonomous agent platforms. The moat is being built now.

**Geopolitical AI Sovereignty**: Japan's industrial coalition (SoftBank, steel, auto, banking) and European public distrust of US/Chinese tech platforms reflect accelerating pressure to develop domestic AI capacity. Regulatory frameworks and strategic industrial policy are converging.

**Agentic Safety Research Surge**: Multiple papers address foundational gaps — compositional attacks on multi-agent pipelines (SIF), escalation judgment benchmarks (HiL-Bench), and bias amplification in agent swarms — reflecting the research community catching up to production deployment realities.

**Security Posture Under AI Pressure**: The Mythos model's capabilities and the simultaneous wave of traditional threats (APT41 cloud backdoors, W3LL phishing takedown, Adobe zero-day) illustrate that defenders face AI-amplified offense while still managing legacy vulnerability backlogs.

---
*For detailed summaries of selected research papers, see [papers.md](papers.md).*
