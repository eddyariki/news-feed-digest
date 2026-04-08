# AI News Digest — April 8, 2026

## Highlights

- **[Anthropic's Project Glasswing AI Found Vulnerabilities in Every Major OS and Browser](https://www.theverge.com/ai-artificial-intelligence/908114/anthropic-project-glasswing-cybersecurity)**: Anthropic debuted a specialized cybersecurity model ("Mythos") that autonomously identified security flaws across operating systems and browsers as part of a defensive partnership with Nvidia, Google, AWS, Apple, and Microsoft.
- **[Flowise LLM Platform Hit by CVSS 10.0 RCE Zero-Day, 12,000+ Instances Exposed](https://thehackernews.com/2026/04/flowise-ai-agent-builder-under-active.html)**: Attackers are actively exploiting a maximum-severity code-injection flaw in Flowise, a popular open-source LLM/agent builder, with over 12,000 internet-exposed instances at risk.
- **[APT28's FrostArmada Router Hijacking Campaign Disrupted by International Operation](https://www.bleepingcomputer.com/news/security/authorities-disrupt-dns-hijacks-used-to-steal-microsoft-365-logins/)**: Law enforcement and private partners dismantled a Russian GRU-linked campaign that hijacked MikroTik and TP-Link routers on 18,000+ networks to silently steal Microsoft 365 credentials.
- **[Anthropic Hits $30B Run-Rate Revenue, Signs Multi-Gigawatt TPU Deal](https://techcrunch.com/2026/04/07/anthropic-compute-deal-google-broadcom-tpus/)**: As demand surges, Anthropic expanded its compute agreement with Google and Broadcom for multiple gigawatts of TPU capacity coming online from 2027.
- **[Intel Signs On to Elon Musk's Terafab AI Chip Factory in Texas](https://www.theverge.com/transportation/907976/elon-musk-terafab-intel-ai-chip-spacex-tesla)**: Intel joined SpaceX and Tesla to help design and build the Terafab semiconductor facility in Austin, which would supply AI chips for Musk's companies.

---

## News

### AI Security

- **[Anthropic Debuts Mythos / Project Glasswing](https://techcrunch.com/2026/04/07/anthropic-mythos-ai-model-preview-security/)**: A new Anthropic model for defensive cybersecurity will be deployed by a small group of high-profile companies and government entities to flag vulnerabilities with minimal human intervention.
- **[Grafana Patches AI Bug That Could Have Leaked User Data](https://www.darkreading.com/application-security/grafana-patches-ai-bug-leaked-user-data)**: Hidden malicious instructions on an attacker-controlled page could cause the AI to return sensitive data to an external server — a prompt-injection attack in a production monitoring tool.
- **[Max Severity Flowise RCE Now Exploited in Attacks](https://www.bleepingcomputer.com/news/security/max-severity-flowise-rce-vulnerability-now-exploited-in-attacks/)**: CVE-2025-59528 (CVSS 10.0) in the Flowise CustomMCP node allows arbitrary code execution; active exploitation is confirmed across thousands of exposed instances.
- **[ComfyUI Instances Targeted in Cryptomining Botnet Campaign](https://thehackernews.com/2026/04/over-1000-exposed-comfyui-instances.html)**: A purpose-built Python scanner sweeps cloud IP ranges for exposed ComfyUI stable diffusion servers and installs malicious nodes via ComfyUI-Manager.
- **[Cybersecurity in the Age of Instant Software](https://www.schneier.com/blog/archives/2026/04/cybersecurity-in-the-age-of-instant-software.html)**: Bruce Schneier examines how AI-generated ephemeral software will reshape the attack surface and vulnerability patching cycle.
- **[RSAC 2026: AI Is Reshaping Cybersecurity Faster Than Ever](https://www.darkreading.com/cybersecurity-operations/rsac-2026-how-ai-is-reshaping-cybersecurity-faster-than-ever)**: Dark Reading recaps RSAC 2026 — AI dominated the conference, with CISOs debating agentic security tools and the limits of human oversight.
- **[Human vs AI Debates Shape RSAC 2026](https://www.darkreading.com/cybersecurity-operations/human-vs-ai-debates-shape-rsac-2026-cybersecurity-trends)**: Industry leaders debated how much to trust AI decision-making in security operations and whether humans can keep pace with AI-assisted attacks.
- **[Docker CVE-2026-34040 Lets Attackers Bypass Authorization and Gain Host Access](https://thehackernews.com/2026/04/docker-cve-2026-34040-lets-attackers.html)**: A high-severity (CVSS 8.8) incomplete fix resurfaces in Docker Engine, allowing AuthZ plugin bypass and potential host compromise.

### USA

- **[Intel Joins Elon Musk's Terafab AI Chip Factory](https://techcrunch.com/2026/04/07/intel-signs-on-to-elon-musks-terafab-chips-project/)**: Intel will help design and build the Texas facility alongside SpaceX and Tesla to produce AI chips domestically.
- **[Anthropic Ups Compute Deal with Google and Broadcom](https://techcrunch.com/2026/04/07/anthropic-compute-deal-google-broadcom-tpus/)**: With run-rate revenue surging to $30B, Anthropic locked in multi-gigawatt TPU capacity starting 2027.
- **[OpenAI, Anthropic, and Google Team Up Against Chinese Model Copying](https://the-decoder.com/openai-anthropic-and-google-team-up-against-unauthorized-chinese-model-copying/)**: The three AI giants are sharing intelligence to combat adversarial distillation — unauthorized reproduction of their models' capabilities by Chinese competitors.
- **[Arcee: The Tiny Open Source LLM Maker Gaining Traction](https://techcrunch.com/2026/04/07/i-cant-help-rooting-for-tiny-open-source-ai-model-maker-arcee/)**: A 26-person U.S. startup built a high-performing large open-source LLM that is gaining popularity with Claude-compatible tooling.
- **[Firmus AI Data Center Builder Hits $5.5B Valuation](https://techcrunch.com/2026/04/07/firmus-the-southgate-ai-datacenter-builder-backed-by-nvidia-hits-5-5b-valuation/)**: The Nvidia-backed Asia-focused AI data center provider raised $1.35B in six months.
- **[Uber Expands AWS Contract for Amazon AI Chips](https://techcrunch.com/2026/04/07/uber-is-the-latest-to-be-won-over-by-amazons-ai-chips/)**: Uber is running more ride-sharing features on Amazon's in-house AI silicon, signaling broader enterprise adoption of AWS Trainium/Inferentia.
- **[Meta Plans to Open-Source Parts of Its New AI Models](https://the-decoder.com/meta-plans-to-open-source-parts-of-its-new-ai-models/)**: Meta is preparing open-source releases of select model variants from its upcoming generation.
- **[Bezos' Project Prometheus Hires xAI Co-Founder](https://the-decoder.com/bezos-project-prometheus-hires-xai-co-founder-from-openai/)**: Jeff Bezos' stealth AI startup added Kyle Kosic, formerly of xAI and OpenAI, as a key hire.
- **[Google AI Overviews Are Correct 9 Out of 10 Times, Study Finds](https://the-decoder.com/googles-ai-overviews-are-correct-nine-out-of-ten-times-study-finds/)**: The first systematic accuracy study of Google's AI-generated search summaries found a ~90% correctness rate, though error patterns remain understudied.
- **[Microsoft Bing Open-Sources "Harrier" Multilingual Embedding Model](https://the-decoder.com/microsofts-bing-team-open-sources-harrier-embedding-model/)**: Harrier tops the multilingual MTEB v2 benchmark across 100+ languages.
- **[FBI: Americans Lost Record $21 Billion to Cybercrime Last Year](https://www.bleepingcomputer.com/news/security/fbi-americans-lost-a-record-21-billion-to-cybercrime-last-year/)**: Investment scams, BEC, and data breaches drove the record figure from the IC3 annual report.
- **[The AI Gold Rush Is Pulling Private Wealth Into Earlier, Riskier Bets](https://techcrunch.com/2026/04/07/the-ai-gold-rush-is-pulling-private-wealth-into-riskier-earlier-bets/)**: Family offices are bypassing VCs to invest directly in early-stage AI startups as valuations continue to climb.

### Europe

- **[Russia Hacked Routers to Steal Microsoft Office Tokens (APT28)](https://krebsonsecurity.com/2026/04/russia-hacked-routers-to-steal-microsoft-office-tokens/)**: APT28 (Forest Blizzard) exploited known flaws in MikroTik and TP-Link routers on 18,000+ networks to harvest authentication tokens without deploying malware.
- **[APT28 FrostArmada DNS Hijacking Campaign Disrupted](https://www.bleepingcomputer.com/news/security/authorities-disrupt-dns-hijacks-used-to-steal-microsoft-365-logins/)**: An international law enforcement operation dismantled the router-based infrastructure used to redirect Microsoft 365 login traffic.
- **[Storm-1175 Deploys Medusa Ransomware at "High Velocity"](https://www.darkreading.com/threat-intelligence/storm-1175-medusa-ransomware-high-velocity)**: Microsoft linked this China-based financially motivated group to rapid exploitation of zero-days and N-day vulnerabilities to deploy Medusa ransomware at scale.

### Japan (AI & Tech)

- **[China Rolls Out AI in K-12 Schools to Ease Teacher Load and Improve Rural Education](https://gigazine.net/news/20260408-china-ai-education/)**: The Chinese government is pushing AI into primary and middle schools to reduce teacher burden and support students with disabilities, with media coverage via ChinaTalk.
- **[TOPPAN Develops AI-OCR for Medieval Greek Manuscripts Using Kuzushiji Recognition](https://www.itmedia.co.jp/news/articles/2604/07/news124.html)**: TOPPAN Group transferred its Japanese cursive character recognition AI to decode Vatican Library manuscripts, targeting 95%+ recognition accuracy.
- **[Sakana AI Builds SNS Misinformation Detection Tech for Japan's Ministry of Finance](https://www.itmedia.co.jp/aiplus/articles/2604/07/news117.html)**: The Tokyo-based AI lab developed a system for visualizing, fact-checking, and simulating suppression of misinformation spread on social networks.
- **[Google Gemma 4 Now Runs Locally on iPhone via AI Edge Gallery](https://gigazine.net/news/20260407-google-gemma-4-on-ios/)**: Google's open-source Gemma 4 model is available on iOS through the official AI Edge Gallery app for free on-device inference.
- **[OpenAI, Anthropic, Google Cooperating to Counter Adversarial Distillation by Chinese AI Firms](https://gigazine.net/news/20260407-openai-anthropic-google-adversarial-distillation/)**: The three labs are sharing information on adversarial distillation attacks — extraction of model capabilities in violation of terms of service.
- **[Japan Focuses on "Physical AI" — Robots and Autonomous Vehicles — to Sustain Economy Amid Labor Shortage](https://gigazine.net/news/20260407-japan-physical-ai-robots-sustain-economy/)**: TechCrunch reports a hybrid model of startups and large firms is emerging in Japan around AI-powered robotics.
- **[HackerOne Pauses Internet Bug Bounty Program — AI Found Too Many Bugs](https://gigazine.net/news/20260407-hackerone-internet-bug-bounty-program-pause/)**: HackerOne suspended new submissions to its IBB program after AI tools dramatically accelerated both the speed and volume of bug discovery.

---

## Research Papers

### Benchmarks & Evaluation

- **[Position: Science of AI Evaluation Requires Item-Level Benchmark Data](https://arxiv.org/abs/2604.03244)** (Jiang et al.): Argues that current benchmark paradigms have systemic validity failures and that item-level diagnostic analysis is essential for trustworthy AI deployment decisions in high-stakes domains.
- **[TableVision: A Large-Scale Benchmark for Spatially Grounded Reasoning over Complex Hierarchical Tables](https://arxiv.org/abs/2604.03660)** (Chen et al.): Identifies a "Perception Bottleneck" in MLLMs for complex hierarchical tables in finance, healthcare, and science, and introduces a benchmark to measure it.
- **[FeynmanBench: Benchmarking Multimodal LLMs on Diagrammatic Physics Reasoning](https://arxiv.org/abs/2604.03893)** (Wang et al.): First benchmark centered on Feynman diagram tasks, testing whether MLLMs can follow the global structural logic of formal scientific notation rather than just local extraction.
- **[TimeSeek: Temporal Reliability of Agentic Forecasters](https://arxiv.org/abs/2604.04220)** (Mostafa et al.): Evaluates 10 frontier models on 150 regulated prediction markets at five temporal checkpoints — finds models are most competitive early in a market's lifecycle and weakest near resolution.
- **[VERT: Reliable LLM Judges for Radiology Report Evaluation](https://arxiv.org/abs/2604.03376)** (Bologna et al.): Conducts a thorough correlation analysis between expert and LLM-based radiology metrics across modalities, identifying which model/prompt configurations are robust judges.
- **[Structured Multi-Criteria Evaluation of LLMs with Fuzzy AHP and DualJudge](https://arxiv.org/abs/2604.03742)** (He et al.): Adapts the Analytic Hierarchy Process to LLM evaluation, adding fuzzy uncertainty modeling via triangular numbers to make LLM judging more transparent and consistent.

### Security & Adversarial

- **[When Do Hallucinations Arise? A Graph Perspective on Path Reuse and Path Compression](https://arxiv.org/abs/2604.03557)** (Dai et al.): Models next-token prediction as graph search and identifies "path compression" in token-entity graphs as a mechanistic source of hallucinations in decoder-only transformers.
- **[Don't Blink: Evidence Collapse during Multimodal Reasoning](https://arxiv.org/abs/2604.04207)** (Raghu & Pandey): Finds that reasoning VLMs lose visual grounding progressively during chain-of-thought — creating confident but ungrounded outputs that text-only monitoring cannot detect.
- **[Selective Forgetting for Large Reasoning Models](https://arxiv.org/abs/2604.03571)** (Le et al.): Addresses privacy and copyright risks in LRMs whose chain-of-thought exposes training data; proposes machine unlearning methods targeted at intermediate reasoning steps.
- **[CoALFake: Collaborative Active Learning with Human-LLM Co-Annotation for Cross-Domain Fake News Detection](https://arxiv.org/abs/2604.04174)** (Aïmeur et al.): Tackles cross-domain fake news detection with an active learning framework that combines human annotators and LLMs to generalize across domains without labelled data.

### Compliance & Regulation

- **[Automated Analysis of Global AI Safety Initiatives: A Taxonomy-Driven LLM Approach](https://arxiv.org/abs/2604.03533)** (Semitsu et al.): Presents an automated crosswalk framework using the Activity Map on AI Safety taxonomy to compare and score AI safety policy documents across nations.
- **[Compliance-by-Construction Argument Graphs for Certification-Grade Accountability](https://arxiv.org/abs/2604.04103)** (Moghaddam): Proposes using generative AI to produce formal argument structures that link safety claims to evidence in a verifiable manner, suitable for regulatory certification of high-stakes AI systems.
- **[Quantifying Trust: Financial Risk Management for Trustworthy AI Agents](https://arxiv.org/abs/2604.03976)** (Hua et al.): Reframes AI trust from model-internal properties (bias, robustness) to end-to-end operational outcomes — task completion, intent alignment, and harm avoidance — especially for agents connected to financial assets.

### Alignment & Safety

- **[Implementing Surrogate Goals for Safer Bargaining in LLM-based Agents](https://arxiv.org/abs/2604.04341)** (Oesterheld et al.): Proposes and tests surrogate goal strategies that deflect threats in multi-agent bargaining scenarios away from what principals care about, reducing manipulation risk.
- **[Pedagogical Safety in Educational Reinforcement Learning: Formalizing and Detecting Reward Hacking in AI Tutoring Systems](https://arxiv.org/abs/2604.04237)** (Olukola & Rahimi): Introduces a four-layer pedagogical safety model and a Reward Hacking Severity Index (RHSI) to detect when RL tutors optimize proxy metrics at the expense of genuine learning outcomes.
- **[Evaluating Artificial Intelligence Through a Christian Understanding of Human Flourishing](https://arxiv.org/abs/2604.03356)** (Skytland et al.): Argues AI alignment is fundamentally a "formation" problem — LLMs function as instruments of digital catechesis shaping moral reasoning — and proposes metrics grounded in human flourishing frameworks.

### Applications

- **[ActionNex: A Virtual Outage Manager for Cloud](https://arxiv.org/abs/2604.03512)** (Lin et al.): Production-grade agentic system for cloud outage management that provides real-time triage, cross-team coordination, and role-conditioned next-best-action recommendations in large-scale operations.
- **[Toward Full Autonomous Laboratory Instrumentation Control with LLMs](https://arxiv.org/abs/2604.03286)** (Xie et al.): Demonstrates LLM-based agents enabling non-programmers to automate complex scientific equipment, lowering the barrier for computational laboratory science.
- **[A Multimodal Foundation Model of Spatial Transcriptomics and Histology for Biological Discovery and Clinical Prediction](https://arxiv.org/abs/2604.03630)** (Xiang et al.): STORM, a foundation model trained on 1.2M spatially resolved transcriptomic profiles with matched histology, enables gene expression prediction from standard H&E staining.
- **[BioAlchemy: Distilling Biological Literature into Reasoning-Ready RL Training Data](https://arxiv.org/abs/2604.03506)** (Hsu et al.): Shows current reasoning datasets underrepresent modern biology research topics and introduces a pipeline to extract verifiable biology training problems aligned with the research frontier.

### Guardrails & Robustness

- **[Beyond Fluency: Toward Reliable Trajectories in Agentic IR](https://arxiv.org/abs/2604.04269)** (Sinha et al.): Catalogs failure modes in industrial agentic information retrieval systems where minor early errors cascade into functional misalignment despite continued linguistic fluency.
- **[Explainable Model Routing for Agentic Workflows](https://arxiv.org/abs/2604.03527)** (Okamoto et al.): Proposes routing architectures that record and expose trade-offs between cost and capability, enabling developers to audit and understand intelligent routing decisions in multi-model pipelines.
- **[Entropy and Attention Dynamics in Small Language Models on TruthfulQA](https://arxiv.org/abs/2604.03589)** (Adeseye et al.): Analyzes how attention entropy evolves during inference in SLMs, finding that confident mispredictions correlate with specific attention instability patterns — enabling pre-output safety checks.

---

## Key Themes

- **AI as an offensive and defensive security force**: Anthropic's Mythos/Glasswing finding OS/browser vulnerabilities, Flowise CVSS 10.0 RCE actively exploited, and ComfyUI targeted for cryptomining illustrate AI infrastructure increasingly becoming both a tool and a target.
- **Nation-state cyber operations intensifying**: APT28's router-based FrostArmada campaign and China-linked Storm-1175's high-velocity ransomware deployment reflect sustained state-actor activity against Western infrastructure.
- **AI supply chain competition**: The OpenAI/Anthropic/Google coalition against Chinese adversarial distillation, plus Intel's Terafab commitment, underline semiconductor and model supply-chain sovereignty as a strategic priority.
- **Compute race accelerating**: Anthropic's $30B run-rate and multi-gigawatt TPU deal with Google/Broadcom signal that frontier AI development is entering a new capital intensity tier.
- **Evaluation rigor as a safety prerequisite**: Multiple papers argue that current benchmarks have systemic validity gaps — item-level diagnostics, temporal reliability, and multimodal grounding failures all point to evaluation methodology as a core safety bottleneck.
- **Japan investing in physical AI and misinformation defense**: Japan's labor-shortage-driven push into robots and autonomous systems contrasts with Sakana AI's government-backed SNS misinformation detection work — both reflect strategic AI priorities at the national level.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
