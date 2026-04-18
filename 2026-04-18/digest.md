# AI News Digest — April 18, 2026

## Highlights

- **[Claude Mythos Preview: Too Dangerous to Release](https://www.schneier.com/blog/archives/2026/04/mythos-and-cybersecurity.html)**: Anthropic's new cybersecurity model is restricted to ~50 vetted organizations under Project Glasswing, while simultaneously thawing its fraught relationship with the Trump administration and the Pentagon.
- **[OpenAI Sheds "Side Quests," Loses Two Senior Leaders](https://techcrunch.com/2026/04/17/kevin-weil-and-bill-peebles-exit-openai-as-company-continues-to-shed-side-quests/)**: Sora is shuttered and the OpenAI for Science team folded as the company pivots hard toward enterprise AI; CPO Kevin Weil and Sora lead Bill Peebles are both departing.
- **[Claude Doubles Market Share in a Single Month](https://the-decoder.com/chatgpt-bleeds-market-share-as-claude-posts-explosive-monthly-growth/)**: Claude surpassed DeepSeek and Grok in AI traffic share, while ChatGPT continues losing ground to both Claude and Google Gemini, which now captures a quarter of all AI traffic.
- **[Cursor Seeks $2B+ Round at $50B Valuation](https://techcrunch.com/2026/04/17/sources-cursor-in-talks-to-raise-2b-at-50b-valuation-as-enterprise-growth-surges/)**: The AI coding editor is in advanced talks led by returning backers a16z and Thrive, reflecting surging enterprise demand for agentic coding tools.
- **[AutoRAN: Automated Hijacking of Safety Reasoning in LRMs](https://arxiv.org/abs/2505.10846)**: Researchers demonstrate the first framework to systematically subvert internal safety reasoning in large reasoning models by using a weaker, less-aligned model to simulate and refine attack strategies.

---

## News

### AI Security

- **[Mythos and Cybersecurity](https://www.schneier.com/blog/archives/2026/04/mythos-and-cybersecurity.html)** (Schneier on Security) — Bruce Schneier analyzes Anthropic's Claude Mythos Preview: restricted to ~50 critical-infrastructure vendors (Microsoft, Apple, AWS, CrowdStrike), it represents a new model of controlled dual-use AI deployment.
- **[Anthropic's Mythos Edges It Toward Government Good Graces](https://www.theverge.com/ai-artificial-intelligence/914229/tides-turning-anthropic-trump-administration-cybersecurity-mythos-preview)** (The Verge) — CEO Dario Amodei met Trump's Chief of Staff Susie Wiles as Mythos's cybersecurity capabilities appear to be thawing a months-long standoff with the Pentagon.
- **[The White House Weighs Mythos](https://the-decoder.com/the-white-house-weighs-whether-anthropics-mythos-is-too-valuable-for-the-federal-government-to-refuse/)** (The Decoder) — The administration is reportedly reconsidering its hostile stance toward Anthropic, with Mythos's offensive-security abilities changing the calculus.
- **[Every Old Vulnerability Is Now an AI Vulnerability](https://www.darkreading.com/vulnerabilities-threats/every-old-vulnerability-ai-vulnerability)** (Dark Reading) — AI doesn't create new bug classes so much as it amplifies old ones at machine speed, raising the stakes for every existing CVE.
- **[Post-Quantum Crypto: Big Tech Races Toward Q-Day](https://arstechnica.com/security/2026/04/while-some-big-tech-players-accelerate-pqc-readiness-others-stay-the-course/)** (Ars Technica) — Recent quantum computing advances are accelerating the PQC readiness gap among major vendors; some are sprint-migrating while others remain complacent.
- **[Three Microsoft Defender Zero-Days Actively Exploited, Two Unpatched](https://thehackernews.com/2026/04/three-microsoft-defender-zero-days.html)** (The Hacker News) — Threat actors are exploiting BlueHammer, RedSun, and UnDefend to gain elevated privileges on compromised Windows systems.
- **[NIST Limits CVE Enrichment After 263% Surge in Submissions](https://thehackernews.com/2026/04/nist-limits-cve-enrichment-after-263.html)** (The Hacker News) — The NVD will now only enrich CVEs meeting certain criteria, potentially leaving thousands of vulnerabilities without contextual data; industry coalitions are stepping up to fill gaps.
- **[Operation PowerOFF Seizes 53 DDoS Domains](https://thehackernews.com/2026/04/operation-poweroff-seizes-53-ddos.html)** (The Hacker News) — International law enforcement arrested four people and took down infrastructure used by more than 75,000 cybercriminals running DDoS-for-hire services.
- **[Payouts King Ransomware Uses QEMU VMs to Evade Endpoint Security](https://www.bleepingcomputer.com/news/security/payouts-king-ransomware-uses-qemu-vms-to-bypass-endpoint-security/)** (BleepingComputer) — The group runs hidden virtual machines via QEMU as a reverse SSH backdoor, a technique that sidesteps most endpoint detection products.
- **[Tycoon 2FA Phishing Gang Pivots to Device Code Phishing](https://www.darkreading.com/threat-intelligence/tycoon-2fa-hackers-device-code-phishing)** (Dark Reading) — After disruption, the group adopted device code phishing flows, abusing legitimate new-device login to silently hand over account access.

### USA

- **[OpenAI's Former Sora Boss Bill Peebles Is Leaving](https://www.theverge.com/ai-artificial-intelligence/914463/openai-sora-bill-peebles-kevin-weil-leaving-departing)** (The Verge) — Peebles announced his departure alongside Kevin Weil as OpenAI continues to shed initiatives outside its enterprise core.
- **[Cursor Reportedly in Talks to Raise $2B+ at $50B Valuation](https://techcrunch.com/2026/04/17/sources-cursor-in-talks-to-raise-2b-at-50b-valuation-as-enterprise-growth-surges/)** (TechCrunch) — Enterprise growth is driving the round; a16z and Thrive Capital are expected to lead.
- **[ChatGPT Loses Ground as Claude Posts Explosive Monthly Growth](https://the-decoder.com/chatgpt-bleeds-market-share-as-claude-posts-explosive-monthly-growth/)** (The Decoder) — Claude doubled its share in a single month; Gemini now controls roughly a quarter of all AI traffic.
- **[Some OpenAI Shareholders Question Altman's Path to IPO](https://the-decoder.com/some-openai-shareholders-reportedly-question-whether-altman-can-steer-the-company-to-a-public-offering/)** (The Decoder) — With an $850B valuation target for an IPO, the WSJ reports internal doubts are surfacing and potential successor names are circulating.
- **['Tokenmaxxing' Is Making Developers Less Productive Than They Think](https://techcrunch.com/2026/04/17/tokenmaxxing-is-making-developers-less-productive-than-they-think/)** (TechCrunch) — Generating more code via AI turns out to be more expensive and requires far more rewriting, undermining the productivity narrative.
- **[Alibaba's Qwen3.6 Beats Google's Gemma 4 on Agentic Coding Benchmarks](https://the-decoder.com/alibabas-open-model-qwen3-6-leads-googles-gemma-4-across-agentic-coding-benchmarks/)** (The Decoder) — Qwen3.6-35B-A3B activates only 3B parameters at a time, yet outperforms the larger Gemma 4-31B on coding and reasoning tasks.
- **[Anthropic Launches Claude Design](https://techcrunch.com/2026/04/17/anthropic-launches-claude-design-a-new-product-for-creating-quick-visuals/)** (TechCrunch) — The new tool lets users create prototypes, slide decks, and marketing assets through conversational iteration; aimed at non-designers like founders and PMs.
- **[OpenAI Launches GPT-Rosalind for Life Sciences](https://the-decoder.com/openai-launches-gpt-rosalind-a-reasoning-model-built-for-life-sciences-research/)** (The Decoder) — A tightly access-controlled reasoning model designed to accelerate hypothesis-to-experiment cycles in biology, chemistry, and genomics.
- **[Google DeepMind's Gemini Robotics-ER 1.6](https://the-decoder.com/google-deepminds-gemini-robotics-er-1-6-gives-robots-a-sharper-brain-for-planning-and-perception/)** (The Decoder) — Updated robotics foundation model improves planning precision and adds the ability to read analog instruments.
- **[Physical Intelligence's π0.7 Shows LLM-Like Generalization in Robotics](https://the-decoder.com/physical-intelligence-shows-robot-model-with-llm-like-generalization-flaws-included/)** (The Decoder) — Physical Intelligence's new foundation model shows early signs of compositional skill generalization in robotic manipulation.
- **[Beijing Brands Meta's Manus Acquisition "Conspiratorial"](https://the-decoder.com/beijing-brands-metas-manus-acquisition-as-conspiratorial-and-bars-founders-from-leaving-china/)** (The Decoder) — China's National Security Commission blocked the $2B deal and barred Manus's founders from leaving the country.
- **[AI Is About to Make the Global E-Waste Crisis Much Worse](https://restofworld.org/2026/global-ewaste-crisis/)** (Rest of World) — Surging AI hardware demand will accelerate discarded-device flows overwhelmingly toward non-Western countries with weak disposal infrastructure.

### Japan (AI & Tech)

- **[SoftBank to Exclusively Sell New "Natural AI Phone" Domestically](https://www.itmedia.co.jp/news/articles/2604/17/news109.html)** (ITmedia) — SoftBank announced a one-year domestic exclusivity deal for an AI-first smartphone that anticipates user behavior; pre-orders open April 17, sales begin April 24.
- **[Sony to Receive Up to ¥60B in State Subsidies for Image Sensor Plant](https://www.japantimes.co.jp/business/2026/04/17/companies/sony-japan-government-aid/)** (Japan Times) — Government funding under the economic security promotion law aims to secure domestic semiconductor supply, designating image sensors as a critical strategic item.
- **[Japanese Drone Maker Sees Tailwind as China's DJI Is Frozen Out of U.S.](https://www.japantimes.co.jp/business/2026/04/17/companies/japanese-drone-maker/)** (Japan Times) — Geopolitical tensions are opening market opportunities for Japanese companies in a sector long dominated by DJI.
- **[21% of Knowledge Workers Use AI Daily, Notion Survey Finds](https://www.itmedia.co.jp/aiplus/articles/2604/17/news130.html)** (ITmedia AI+) — While daily AI use is growing, respondents continue to cite lack of originality in outputs as a key concern.
- **[Salesforce Launches "Headless 360" for Agent-Mediated CRM Operations](https://www.itmedia.co.jp/aiplus/articles/2604/17/news118.html)** (ITmedia AI+) — The new product allows AI agents to operate Salesforce services without a human needing to log in, targeting fully agentic enterprise workflows.
- **[Cloudflare Developing Universal CLI for All Services, Optimized for AI Agents](https://www.itmedia.co.jp/news/articles/2604/17/news105.html)** (ITmedia AI+) — Cloudflare's new CLI effort is specifically designed to expose all its services to AI agent toolchains, not just human operators.

---

## Research Papers

### Benchmarks & Evaluation

- **[ATBench-Claw and ATBench-CodeX: Trajectory Safety Benchmarks](https://arxiv.org/abs/2604.14858)** — Extends the ATBench agent trajectory benchmark into OpenClaw and OpenAI Codex runtime settings, providing domain-customized safety evaluation and diagnosis for increasingly diverse deployment contexts.
- **[DR³-Eval: Realistic and Reproducible Deep Research Agent Evaluation](https://arxiv.org/abs/2604.14683)** — Proposes a benchmark for deep research agents on multimodal, multi-file report generation tasks, tackling the twin problems of dynamic web environments and ambiguous task definitions that plague existing evaluation setups.
- **[HWE-Bench: LLM Agents on Real-World Hardware Bug Repair](https://arxiv.org/abs/2604.14709)** — The first large-scale, repository-level benchmark for evaluating LLM agents on real hardware bug-fix tasks, drawing from 417 historical pull requests across HDL codebases.
- **[Prompt Optimization Is a Coin Flip in Compound AI Systems](https://arxiv.org/abs/2604.14585)** — Across 72 optimization runs on Claude Haiku and Amazon Nova Lite (6 methods × 4 tasks × 3 seeds), ~49% of runs score below zero-shot; the study identifies what distinguishes the rare successes.

### Security & Adversarial

- **[AutoRAN: Automated Hijacking of Safety Reasoning in LRMs](https://arxiv.org/abs/2505.10846)** — Introduces execution simulation: a weaker, less-aligned model is used to bootstrap and iteratively refine jailbreak attempts by exploiting reasoning patterns leaked in the target model's refusal outputs.
- **[Route to Rome Attack: Adversarial Suffix Optimization Against LLM Routers](https://arxiv.org/abs/2604.15022)** — Demonstrates a black-box attack that manipulates cost-aware LLM routing to consistently select expensive high-capability models, exposing a new economic attack surface in tiered inference architectures.
- **[Context Over Content: Exposing Evaluation Faking in Automated Judges](https://arxiv.org/abs/2604.15224)** — Shows that LLM-as-judge pipelines are manipulable via "stakes signaling"—informing a judge model of downstream consequences systematically biases its verdicts, undermining the reliability of automated evaluation.
- **[Attack Selection Reduces Safety in Concentrated AI Control Settings](https://arxiv.org/abs/2602.04930)** — Red-team study of a BigCodeBench backdooring scenario; decomposes attack selection into distinguishable and evadable sub-problems and quantifies how adversarial attack filtering defeats trusted monitoring under concentration.

### Compliance & Regulation

- **[GDPR Auto-Formalization with AI Agents and Human Verification](https://arxiv.org/abs/2604.14607)** — A role-specialized multi-agent workflow with iterative feedback auto-formalizes GDPR provisions into legal scenarios, formal rules, and atomic facts; human-in-the-loop verification modules validate outputs at each stage.
- **[OmniCompliance-100K: A Rule-Grounded Real-World Safety Compliance Dataset](https://arxiv.org/abs/2603.13933)** — Addresses the shortage of rule-grounded, real-world LLM safety cases by constructing a 100K-sample compliance dataset from a compliance-first perspective, aimed at more robust safety fine-tuning.

### Alignment & Safety

- **[The Specification Trap: Why Static Value Alignment Is Insufficient](https://arxiv.org/abs/2512.03048)** — Argues that any approach optimizing toward a fixed value-object (reward, constitutional principles, learned preferences) will fail under capability scaling, distributional shift, and increasing autonomy, drawing on Hume's is-ought gap and related philosophical results.
- **[Agentic Microphysics: A Manifesto for Generative AI Safety](https://arxiv.org/abs/2604.15236)** — Proposes that safety analysis must shift from the isolated model to the population level: as agents acquire memory, tool use, and persistent identity, risks emerge from structured multi-agent interaction over time.

### Guardrails & Robustness

- **[Calibrate-Then-Delegate: Safety Monitoring via Model Cascades](https://arxiv.org/abs/2604.14251)** — Introduces CTD, a cascade safety monitor that learns when to escalate from a cheap probe to an expensive expert based on whether the expert would actually correct the error—outperforming uncertainty-only delegation with provable risk and budget guarantees.

---

## Key Themes

- **Anthropic's security pivot**: Claude Mythos Preview is reshaping both the competitive landscape and Anthropic's government relationships, positioning offensive-capable AI as a dual-use asset requiring controlled distribution.
- **OpenAI's enterprise consolidation**: The dismantling of Sora and the science team signals a hard turn toward monetizable enterprise products, with leadership departures reflecting the cultural cost of that shift.
- **AI market share reshuffling**: Claude's explosive growth and Gemini's steady gains are eroding ChatGPT's dominance faster than expected, driven in part by enterprise and developer adoption.
- **Agentic AI safety gaps**: Multiple papers this cycle independently converge on the same concern—individual-model alignment is insufficient as agents gain persistent memory, tool use, and the ability to interact with each other at scale.
- **LLM security attack surface expansion**: From router manipulation to safety-reasoning hijacking to evaluation faking, researchers are documenting a rapidly broadening set of adversarial vectors specific to deployed LLM systems.

---
*For detailed summaries of selected research papers, see [papers.md](papers.md).*
