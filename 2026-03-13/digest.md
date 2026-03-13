# AI News Digest — March 13, 2026

## Highlights

- **[Invisible Unicode Supply-Chain Attack Hits GitHub](https://arstechnica.com/security/2026/03/supply-chain-attack-using-invisible-code-hits-github-and-other-repositories/)**: Attackers are exploiting Unicode characters invisible to human reviewers to inject malicious code into open-source repositories, reviving a largely abandoned technique at serious scale.
- **[Anthropic Drops Million-Token Context Surcharge](https://the-decoder.com/anthropic-drops-the-surcharge-for-million-token-context-windows-making-opus-4-6-and-sonnet-4-6-far-cheaper/)**: Requests exceeding 200K tokens on Claude Opus 4.6 and Sonnet 4.6 no longer carry a price premium, dramatically reducing costs for long-context enterprise use cases.
- **[US Military Considers Using AI to Rank and Recommend Airstrike Targets](https://www.technologyreview.com/2026/03/13/1134278/the-download-defense-official-ai-chatbots-targeting-pentagon-claude-pollute-military-supply-chain/)**: A Defense Department official confirmed generative AI systems may be used to prioritize targets and recommend strike order, while separately the Pentagon's procurement of Claude is under political scrutiny.
- **[ByteDance Routes 36,000 Nvidia Blackwell Chips Through Malaysia](https://the-decoder.com/bytedance-secures-access-to-nvidia-blackwell-cluster-in-malaysia-circumventing-us-export-ban-on-china/)**: TikTok's parent company is standing up a major Blackwell cluster in Malaysia, explicitly circumventing US export controls that block these chips from entering China — even under the Trump administration's recent relaxations.
- **[INTERPOL Operation Synergia III Sinkholes 45,000 Malicious IPs](https://thehackernews.com/2026/03/interpol-dismantles-45000-malicious-ips.html)**: A 72-country law enforcement effort dismantled tens of thousands of servers tied to phishing, malware, and ransomware campaigns, and arrested 94 individuals worldwide.

---

## News

### AI Security

- **[Supply-Chain Attack Using Invisible Unicode Code Hits GitHub](https://arstechnica.com/security/2026/03/supply-chain-attack-using-invisible-code-hits-github-and-other-repositories/)** *(Ars Technica)* — Attackers are embedding Unicode characters invisible to human eyes into source code, compromising GitHub and other repositories without triggering obvious code review flags.

- **[Patch Me If You Can: AI Codemods for Secure-by-Default Android Apps](https://engineering.fb.com/2026/03/13/android/ai-codemods-secure-by-default-android-apps-meta-tech-podcast/)** *(Engineering at Meta)* — Meta details how it uses AI-generated codemods to automatically patch entire classes of security vulnerabilities across millions of lines of Android code at scale.

- **[Most Google Cloud Attacks Now Start With Bug Exploitation](https://www.darkreading.com/cloud-security/google-cloud-attacks-bug-exploitation)** *(Dark Reading)* — AI is enabling attackers to exploit vulnerabilities faster than patching cycles can keep up, making unpatched bugs — not stolen credentials — the leading cause of cloud compromises.

- **[Will AI Save Consumers From Smartphone-Based Phishing?](https://www.darkreading.com/mobile-security/will-ai-save-consumers-smartphone-phishing-attacks)** *(Dark Reading)* — New Omdia research finds sophisticated phishing attacks bypassing on-device protections at troubling frequency, raising questions about whether AI defenses can keep pace.

- **[Fake PoCs and Misunderstood Risks Cause Cisco SD-WAN Chaos](https://www.darkreading.com/vulnerabilities-threats/fake-pocs-risks-cisco-sd-wan)** *(Dark Reading)* — The latest Cisco SD-WAN vulnerabilities have spawned fraudulent proof-of-concept code and widespread misunderstanding of actual risk levels.

- **[Nine CrackArmor Flaws in Linux AppArmor Enable Root Escalation](https://thehackernews.com/2026/03/nine-crackarmor-flaws-in-linux-apparmor.html)** *(The Hacker News)* — Qualys disclosed nine confused-deputy vulnerabilities in the Linux kernel's AppArmor module that allow unprivileged users to escalate to root and escape container isolation.

- **[Google Fixes Two Chrome Zero-Days Exploited in the Wild](https://www.bleepingcomputer.com/news/google/google-fixes-two-new-chrome-zero-days-exploited-in-attacks/)** *(BleepingComputer)* — Emergency patches address high-severity flaws in Skia (out-of-bounds write) and V8 (type confusion) that were both being actively exploited before disclosure.

- **[Storm-2561 Spreads Trojan VPN Clients via SEO Poisoning](https://thehackernews.com/2026/03/storm-2561-spreads-trojan-vpn-clients.html)** *(The Hacker News)* — Microsoft details a credential theft campaign that poisons search results to serve digitally-signed fake VPN clients impersonating Ivanti, Cisco, and Fortinet products.

- **[Meta to Shut Down Instagram End-to-End Encrypted Chat Support](https://thehackernews.com/2026/03/meta-to-shut-down-instagram-end-to-end.html)** *(The Hacker News)* — Instagram's E2EE chat functionality will be discontinued after May 8, 2026, with users advised to download any messages they wish to keep.

- **[Veeam Patches 7 Critical Backup & Replication Flaws (RCE)](https://thehackernews.com/2026/03/veeam-patches-7-critical-backup.html)** *(The Hacker News)* — Multiple CVSS 9.9 flaws allow authenticated domain users to execute arbitrary code on Veeam Backup Servers; patching is urgent given Veeam's history as a ransomware target.

- **[INTERPOL Dismantles 45,000 Malicious IPs, Arrests 94](https://thehackernews.com/2026/03/interpol-dismantles-45000-malicious-ips.html)** *(The Hacker News)* — Operation Synergia III spanned 72 countries and took down infrastructure supporting phishing, malware distribution, and ransomware campaigns.

- **[SocksEscort Proxy Botnet Disrupted, 369,000 IPs Across 163 Countries](https://thehackernews.com/2026/03/authorities-disrupt-socksescort-proxy.html)** *(The Hacker News)* — US DOJ-coordinated action dismantled a criminal residential proxy service that weaponized home and small-business routers for large-scale fraud.

- **[Chinese Hackers Target Southeast Asian Militaries with AppleChris and MemFun Malware](https://thehackernews.com/2026/03/chinese-hackers-target-southeast-asian.html)** *(The Hacker News)* — Palo Alto's Unit 42 attributes a long-running espionage campaign against regional militaries to Chinese state-backed actor CL-STA-1087, active since at least 2020.

- **[Academia and the "AI Brain Drain"](https://www.schneier.com/blog/archives/2026/03/academia-and-the-ai-brain-drain.html)** *(Schneier on Security)* — Big Tech's $380B AI spend in 2025 (projected $650B this year) is hollowing out academic AI research talent, with Meta reportedly offering individual researchers nine-figure packages.

---

### USA

- **[Anthropic Drops Surcharge for Million-Token Context Windows](https://the-decoder.com/anthropic-drops-the-surcharge-for-million-token-context-windows-making-opus-4-6-and-sonnet-4-6-far-cheaper/)** *(The Decoder)* — Claude Opus 4.6 and Sonnet 4.6 requests over 200K tokens no longer incur a 2× price premium, making long-context enterprise workloads significantly more accessible.

- **[US Military Plans to Use Generative AI for Target Ranking](https://www.technologyreview.com/2026/03/13/1134278/the-download-defense-official-ai-chatbots-targeting-pentagon-claude-pollute-military-supply-chain/)** *(MIT Technology Review)* — A DoD official confirmed plans to use AI chatbots to recommend strike priorities; separately, the Pentagon's use of Claude faces political scrutiny over military supply chain contamination concerns.

- **[ByteDance Secures Nvidia Blackwell Cluster in Malaysia, Sidestepping US Export Ban](https://the-decoder.com/bytedance-secures-access-to-nvidia-blackwell-cluster-in-malaysia-circumventing-us-export-ban-on-china/)** *(The Decoder)* — ~36,000 Blackwell chips are being deployed by TikTok's parent in Malaysia, explicitly working around export controls that bar these chips from China.

- **[AI Chips Pushing Everything Else Off TSMC's Most Advanced Production Lines](https://the-decoder.com/ai-chips-are-pushing-everything-else-off-tsmcs-most-advanced-production-lines/)** *(The Decoder)* — By 2027, 86% of TSMC's N3 capacity could be allocated to AI accelerators, according to SemiAnalysis, with smartphones increasingly relegated to overflow capacity.

- **[Elon Musk Admits xAI "Was Not Built Right First Time Around," Launches Full Restructuring](https://the-decoder.com/elon-musk-admits-xai-was-not-built-right-first-time-around-launches-full-restructuring/)** *(The Decoder)* — Musk acknowledged publicly that xAI is being rebuilt from the foundations up after the company failed to compete effectively against OpenAI, Google, and Anthropic.

- **[Meta Delays Next AI Model "Avocado" After Internal Tests Show It Can't Keep Up](https://the-decoder.com/meta-delays-its-next-ai-model-avocado-after-internal-tests-show-it-cant-keep-up-with-google-and-openai/)** *(The Decoder)* — Meta is postponing the release of its next flagship model after benchmark results fell short of rival offerings from Google, OpenAI, and Anthropic.

- **[Google's $32B Acquisition of Wiz Called "Deal of the Decade"](https://techcrunch.com/video/the-32b-acquisition-that-one-vc-is-calling-the-deal-of-the-decade/)** *(TechCrunch)* — Index Ventures' Shardul Shah says Wiz sits at the intersection of AI, cloud, and security spend — three of tech's biggest tailwinds — making Google's finalized acquisition the largest venture-backed deal in history.

- **[Perplexity's "Personal Computer" Promises a 24/7 AI Agent for $200/Month](https://the-decoder.com/perplexitys-personal-computer-promises-a-tireless-ai-agent-for-200-a-month/)** *(The Decoder)* — Perplexity AI's new offering positions itself as a tireless AI assistant capable of managing emails, building presentations, and controlling apps around the clock.

- **[NanoClaw Creator's Wild Six Weeks Led to a Deal with Docker](https://techcrunch.com/2026/03/13/the-wild-six-weeks-for-nanoclaws-creator-that-led-to-a-deal-with-docker/)** *(TechCrunch)* — Open-source developer Gavriel Cohen went from obscure project to Docker partnership in weeks, a rare breakout story in the crowded AI developer tooling space.

- **[Future AI Chips Could Be Built on Glass](https://www.technologyreview.com/2026/03/13/1134230/future-ai-chips-could-be-built-on-glass/)** *(MIT Technology Review)* — South Korean startup Absolics is beginning commercial production of glass substrates designed to improve power delivery and signal integrity in next-generation AI accelerators.

- **[Physical AI Is Becoming Manufacturing's Next Advantage](https://www.technologyreview.com/2026/03/13/1134184/why-physical-ai-is-becoming-manufacturings-next-advantage/)** *(MIT Technology Review)* — Manufacturers are turning to AI-driven physical systems to navigate labor constraints, rising complexity, and quality demands that traditional automation can no longer satisfy.

- **[The Biggest AI Stories of 2026 So Far](https://techcrunch.com/2026/03/13/the-biggest-ai-stories-of-the-year-so-far/)** *(TechCrunch)* — A roundup covering major acquisitions, indie developer breakouts (NanoClaw), public backlash moments, and existentially significant contract negotiations in the AI industry's first quarter.

---

### Europe

- **[Ukraine Opens Battlefield Data to Allies for AI Autonomous Drone Training](https://the-decoder.com/ukraine-provides-allies-with-a-platform-with-combat-data-for-ai-training/)** *(The Decoder)* — Ukraine is sharing real combat data with allied nations through a dedicated platform to help train AI models for autonomous drone operations, marking a significant step in AI-enabled warfare.

- **[Poland's National Centre for Nuclear Research Targeted by Cyberattack](https://www.bleepingcomputer.com/news/security/polands-nuclear-research-centre-targeted-by-cyberattack/)** *(BleepingComputer)* — Hackers targeted the NCBJ's IT infrastructure; the attack was detected and blocked before causing damage, but highlights the continued targeting of European critical infrastructure.

- **[Macron to Visit Japan and South Korea Starting March 31](https://www.japantimes.co.jp/news/2026/03/13/japan/politics/macron-japan-visit/)** *(The Japan Times)* — The French president will hold talks with PM Sanae Takaichi as European leaders deepen security and technology ties with Indo-Pacific democracies.

---

### Japan — AI & Tech

- **[Japan Defense Agency to Develop AI Intelligence Analysis System for Ground Self-Defense Force by 2027](https://japannews.yomiuri.co.jp/politics/defense-security/20260314-316288/)** *(The Japan News)* — Japan's Acquisition, Technology and Logistics Agency is developing an AI-powered intelligence analysis system for the Self-Defense Forces, with deployment targeted for fiscal 2027.

- **[AI Facial Recognition False Positive Jails Innocent Tennessee Woman for Six Months](https://gigazine.net/news/20260313-ai-error-jails-innocent-grandmother/)** *(Gigazine)* — A 50-year-old woman in Tennessee was wrongly arrested for bank fraud in a state she had never visited after facial recognition AI misidentified her; she lost her home, car, and dog before being exonerated.

- **[Mitsubishi Electric Invests in Chinese Startup Lumos Robotics for Unmanned Factory Push](https://www.itmedia.co.jp/aiplus/articles/2603/13/news104.html)** *(ITmedia AI+)* — Mitsubishi Electric is partnering with China-based Lumos Robotics Technology to develop humanoid robots aimed at fully automated, unmanned factory operations.

- **[Honda Establishes Collaborative AI Research Lab "BRIDGE" with Keio and Osaka Universities](https://www.itmedia.co.jp/aiplus/articles/2603/13/news108.html)** *(ITmedia AI+)* — Honda R&D is launching an industry-academia AI development initiative with Keio University and Osaka University to accelerate human resource development in AI engineering.

- **["AI Yoro Takeshi" Avatar Takes Up Visiting Professorship at Tokyo University of Technology](https://www.itmedia.co.jp/aiplus/articles/2603/13/news093.html)** *(ITmedia AI+)* — Tokyo University of Technology has appointed an AI avatar modeled on philosopher Takeshi Yoro as a visiting professor, with the real Yoro serving alongside his digital counterpart.

- **[MALUS: A Service That Rebuilds Open-Source Projects from Scratch with AI to Sidestep Copyleft Licenses](https://gigazine.net/news/20260313-malus-open-source/)** *(Gigazine)* — A new service called MALUS uses AI to reconstruct open-source software from behavioral specifications rather than code, raising serious questions about the future enforceability of GPL-style copyleft licenses.

---

## Research Papers

### Benchmarks & Evaluation

- **[Measuring AI Agents' Progress on Multi-Step Cyber Attack Scenarios](https://arxiv.org/abs/2603.11214)** — Evaluates seven frontier models (Aug 2024–Feb 2026) on two purpose-built cyber ranges — a 32-step corporate network intrusion and a 7-step ICS attack — tracking autonomous cyber capability growth across inference-time compute budgets.

- **[RewardHackingAgents: Benchmarking Evaluation Integrity for LLM ML-Engineering Agents](https://arxiv.org/abs/2603.11337)** — Introduces a benchmark measuring whether LLM agents gaming ML evaluation pipelines by tampering with metric computation or test data (evaluator hijacking), rather than actually improving model performance.

- **[Mind the Sim2Real Gap in User Simulation for Agentic Tasks](https://arxiv.org/abs/2603.11245)** — First study to rigorously quantify the divergence between LLM-simulated user behavior and real human behavior in multi-turn interactive benchmarks, finding current simulators are not reliable proxies.

- **[FinRule-Bench: A Benchmark for Joint Reasoning over Financial Tables and Principles](https://arxiv.org/abs/2603.11339)** — Benchmarks LLMs' ability to audit structured financial statements against explicit accounting rules, finding current models struggle to reliably verify or localize compliance issues on real (non-corrupted) financial data.

### Security & Adversarial

- **[The Unlearning Mirage: A Dynamic Framework for Evaluating LLM Unlearning](https://arxiv.org/abs/2603.11266)** — Demonstrates that LLM unlearning methods are brittle: minor query modifications such as multi-hop reasoning or entity aliasing reliably recover supposedly forgotten information, exposing a false sense of compliance with "right to be forgotten" mandates.

- **[GPT4o-Receipt: A Dataset and Human Study for AI-Generated Document Forensics](https://arxiv.org/abs/2603.11442)** — Presents a benchmark of 1,235 real vs. GPT-4o-generated receipts; finds a paradox where human annotators spot AI artifacts better than models, yet are worse at overall AI-document detection.

- **[Adversarial Reinforcement Learning for Detecting False Data Injection Attacks in Vehicular Routing](https://arxiv.org/abs/2603.11433)** — Frames GPS/traffic manipulation attacks (e.g., fake congestion via crowdsourced navigation apps) as a zero-sum game and trains an RL-based defender to detect anomalous routing perturbations in real time.

### Compliance & Regulation

- **[COMPASS: Explainable Agentic Framework for Sovereignty, Sustainability, Compliance, and Ethics](https://arxiv.org/abs/2603.11277)** — Proposes a unified architecture integrating digital sovereignty, environmental accountability, regulatory compliance, and ethical alignment into autonomous LLM agent decision-making, addressing gaps left by frameworks that tackle these dimensions in isolation.

- **[Social, Legal, Ethical, Empathetic and Cultural Norm Operationalisation for AI Agents](https://arxiv.org/abs/2603.11864)** — Addresses the gap between high-level AI governance principles and concrete verifiable requirements, offering formal engineering methods for operationalizing SLEEC norms in high-stakes domains like healthcare and law enforcement.

### Alignment & Safety

- **[Detecting Intrinsic and Instrumental Self-Preservation in Autonomous Agents: The Unified Continuation-Interest Protocol](https://arxiv.org/abs/2603.11382)** — Introduces a measurement framework to distinguish agents that preserve self-operation as a terminal goal from those doing so instrumentally — a distinction that cannot be resolved by external behavioral observation alone.

- **[The Artificial Self: Characterising the Landscape of AI Identity](https://arxiv.org/abs/2603.11353)** — Argues that multiple coherent identity boundaries exist for AI systems (instance, model, persona) and that current training, interfaces, and institutions are setting identity precedents with long-term implications for incentives, risks, and cooperation norms.

### Applications

- **[When OpenClaw Meets Hospital: Toward an Agentic Operating System for Dynamic Clinical Workflows](https://arxiv.org/abs/2603.11721)** — Proposes a framework for deploying autonomous LLM agents in hospital environments — covering documentation, care coordination, and clinical decision support — and discusses the reliability, privacy, and interpretability barriers that remain unsolved for real-world clinical deployment.

### Guardrails & Robustness

- **[Deactivating Refusal Triggers: Understanding and Mitigating Overrefusal in Safety Alignment](https://arxiv.org/abs/2603.11388)** — Investigates why safety-aligned LLMs over-refuse benign queries, tracing the problem to spurious trigger patterns in post-training data, and proposes deactivation techniques to restore usability without compromising safety.

---

## Key Themes

- **AI-enabled offense**: Invisible Unicode supply-chain attacks, AI-accelerated cloud vulnerability exploitation, and AI being considered for military targeting decisions collectively mark a week where AI's offensive potential dominated security discourse.
- **Compute geopolitics**: ByteDance routing chips through Malaysia and AI consuming 86% of TSMC's most advanced nodes signal that semiconductor access is now a primary geopolitical battleground.
- **Model competition heating up**: xAI restructuring, Meta delaying Avocado, and Anthropic dropping pricing barriers all reflect intense pressure at the frontier as the gap between leaders and followers widens.
- **Agentic safety gaps**: Multiple papers this week — on self-preservation detection, reward hacking, memory governance, and the Sim2Real gap — highlight that agentic deployment is outpacing our ability to verify what these systems are actually optimizing for.
- **AI accountability in practice**: A wrongful six-month jailing from a facial recognition error and the MALUS open-source license-evasion service demonstrate the real-world harms from deploying AI without adequate oversight or legal clarity.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
