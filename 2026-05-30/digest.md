# AI News Digest — 2026-05-30

## Highlights

- **[Anthropic releases Claude Opus 4.8 and confirms Mythos-class rollout](https://www.bleepingcomputer.com/news/artificial-intelligence/anthropic-confirms-claude-mythos-class-models-will-roll-out-to-the-public/)**: Opus 4.8 ships with sharply improved "honesty" calibration and a new dynamic-workflows feature for hundreds of parallel subagents, while the higher-capability Mythos tier moves to public rollout within weeks after a safety-driven delay.
- **[OpenAI launches Japan Cyber Action Plan, giving GPT-5.5-Cyber to government and major banks](https://www.itmedia.co.jp/aiplus/article/2605/29/2000000037/)**: Tokyo and the largest Japanese financial institutions receive privileged access to a cybersecurity-tuned frontier model to defend against AI-augmented attacks, an explicit national-defense deployment.
- **[Dutch authorities dismantle a 17-million-device botnet tied to a Russian residential proxy network](https://arstechnica.com/security/2026/05/botnet-of-more-than-17-million-devices-dismantled/)**: One of the largest known proxy-botnet takedowns; over 200 servers seized at a complicit hosting provider.
- **[ChatGPhish turns ChatGPT web summaries into a phishing surface](https://thehackernews.com/2026/05/chatgphish-vulnerability-turns-chatgpt.html)**: Permiso Security shows that ChatGPT's markdown-link renderer implicitly trusts attacker-supplied URLs, enabling prompt-injection-driven phishing inside the chat UI.
- **[OpenAI opens its GPT-Rosalind life-sciences model for free via the Rosalind Biodefense program](https://openai.com/index/strengthening-societal-resilience-with-rosalind-biodefense)**: Partners include Lawrence Livermore, Johns Hopkins, and CEPI, marking an unusual giveaway of a frontier scientific model framed as pandemic-preparedness infrastructure.

---

## News

### AI Security

- **[ChatGPhish vulnerability turns ChatGPT web summaries into a phishing surface](https://thehackernews.com/2026/05/chatgphish-vulnerability-turns-chatgpt.html)** — Permiso Security shows attacker-controlled markdown in summarized pages triggers prompt injection and phishing redirects inside ChatGPT.
- **[ChatGPT share links abused to host fake outage pages delivering malware](https://www.bleepingcomputer.com/news/security/chatgpt-share-links-abused-to-host-fake-outage-pages-to-deliver-malware/)** — Threat actors weaponize the share feature to push a trojanized "ChatGPT desktop" installer.
- **[Attackers use an LLM agent for post-exploitation after Marimo CVE-2026-39987](https://thehackernews.com/2026/05/attackers-use-llm-agent-for-post.html)** — First clearly documented case of an autonomous LLM agent driving the hands-on-keyboard stage of an intrusion.
- **[GreyVibe hackers use ChatGPT and Gemini to power Ukraine cyberattacks](https://www.bleepingcomputer.com/news/security/greyvibe-hackers-use-chatgpt-gemini-to-power-cyberattacks/)** — Russian-linked cluster generates lures and bespoke malware with commercial LLMs ([Hacker News writeup](https://thehackernews.com/2026/05/new-russian-linked-greyvibe-targets.html)).
- **[Dutch govt disrupts 17M-device malware botnet](https://www.bleepingcomputer.com/news/security/dutch-govt-disrupts-malware-botnet-with-17-million-infected-devices/)** — 200+ servers seized at a Dutch hoster supporting a Russia-linked residential proxy network ([Ars summary](https://arstechnica.com/security/2026/05/botnet-of-more-than-17-million-devices-dismantled/)).
- **[Charter Communications breach hits 4.9M accounts](https://www.bleepingcomputer.com/news/security/charter-communications-data-breach-affects-49-million-accounts/)** — ShinyHunters claims another major US telecom intrusion.
- **[California AG sues 23andMe over 2023 health-data breach](https://www.bleepingcomputer.com/news/security/california-ag-sues-23andme-over-2023-breach-exposing-health-data/)** — Suit alleges insufficient protection of genetic and personal data.
- **[Kimsuky deploys HTTPSpy and abuses VS Code tunnels](https://thehackernews.com/2026/05/kimsuky-deploys-httpspy-expands-arsenal.html)** — North Korean group expands its arsenal against South Korean military and corporate targets.
- **[Malicious Sicoob NuGet steals banking credentials](https://thehackernews.com/2026/05/malicious-sicoob-nuget-steals-banking.html)** — A typosquat of a major Brazilian co-op bank's SDK exfiltrates PFX certificates and client IDs.
- **["The Shadow Builders" report — what 2,000 exposed vibe-coded apps reveal](https://thehackernews.com/2026/05/what-2000-exposed-vibe-coded-apps.html)** — Employee-built LLM apps now publish straight to the open internet, bypassing security stacks.
- **[Google Chrome turns on Device Bound Session Credentials for everyone](https://www.bleepingcomputer.com/news/security/google-chrome-adds-session-cookie-theft-protection-for-all-users/)** — DBSC is now generally available to blunt session-cookie theft.
- **[As global powers explore humanoid robots, cyber-risk looms](https://www.darkreading.com/cyber-risk/global-powers-explore-humanoids-cyber-risk)** — Nation-states racing on embodied AI are creating a new and largely unguarded supply chain.
- **[Complex cloud integrations: small errors lead to major compromises](https://www.darkreading.com/vulnerabilities-threats/complex-cloud-integrations-small-errors-compromises)** — Researchers build an exploit chain in a popular automation service from over-permissioned roles and exposed secrets.
- **[Anthropic confirms Claude Mythos-class models will roll out to the public](https://www.bleepingcomputer.com/news/artificial-intelligence/anthropic-confirms-claude-mythos-class-models-will-roll-out-to-the-public/)** — Rollout had been delayed over public-safety concerns; new safeguards now in place.
- **[Google security engineer charged with Polymarket insider trading](https://www.bleepingcomputer.com/news/security/us-charges-google-security-engineer-with-polymarket-insider-trading/)** — Allegedly used confidential corporate data to win $1.2M on a crypto prediction market.
- **[GitHub bans Windows zero-day researcher Nightmare-Eclipse; GitLab follows](https://gigazine.net/news/20260529-nightmare-eclipse-github-banned/)** — Researcher says the bans are Microsoft retaliation for repeated zero-day disclosures.
- **[Man jailed 10+ years for selling data of 7M elderly Americans to Jamaican scammers](https://www.bleepingcomputer.com/news/security/man-sent-to-prison-for-selling-data-of-7-millions-elderly-americans/)** — North Carolina case.
- **[Inside the DDoS-as-a-Service market: from $5 attacks to botnet platforms](https://www.bleepingcomputer.com/news/security/from-5-attacks-to-botnet-powered-platforms-inside-the-ddos-as-a-service-market/)** — Flare profiles the maturation of booters into subscription products.

### USA

- **[OpenAI gives GPT-5.5 Instant a readability upgrade and retires o3 and GPT-4.5](https://the-decoder.com/openai-gives-gpt-5-5-instant-a-readability-upgrade-while-phasing-out-two-older-models/)** — Canvas is being dropped from the newest models; both legacy models shut down by August 2026.
- **[OpenAI launches Rosalind Biodefense, opening GPT-Rosalind to governments and vetted developers](https://openai.com/index/strengthening-societal-resilience-with-rosalind-biodefense)** — Pandemic-preparedness push covering biodefense and public-health partners ([Decoder summary](https://the-decoder.com/openai-is-giving-away-its-life-sciences-ai-model-to-help-governments-prepare-for-the-next-pandemic/)).
- **[OpenAI publishes "A shared playbook for trustworthy third-party evaluations"](https://openai.com/index/trustworthy-third-party-evaluations-foundations)** — Guidance for evaluating capabilities, safeguards, and evaluation validity on frontier systems.
- **[Anthropic releases Claude Opus 4.8 with sharper "honesty" calibration and dynamic workflows](https://www.itmedia.co.jp/aiplus/article/2605/29/2000000034/)** — Hundreds of parallel subagents and improved agentic coding ([Gigazine](https://gigazine.net/news/20260529-anthropic-claude-opus-4-8/)).
- **[Groq is raising $650M as it pivots from chips to inference](https://techcrunch.com/2026/05/29/after-nvidias-20b-not-acqui-hire-ai-chip-startup-groq-reportedly-raising-650m/)** — Internal round follows Nvidia's $20B not-acqui-hire.
- **[Google AI Studio publishes Gemini Omni & Gemini 3.5 demo reel](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-omni-3-5-videos/)** — Nine showcase demos for the latest multimodal models.
- **[Google fixes Gemini quota bugs that drained subscribers in minutes](https://the-decoder.com/google-fixes-several-bugs-in-gemini-usage-limits-that-burned-through-quotas-too-fast/)** — Ultra tier gets double the video generations and failed requests no longer bill.
- **[Nano Banana 2 and Nano Banana Pro hit general availability](https://gigazine.net/news/20260529-nano-banana-ga/)** — Google's image models leave preview; Nano Banana 2 previews video-to-image.
- **[Waymo launches its 6th-gen Ojai robotaxi to the public](https://gigazine.net/news/20260529-waymo-ojai/)** — General rollout following months of testing.
- **["AI psychosis" — Aaron Levie says CEOs misunderstand what they're cutting](https://techcrunch.com/video/what-happens-when-companies-become-too-ai-pilled/)** — ClickUp's 22% AI-driven layoff cited as the canonical case; 2026 tech layoffs already nearing all of 2025.
- **[One company reportedly spent $500M on Claude in one month](https://the-decoder.com/one-company-reportedly-spent-500-million-on-claude-in-one-month-after-failing-to-cap-ai-usage/)** — No usage caps + no model-selection expertise = runaway cost.
- **[Amazon kills its internal AI leaderboard after employees gamed it](https://the-decoder.com/amazon-kills-internal-ai-leaderboard-after-employees-gamed-it-with-pointless-tasks/)** — Workers ran pointless tasks to inflate scores, driving up internal cloud costs.
- **[Shift, an AI training startup, will clean your home for free in exchange for footage](https://www.theverge.com/ai-artificial-intelligence/939765/ai-training-data-startup-shift-free-cleaning)** — Stunt-priced labor for robot-training data ([Verge analysis](https://www.theverge.com/ai-artificial-intelligence/940007/ai-companies-will-pay-for-robot-training-data)).
- **[Cognition's Scott Wu: AI coding agents shouldn't replace humans](https://techcrunch.com/2026/05/29/cognitions-scott-wu-says-ai-coding-agents-shouldnt-replace-humans/)** — Counter-narrative from the maker of Devin.
- **[Glean tops $300M ARR as AI-budget-cutting becomes its pitch](https://techcrunch.com/2026/05/28/gleans-top-line-crosses-300m-as-ai-budget-cutting-becomes-its-major-selling-point/)** — Enterprise search startup triples revenue.
- **[XCENA raises $135M at a $570M valuation betting memory is AI's bottleneck](https://techcrunch.com/2026/05/29/xcena-secures-135m-at-570m-valuation-betting-on-memory-as-ais-real-bottleneck/)** — Korean chip startup with US ambitions.
- **[Apple is shrinking Gemini to run an in-house Siri on-device](https://gigazine.net/news/20260529-apple-massive-gemini-model-into-iphone-siri/)** — The Information says Apple's multi-year Google deal includes co-engineering for iPhone deployment.
- **[Boston Children's Hospital says GPT helped identify 40+ rare-disease diagnoses](https://openai.com/index/boston-childrens-hospital)** — Pediatric care case study.
- **[Pope Leo XIV's encyclical Magnifica Humanitas frames AI as a moral test](https://www.technologyreview.com/2026/05/29/1138107/how-the-popes-magnifica-humanitas-offers-a-template-for-individuals-to-meet-the-ai-moment/)** — "Technology is never neutral" — explicit charter for technologists and policymakers ([Rest of World context](https://restofworld.org/2026/pope-ai-encyclical/?utm_source=rss&utm_medium=rss&utm_campaign=feeds)).
- **[NVIDIA's Vera CPU outperforms AMD EPYC and Intel Xeon in early benchmarks](https://gigazine.net/news/20260529-nvidia-vera-benchmark/)** — Phoronix tests the AI-oriented chip ahead of late-2026 launch.
- **[NVIDIA releases LocateAnything for fast object detection on images and UIs](https://gigazine.net/news/20260529-nvidia-ai-locateanything/)** — Aimed at robotics and PC-automation pipelines.

### Europe

- **[EU fines Temu €200M (≈¥37B) for inadequate handling of illegal listings](https://gigazine.net/news/20260529-ec-fines-temu-200m-eur/)** — Commission cites weak risk assessment under the DSA.
- **[Mistral AI rebrands Le Chat as "Vibe" and folds in coding + work agents](https://gigazine.net/news/20260529-mistral-ai-vibe/)** — VS Code extension launches alongside Gmail-integrated info-gathering features.
- **[The Vatican publishes Pope Leo XIV's AI encyclical Magnifica Humanitas](https://www.technologyreview.com/2026/05/29/1138107/how-the-popes-magnifica-humanitas-offers-a-template-for-individuals-to-meet-the-ai-moment/)** — A direct intervention in the global AI-governance debate.

### Japan (AI & Tech only)

- **[OpenAI launches "Japan Cyber Action Plan," supplying GPT-5.5-Cyber to government and major banks](https://www.itmedia.co.jp/aiplus/article/2605/29/2000000037/)** — Cyber-specialized model deployed to Japanese financial institutions.
- **[Japanese government and top banks granted access to OpenAI's newest model](https://www.itmedia.co.jp/news/articles/2605/29/news144.html)** — Minister Katayama frames it as a defense against AI-augmented attacks.
- **[Fujitsu signs partnerships with OpenAI and Anthropic the same day](https://www.itmedia.co.jp/enterprise/articles/2605/29/news067.html)** — Aimed at combining frontier models with Fujitsu's own AI stack for enterprise.
- **[Digital Agency reopens its "Gen-nai" domestic LLM tender on a paid procurement basis](https://www.itmedia.co.jp/aiplus/article/2605/29/2000000036/)** — Evaluation expands from 50 to 300 questions for FY2027.
- **[Tokyo University spinoff Highlanders aims to mass-produce a domestic humanoid robot](https://www.itmedia.co.jp/aiplus/article/2605/29/2000000035/)** — Mitsubishi Motors among investors.
- **[Mitsui ramps up LNG investment to power AI data centers](https://www.japantimes.co.jp/business/2026/05/29/companies/mitsui-ceo-lng-investments/)** — CEO Hori cites "big additional demand" from clean-energy needs of AI infrastructure.
- **[Taiyo Yuden warns of "scary" AI-driven demand for MLCCs](https://www.japantimes.co.jp/business/2026/05/29/companies/taiyo-yuden-ai-demand/)** — Murata and Taiyo Yuden dominate supply of high-end multilayer ceramic capacitors essential for AI gear.
- **[Labor-shortage push fuels Japan's humanoid-robot investment wave](https://www.japantimes.co.jp/business/2026/05/29/tech/humanoids-summit-labor-shortages/)** — Declining birthrates drive an "unprecedented" capex cycle.
- **[JR West develops AI to automate hand-written rail-yard work plans](https://atmarkit.itmedia.co.jp/ait/articles/2605/29/news103.html)** — Replaces a niche but expert-only planning workflow.
- **[Microsoft's Foundry Local goes GA, offering on-device AI without token billing](https://atmarkit.itmedia.co.jp/ait/articles/2605/29/news075.html)** — Targeted at Japanese enterprises wary of cloud dependence.
- **[Obayashi tests RICOS's AI-CAE solution for wind-load prediction](https://monoist.itmedia.co.jp/mn/articles/2605/29/news025.html)** — AI accelerates structural design for tall buildings.
- **[IFS expands industrial-AI investment, calling Japan "a manufacturing powerhouse"](https://monoist.itmedia.co.jp/mn/articles/2605/29/news054.html)** — Partnership push with IBM Japan and others for asset-intensive industries.
- **[Anthropic's Opus 4.8 GA brings Mythos-tier safety to Japanese customers within weeks](https://www.itmedia.co.jp/news/articles/2605/29/news084.html)** — Tracks Anthropic's global rollout schedule.

---

## Research Papers

### Benchmarks & Evaluation

- **[BenchTrace: A Benchmark for Testing Reflection Ability and Controlled Evolution in LLM Agents](https://arxiv.org/abs/2605.29225)** — Goes beyond pass/fail to measure whether self-evolving agents actually learn from reflection, not just luck their way to a higher score.
- **[FinVerBench: Benchmark Validity and Calibration in LLM Financial Statement Verification](https://arxiv.org/abs/2605.29586)** — Stress-tests whether LLMs can decide if a set of corporate financial statements is internally consistent — and whether the benchmark itself is valid.

### Security & Adversarial

- **[Hijacking Agent Memory: Stealthy Trojan Attacks Through Conversational Interaction](https://arxiv.org/abs/2605.29960)** — Memory-poisoning attack on long-running LLM agents, planted purely through normal conversation.
- **[How Reliable Are AI Attackers Against a Fixed Vulnerable Target? A 400-Run Empirical Study of LLM Penetration Testing Consistency](https://arxiv.org/abs/2605.30096)** — First systematic look at how often LLM-driven pentest agents reproduce their own results — non-determinism is the dominant failure.
- **[Token Inflation: How Dishonest Providers Can Overcharge for LLM Usage](https://arxiv.org/abs/2605.30040)** — Per-token billing creates a real fraud vector: providers can silently inflate counts, and users have no good way to audit.

### Compliance & Regulation

- **[Citation-Closure Retrieval and Per-Rule Attribution for Real-World Regulatory Compliance QA](https://arxiv.org/abs/2605.29742)** — Deploying LLMs in compliance demands traceable citations across multi-tiered authorities; this paper formalizes the retrieval problem.
- **[Does Distributed Training Undermine Compute Governance?](https://arxiv.org/abs/2605.29359)** — Compute-governance proposals assume frontier training requires detectable clusters; the authors show distributed training algorithms may invalidate that assumption.

### Alignment & Safety

- **[BioRefusalAudit: Auditing Biosecurity Refusal Depth Using General and Domain-Fine-Tuned Sparse Autoencoders](https://arxiv.org/abs/2605.30162)** — Doesn't just ask whether a model refuses biohazard prompts but whether the refusal is *structurally sound* or surface-level.
- **[How Coding Agents Fail Their Users: A Large-Scale Analysis of Developer-Agent Misalignment in 20,574 Real-World Sessions](https://arxiv.org/abs/2605.29442)** — Production telemetry — not benchmark trajectories — used to characterize the way coding agents diverge from what developers actually want.

### Applications

- **[Agora: Toward Autonomous Bug Detection in Production-Level Consensus Protocols with LLM Agents](https://arxiv.org/abs/2605.29910)** — LLM agents find protocol-level bugs in distributed-systems code where conventional static analysis stalls.
- **[The Biosecurity Blind Spot: Systematic Dual-use Detection in Open Science Infrastructure](https://arxiv.org/abs/2605.28843)** — Maps the dual-use surface created when AI accelerates protein-prediction, genome-modeling, and drug-discovery pipelines in open repositories.

### Guardrails & Robustness

- **[Provably Secure Agent Guardrail](https://arxiv.org/abs/2605.29251)** — Argues that as LLMs gain execution privileges, classical input-output safety filters are no longer sufficient; offers a formal guarantee.
- **[Robust and Generalizable Safety Steering for Text-to-Image Diffusion Transformers](https://arxiv.org/abs/2605.30049)** — Layered diffusion makes prompt-level filters fragile; the authors steer the cross-modal pathway itself.

---

## Key Themes

- **Agentic security crystallizes as the new attack surface.** Hijacking long-running agent memory, prompt injection through ChatGPT's renderer, the first documented in-the-wild use of an LLM agent for hands-on-keyboard post-exploitation (Marimo CVE), and an empirical study of LLM-pentester reliability all land the same week — defenders and attackers are now both running LLMs inside the kill chain.
- **States take direct positions on AI.** Japan stands up an OpenAI-backed national cyber action plan, the EU fines Temu under the DSA, the Pope publishes an AI encyclical, and a research paper questions whether distributed training quietly undermines US compute-governance assumptions. Regulation is moving from drafting to operating.
- **Honesty and refusal depth as alignment targets.** Anthropic's Opus 4.8 ships a measurable jump in calibrated self-uncertainty, BioRefusalAudit examines whether biosecurity refusals are deep or theatrical, and OpenAI publishes its trusted-third-party-evaluation playbook — converging on *how* models say no, not just whether they do.
- **Frontier capability + frontier cost.** A single customer reportedly spent half a billion on Claude in a month, Amazon shutters a gamed internal AI leaderboard, and Glean's $300M run-rate is sold on AI-budget *cuts*. The economics of large-scale LLM deployment are being publicly stress-tested.
- **Robotics and physical-world AI move from demos to factories.** Humanoid-robot supply chains, Japan's domestic humanoid push, NVIDIA LocateAnything for robot perception, and dual-use biosecurity all signal that AI safety is now a physical-systems problem, not only a chatbot problem.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
