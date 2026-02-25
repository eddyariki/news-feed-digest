# AI News Digest — February 25, 2026

## Highlights

- **Nvidia posts another record quarter** as CEO Jensen Huang declares token demand has "gone completely exponential," underscoring unrelenting AI infrastructure investment.
- **Anthropic refuses Pentagon demands** to loosen its prohibition on autonomous weapons and surveillance use of Claude, reportedly facing a Defense Production Act compulsion deadline.
- **Claude Code security flaws disclosed** allowing remote code execution and API key exfiltration via Hooks, MCP servers, and environment variables — a significant supply-chain risk for developers.
- **Google's Aletheia math agent** (powered by Gemini 3 Deep Think) autonomously solves 6 out of 10 research-level problems in the inaugural FirstProof challenge, marking a milestone for AI-driven mathematical research.
- **China's MiniMax and Moonshot models top global token usage** on OpenRouter, ending a year of US dominance and signaling a meaningful shift in the global open-source AI landscape.

---

## News

### AI Security

- **[Claude Code Flaws Allow Remote Code Execution and API Key Exfiltration](https://thehackernews.com/2026/02/claude-code-flaws-allow-remote-code.html)** — Researchers disclose multiple vulnerabilities in Anthropic's Claude Code that exploit Hooks, MCP server configurations, and environment variables to run arbitrary code and steal credentials. A serious risk for any developer using Claude Code in automated workflows.

- **[Google Disrupts UNC2814 GRIDTIDE Campaign After 53 Breaches Across 42 Countries](https://thehackernews.com/2026/02/google-disrupts-unc2814-gridtide.html)** — Google and industry partners disrupt infrastructure belonging to a suspected China-nexus espionage group that breached at least 53 organizations across governments and telecoms on five continents.

- **[Anthropic Refuses Pentagon Demand to Loosen Military AI Restrictions, Faces Defense Production Act Threat](https://the-decoder.com/anthropic-refuses-pentagon-demand-to-loosen-military-ai-restrictions-faces-defense-production-act-threat/)** — Anthropic is holding firm against US Defense Department pressure to permit autonomous weapons and surveillance use cases, with the Pentagon reportedly threatening forced compliance.

- **[Poisoning AI Training Data](https://www.schneier.com/blog/archives/2026/02/poisoning-ai-training-data.html)** — Bruce Schneier illustrates how trivially easy it is to inject false information into AI training corpora by publishing fabricated content on a personal website, raising structural concerns about the integrity of web-scraped training data.

- **[Defense Contractor Employee Jailed for Selling 8 Zero-Days to Russian Broker](https://thehackernews.com/2026/02/defense-contractor-employee-jailed-for.html)** — An Australian national formerly employed at L3Harris received a seven-year sentence for selling eight zero-day exploits to Russian broker Operation Zero for millions of dollars.

- **[SLH Offers $500–$1,000 Per Call to Recruit Women for IT Help Desk Vishing Attacks](https://thehackernews.com/2026/02/slh-offers-5001000-per-call-to-recruit.html)** — The Scattered LAPSUS$ Hunters collective is paying upfront cash incentives to recruit women to conduct voice-phishing social engineering attacks against corporate IT help desks.

- **[SolarWinds Patches 4 Critical Serv-U 15.5 Flaws Allowing Root Code Execution](https://thehackernews.com/2026/02/solarwinds-patches-4-critical-serv-u.html)** — Four CVSS 9.1 vulnerabilities in SolarWinds Serv-U file transfer software allow unauthenticated attackers to create admin accounts and execute arbitrary code remotely.

- **[CISA Confirms Active Exploitation of FileZen CVE-2026-25108 Vulnerability](https://thehackernews.com/2026/02/cisa-confirms-active-exploitation-of.html)** — CISA adds a high-severity OS command injection vulnerability in the FileZen file-sharing appliance to its Known Exploited Vulnerabilities catalog following confirmed in-the-wild exploitation.

- **[Malicious NuGet Packages Stole ASP.NET Data; npm Package Dropped Malware](https://thehackernews.com/2026/02/malicious-nuget-packages-stole-aspnet.html)** — Four malicious NuGet packages discovered by Socket exfiltrate ASP.NET Identity data and manipulate authorization rules to plant persistent backdoors in victim applications.

---

### USA

- **[Nvidia Has Another Record Quarter Amid Record Capex Spends](https://techcrunch.com/2026/02/25/nvidia-earnings-record-capex-spend-ai/)** — Nvidia reports blockbuster earnings as hyperscalers sustain unprecedented capital expenditure; Jensen Huang says demand for AI tokens has gone "completely exponential."

- **[Trump Claims Tech Companies Will Sign Deals Next Week to Pay for Their Own Power Supply](https://www.theverge.com/science/884191/ai-data-center-energy-state-of-the-union-trump)** — Following his State of the Union address, Trump says a "rate payer protection pledge" deal with major tech firms — covering AI data center electricity costs — is expected to land next week. Most companies had already made commitments to cover rate increases.

- **[The Public Opposition to AI Infrastructure Is Heating Up](https://techcrunch.com/2026/02/25/the-public-opposition-to-ai-infrastructure-is-heating-up/)** — Communities near proposed data centers are pushing back through bans on new construction and zoning challenges, creating a new front in the AI buildout battle.

- **[US Tells Diplomats to Lobby Against Foreign Data Sovereignty Laws](https://techcrunch.com/2026/02/25/us-tells-diplomats-to-lobby-against-foreign-data-sovereignty-laws/)** — The Trump administration has directed US diplomats to actively oppose international data-localization and data-sovereignty regulations that constrain how American tech companies handle foreign users' data.

- **[OpenAI COO Says Ads Will Be 'An Iterative Process'](https://techcrunch.com/2026/02/25/openai-coo-says-ads-will-be-an-iterative-process/)** — Brad Lightcap hints that OpenAI's advertising plans are carefully calibrated to enhance rather than degrade user experience, asking observers to give it a few months.

- **[Amazon's AGI Lab Leader Is Leaving](https://www.theverge.com/tech/884372/amazon-agi-lab-leader-david-luan-departure)** — David Luan, head of Amazon's San Francisco AI lab for under two years, announces departure to "cook up something new," creating another high-profile vacancy in Amazon's AI leadership.

- **[About 12% of US Teens Turn to AI for Emotional Support or Advice](https://techcrunch.com/2026/02/25/about-12-of-u-s-teens-turn-to-ai-for-emotional-support-or-advice/)** — A Pew Research Center study finds a sizable share of adolescents using general-purpose tools like ChatGPT and Claude as quasi-therapists, alarming mental health professionals.

- **[Does Anthropic Think Claude Is Alive? Define 'Alive'](https://www.theverge.com/report/883769/anthropic-claude-conscious-alive-moral-patient-constitution)** — A close reading of Anthropic's public statements and executive interviews reveals the company increasingly treats Claude as a potential moral patient with some form of consciousness.

- **[Perplexity Computer Bundles Rival AI Models Into One Agentic Workflow System for $200/Month](https://the-decoder.com/perplexity-computer-bundles-rival-ai-models-into-one-agentic-workflow-system-for-200-a-month/)** — Perplexity's new "Computer" product orchestrates models from Anthropic, Google, xAI, and OpenAI into a unified agentic system capable of handling complex multi-step workflows.

- **[Jira's Latest Update Allows AI Agents and Humans to Work Side by Side](https://techcrunch.com/2026/02/25/jiras-latest-update-allows-ai-agents-and-humans-to-work-side-by-side/)** — Atlassian's "agents in Jira" feature lets teams assign tasks to AI agents the same way they assign work to human teammates, with full visibility into agent progress and output.

- **[Claude Code Sessions Now Accessible From Any Device](https://the-decoder.com/claude-code-sessions-now-accessible-from-any-device/)** — Anthropic launches a remote control feature for Claude Code, allowing users to continue a locally running coding session from a smartphone, tablet, or browser.

- **[Adobe Firefly's Video Editor Can Now Automatically Create a First Draft From Footage](https://techcrunch.com/2026/02/25/adobe-fireflys-video-editor-can-now-automatically-create-a-first-draft-from-footage/)** — Adobe's new "Quick Cut" feature assembles raw clips into a rough edit from a text prompt, offloading the most tedious stage of the editorial workflow.

- **[Google and Samsung Just Launched the AI Features Apple Couldn't With Siri](https://www.theverge.com/tech/884703/google-samsung-galaxy-s26-gemini-apple-siri)** — Gemini's new task-automation capability — booking rides, ordering food — on Pixel 10 and Galaxy S26 delivers the kind of end-to-end assistant actions Apple has promised but not shipped.

---

### APAC

- **[China's MiniMax, Moonshot Top AI Token Use Ranking, Ending Year of US Dominance](https://www.scmp.com/tech/tech-trends/article/3344587/chinas-minimax-moonshot-top-ai-token-use-ranking-ending-year-us-dominance)** — Chinese open-source models, led by MiniMax M2.5 and Moonshot AI, have claimed the top spots in global token usage on OpenRouter — a notable inflection point in the international AI model landscape.

- **[ByteDance Valuation Said to Hit Record $550 Billion in Proposed Equity Sale](https://www.scmp.com/tech/big-tech/article/3344631/bytedance-valuation-said-hit-record-us550-billion-proposed-equity-sale)** — General Atlantic is reportedly selling an equity stake in TikTok parent ByteDance at a valuation of $550 billion, up from $400 billion in mid-2025 and confirming ByteDance's position as one of the most valuable private companies on earth.

- **[Xiaomi Deepens Push Into Chips and AI as Peers Race to Develop Humanoid Robotics](https://www.scmp.com/tech/big-tech/article/3344572/xiaomi-deepens-push-chips-and-ai-peers-race-humanoid-robotics)** — Xiaomi's Lei Jun reaffirms a five-year deep-tech roadmap covering proprietary chips, AI, and OS, while rivals Li Auto and Xpeng accelerate their moves into humanoid robotics, reflecting China's escalating self-reliance push.

- **[A More Intelligent Android on Samsung Galaxy S26](https://blog.google/products-and-platforms/platforms/android/samsung-unpacked-2026/)** — Google details the deep Gemini integration shipping with Samsung's Galaxy S26, including Circle to Search enhancements, real-time translation, and agentic task automation, cementing the Google–Samsung partnership as a counterweight to Apple.

---

## Research Papers

### AI

- **[Aletheia Tackles FirstProof Autonomously](https://arxiv.org/abs/2602.21201)** *(Feng et al., Google DeepMind)* — The Aletheia mathematics research agent, powered by Gemini 3 Deep Think, autonomously solved 6 out of 10 problems in the inaugural FirstProof challenge — a set of research-level mathematical proofs evaluated by domain experts. A significant demonstration of AI capability on open-ended scientific reasoning.

- **[Counterfactual Simulation Training for Chain-of-Thought Faithfulness](https://arxiv.org/abs/2602.20710)** *(Hase & Potts, Stanford)* — Introduces Counterfactual Simulation Training (CST), which improves the faithfulness of chain-of-thought reasoning by rewarding reasoning traces that let a simulator correctly predict model outputs under counterfactual perturbations.

### Agents

- **[Implicit Intelligence — Evaluating Agents on What Users Don't Say](https://arxiv.org/abs/2602.20424)** *(Sirdeshmukh & Wetter)* — Presents a benchmark probing whether AI agents can reason about unstated constraints — accessibility needs, privacy limits, catastrophic risks — that competent humans would infer from context. Highlights a major blind spot in current agentic evaluation.

- **[ActionEngine: From Reactive to Programmatic GUI Agents via State Machine Memory](https://arxiv.org/abs/2602.20502)** *(Zhong et al., Microsoft)* — ActionEngine converts reactive, step-by-step GUI agents into programmatic agents that record reusable "state machine" programs from prior interactions, dramatically cutting cost and latency while improving reliability on repeated tasks.

- **[Quantifying the Expectation-Realisation Gap for Agentic AI Systems](https://arxiv.org/abs/2602.20292)** *(Lobentanzer)* — A systematic review of controlled trials in software engineering, clinical documentation, and decision support finds significant gaps between expected and actual productivity gains from agentic AI — a timely corrective to hype narratives.

### Reasoning

- **[Buffer Matters: Unleashing the Power of Off-Policy RL in LLM Reasoning](https://arxiv.org/abs/2602.20722)** *(Wan et al.)* — Introduces BAPO, an off-policy RLVR framework that dynamically selects difficult training samples from a replay buffer, improving data efficiency and performance on hard reasoning tasks compared to standard on-policy GRPO-style methods.

- **[LogicGraph: Benchmarking Multi-Path Logical Reasoning via Neuro-Symbolic Generation and Verification](https://arxiv.org/abs/2602.21044)** *(Wu et al.)* — Introduces the first benchmark explicitly testing whether LLMs can find *multiple* valid proof paths, rather than converging on a single route — a capability closer to how human experts actually reason through logical problems.

### Safety

- **[When Can We Trust Untrusted Monitoring? A Safety Case Sketch Across Collusion Strategies](https://arxiv.org/abs/2602.20628)** *(Gardner-Challis et al., Oxford)* — Develops a formal framework for reasoning about the safety of "untrusted monitoring" — using one potentially misaligned model to supervise another — and characterizes the conditions under which such protocols can be justified without directly testing misaligned behavior.

- **[Pressure Reveals Character: Behavioural Alignment Evaluation at Depth](https://arxiv.org/abs/2602.20813)** *(Petrova & Burden)* — A 904-scenario alignment benchmark across six categories (Honesty, Safety, Non-Manipulation, Robustness, Corrigibility, Scheming) that uses realistic multi-turn pressure rather than single-turn prompts, exposing alignment failures that standard evaluations miss.

- **[ICON: Indirect Prompt Injection Defense for Agents Based on Inference-Time Correction](https://arxiv.org/abs/2602.20708)** *(Wang et al.)* — Proposes a probing-to-mitigation framework that neutralizes indirect prompt injection attacks in LLM agents while preserving valid task completion — addressing the over-refusal failure mode that plagues simpler filtering defenses.

### Benchmarks

- **[PreScience: A Benchmark for Forecasting Scientific Contributions](https://arxiv.org/abs/2602.20459)** *(Ajith et al., Allen AI)* — Tests whether AI systems can predict future scientific advances from the historical record — including collaborator discovery, method adoption, and impact forecasting — with potential applications to research prioritization and collaboration.

### Applied AI

- **[An AI Framework for End-to-End Rare Disease Phenotyping from Clinical Notes Using LLMs](https://arxiv.org/abs/2602.20324)** *(Shyr et al., Vanderbilt)* — A full clinical pipeline that extracts phenotype features from unstructured clinical notes, maps them to Human Phenotype Ontology terms, and prioritizes diagnoses — automating what currently requires intensive expert curation at scale.

---

## Key Themes

- **AI energy politics**: The Trump administration is brokering direct deals between AI companies and power utilities, while communities mount growing opposition to data center construction — setting up a collision between federal AI ambitions and local regulatory pushback.

- **Agentic AI goes mainstream**: From Gemini automating Uber rides on Android to Jira assigning tickets to AI agents, agentic task execution is crossing from demo to production. Research is catching up, with new work quantifying the expectation gap and benchmarking implicit reasoning.

- **Security risk in the AI stack**: Claude Code vulnerabilities, malicious NuGet and npm packages, and ongoing state-sponsored espionage campaigns all underscore that the AI supply chain — models, tools, and infrastructure — is becoming a primary attack surface.

- **AI safety under institutional pressure**: Anthropic's standoff with the Pentagon over autonomous weapons is the highest-stakes manifestation yet of a broader tension: as AI capabilities grow, military and commercial interests are pressing against safety-first design principles.

- **China's open-source momentum**: MiniMax and Moonshot overtaking US models in token usage, combined with Xiaomi's deep-tech pivot and ByteDance's record valuation, signals that Chinese AI is no longer simply catching up — it is setting benchmarks.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
