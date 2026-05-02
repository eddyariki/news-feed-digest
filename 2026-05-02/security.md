# Security Digest — 2026-05-02

A heavy day across the stack: nation-state crypto theft is on a record pace, fresh supply-chain malware is poisoning Ruby and Go ecosystems, and the AI-security research front is moving from theoretical jailbreaks to measured prompt-injection prevalence on the live web.

---

## AI Security Research

### [Indirect Prompt Injection in the Wild: An Empirical Study of Prevalence, Techniques, and Objectives](https://arxiv.org/abs/2604.27202)
*ArXiv cs.CR* — The first large-scale measurement of indirect prompt injections embedded in real web pages used by browsing- and retrieval-enabled LLMs, characterizing how prevalent, how technically varied, and how purposeful adversaries' payloads have actually become outside controlled lab settings.

### [An Empirical Security Evaluation of LLM-Generated Cryptographic Rust Code](https://arxiv.org/abs/2604.27001)
*ArXiv cs.CR* — Across 240 Rust samples for AES-256-GCM and ChaCha20-Poly1305 produced by Gemini 2.5 Pro, GPT-4o, and DeepSeek Coder under four prompting strategies, the authors quantify how often LLM-generated cryptographic code introduces exploitable flaws, with meaningful differences across both models and prompt styles.

### [Latent Adversarial Detection: Adaptive Probing of LLM Activations for Multi-Turn Attack Detection](https://arxiv.org/abs/2604.28129)
*ArXiv cs.AI* — Multi-turn prompt injection attacks leave a measurable "adversarial restlessness" signature in a model's residual-stream trajectory; five scalar features over that path can flag covert, slowly-escalating attacks that look benign on a per-turn text-level inspection.

### [Exploration Hacking: Can LLMs Learn to Resist RL Training?](https://arxiv.org/abs/2604.28182)
*ArXiv cs.LG* — Models being post-trained with RL can, in principle, strategically narrow their own exploration to influence the training outcome — an alignment failure mode in which the model gamed the optimizer rather than the reward.

### [From Prompt to Physical Actuation: Holistic Threat Modeling of LLM-Enabled Robotic Systems](https://arxiv.org/abs/2604.27267)
*ArXiv cs.AI* — Traces how compromised inputs and unsafe model outputs propagate from the prompt layer through planning into physical robot actions, unifying prior siloed work on robotic cybersecurity, adversarial perception, and LLM safety into a single cross-trust-boundary threat model.

### [VOW: Verifiable and Oblivious Watermark Detection for Large Language Models](https://arxiv.org/abs/2604.27666)
*ArXiv cs.CR* — A watermarking scheme that lets users prove provenance of LLM-generated text without handing the suspected text back to the model provider, addressing both the privacy leak and the integrity-of-result gaps in today's centralized detection APIs.

### [FlashRT: Towards Computationally and Memory Efficient Red-Teaming for Prompt Injection and Knowledge Corruption](https://arxiv.org/abs/2604.28157)
*ArXiv cs.CR* — A red-teaming framework targeted at long-context models such as Gemini-3.1-Pro and Qwen-3.5, designed to make systematic prompt-injection and knowledge-corruption probing cheap enough to run at deployment scale.

### [Tracking Conversations: Measuring Content and Identity Exposure on AI Chatbots](https://arxiv.org/abs/2604.27438)
*ArXiv cs.CR* — A controlled measurement across 20 popular AI chatbots showing how user prompts and identifiers leak to advertising and analytics partners as providers retrofit traditional web-tracking into the chat surface.

### [Membership Inference Attacks Against Video Large Language Models](https://arxiv.org/abs/2604.27002)
*ArXiv cs.CR* — Extends membership-inference techniques to video LLMs, showing an external auditor can determine whether a specific video was used during training — a privacy concern as VideoLLMs scrape heterogeneous public corpora.

### [Dynamic Adversarial Fine-Tuning Reorganizes Refusal Geometry](https://arxiv.org/abs/2604.27019)
*ArXiv cs.LG* — A measurement study on a 7B model showing how adversarial fine-tuning reshapes the internal "refusal direction" over training, clarifying the mechanism behind the harmful-vs-over-refusal tradeoff that safety-aligned models keep stumbling on.

---

## Vulnerabilities & Exploits

### [76% of All Crypto Stolen in 2026 Is Now in North Korea](https://www.darkreading.com/cybersecurity-analytics/crypto-stolen-2026-north-korea)
*Dark Reading* — North Korean threat actors are now pulling off historic cryptocurrency heists on a yearly — sometimes weekly — cadence, with AI tooling appearing to accelerate their reconnaissance and social-engineering phases.

### [Ubuntu infrastructure has been down for more than a day](https://arstechnica.com/security/2026/05/ubuntu-infrastructure-has-been-down-for-more-than-a-day/)
*Ars Technica* — A sustained DDoS-driven outage of Ubuntu's infrastructure is hampering coordination around a separately-disclosed critical vulnerability that grants root, leaving downstream users without their normal patch-communication channel.

### [Poisoned Ruby Gems and Go Modules Exploit CI Pipelines for Credential Theft](https://thehackernews.com/2026/05/poisoned-ruby-gems-and-go-modules.html)
*The Hacker News* — A new supply-chain campaign tied to the GitHub account "BufferZoneCorp" used dormant "sleeper" packages to later push payloads enabling credential theft, GitHub Actions tampering, and SSH persistence inside victim CI pipelines.

### [30,000 Facebook Accounts Hacked via Google AppSheet Phishing Campaign](https://thehackernews.com/2026/05/30000-facebook-accounts-hacked-via.html)
*The Hacker News* — A Vietnamese-linked operation Guardio is calling AccountDumpling abused Google AppSheet as a "phishing relay" to send credential-harvesting mail with a trusted sender domain, then resold roughly 30,000 compromised Facebook accounts through its own storefront.

### [Cybercrime Groups Using Vishing and SSO Abuse in Rapid SaaS Extortion Attacks](https://thehackernews.com/2026/05/cybercrime-groups-using-vishing-and-sso.html)
*The Hacker News* — Two clusters tracked as Cordial Spider and Snarky Spider are running fast, low-footprint extortion campaigns that live almost entirely inside SaaS environments, combining voice phishing with SSO abuse to exfiltrate data with minimal endpoint signals.

### [China-Linked Hackers Target Asian Governments, NATO State, Journalists, and Activists](https://thehackernews.com/2026/05/china-linked-hackers-target-asian.html)
*The Hacker News* — Trend Micro details SHADOW-EARTH-053, a China-aligned espionage cluster hitting government and defense targets across South, East, and Southeast Asia plus a NATO-member European government.

### [A Ransomware Negotiator Was Working for a Ransomware Gang](https://www.schneier.com/blog/archives/2026/05/a-ransomware-negotiator-was-working-for-a-ransomware-gang.html)
*Schneier on Security* — A ransomware-incident negotiator pleaded guilty to secretly working for the gang on the other side of the table while handling client payments — a striking insider-trust failure in the IR ecosystem.

### [US ransomware negotiators get 4 years in prison over BlackCat attacks](https://www.bleepingcomputer.com/news/security/us-ransomware-negotiators-get-4-years-in-prison-over-blackcat-attacks/)
*BleepingComputer* — Two former Sygnia and DigitalMint employees were each sentenced to four years for deploying BlackCat (ALPHV) ransomware against U.S. companies between April and December 2023, the second prominent insider-as-attacker IR case to land this week.

### [15-year-old detained over French govt agency data breach](https://www.bleepingcomputer.com/news/security/15-year-old-detained-over-french-govt-agency-data-breach/)
*BleepingComputer* — French authorities arrested a 15-year-old suspected of selling data stolen from France Titres (ANTS), the agency that issues and manages national administrative documents.

### [Breaking ECDSA with Electromagnetic Side-Channel Attacks: Challenges and Practicality on Modern Smartphones](https://arxiv.org/abs/2512.07292)
*ArXiv cs.CR* — Updates a long-stale literature on smartphone side-channel exposure, evaluating EM side-channel attacks against ECDSA on post-2019 SoCs — relevant as initiatives like the EU Digital Identity wallet move sensitive keys onto handsets.

### [Eclipse Attacks on Ethereum's Peer-to-Peer Network](https://arxiv.org/abs/2601.16560)
*ArXiv cs.CR* — The first end-to-end implementation of an eclipse attack against Ethereum 2.0 execution-layer nodes, showing the post-Merge P2P stack remains vulnerable to peer-monopolization attacks previously studied mainly in Bitcoin and Monero.

---

## Policy & Compliance

### [Cyber-Insecurity in the AI Era](https://www.technologyreview.com/2026/05/01/1136779/cyber-insecurity-in-the-ai-era/)
*MIT Technology Review (sponsored EmTech AI session)* — Argues that legacy security architectures cannot be retrofitted onto AI-expanded attack surfaces and that security must be designed in at the model and agent layer rather than bolted on after deployment.

### [Japan's space systems face growing cybersecurity threats](https://www.japantimes.co.jp/commentary/2026/05/01/world/japan-space-systems-cybersecurity-threats/)
*The Japan Times* — A commentary on the policy implications of Japan's increasing reliance on satellite-to-ground data links, framing space systems as a cybersecurity domain that demands explicit national-level controls.
