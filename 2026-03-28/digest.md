# AI News Digest — 2026-03-28

## Highlights

- **[Anthropic Leak Reveals "Claude Mythos"](https://the-decoder.com/anthropic-leak-reveals-new-model-claude-mythos-with-dramatically-higher-scores-on-tests-than-any-previous-model/)**: Leaked Anthropic draft posts reveal a new model class above Opus with "dramatically higher scores on tests," a deliberate slow-release strategy, and a strong cybersecurity focus.
- **[Federal Judge Blocks Trump's Ban on Anthropic AI Models](https://the-decoder.com/federal-judge-blocks-trumps-ban-on-anthropic-ai-models-calls-security-risk-label-orwellian/)**: A San Francisco judge called the government's "national security risk" label for Anthropic "Orwellian," ruling it constituted illegal First Amendment retaliation.
- **[LangChain and LangGraph Flaws Expose Files, Secrets, and Databases](https://thehackernews.com/2026/03/langchain-langgraph-flaws-expose-files.html)**: Three newly disclosed vulnerabilities in widely deployed AI orchestration frameworks could expose filesystem data, environment secrets, and conversation history.
- **[SoftBank's $40B Loan Points to a 2026 OpenAI IPO](https://techcrunch.com/2026/03/27/why-softbanks-new-40b-loan-points-to-a-2026-openai-ipo/)**: JPMorgan and Goldman Sachs are extending a 12-month unsecured loan to SoftBank, widely read as financial preparation for an OpenAI public offering.
- **[ARC-AGI-3 Sets a New Bar for Agentic Intelligence](https://arxiv.org/abs/2603.24621)**: A successor to ARC-AGI-1/2 evaluates frontier models on turn-based abstract environments requiring goal inference and planning without explicit instructions.

---

## News

### AI Security

- **[LangChain and LangGraph Flaws Expose Files, Secrets, Databases in Widely Used AI Frameworks](https://thehackernews.com/2026/03/langchain-langgraph-flaws-expose-files.html)** (The Hacker News) — Three vulnerabilities in LangChain and LangGraph could allow attackers to access filesystem data, environment secrets, and conversation histories in deployed AI applications.

- **[Anthropic Leak Reveals "Claude Mythos"](https://the-decoder.com/anthropic-leak-reveals-new-model-claude-mythos-with-dramatically-higher-scores-on-tests-than-any-previous-model/)** (The Decoder) — Leaked internal documents show Anthropic's next-generation model above Opus, with cybersecurity capabilities as a central design priority and a deliberately cautious release plan.

- **[Backdoored Telnyx PyPI Package Pushes Malware Hidden in WAV Audio](https://www.bleepingcomputer.com/news/security/backdoored-telnyx-pypi-package-pushes-malware-hidden-in-wav-audio/)** (BleepingComputer) — TeamPCP — the group behind earlier supply chain attacks on Trivy, KICS, and litellm — compromised the Telnyx Python package on PyPI, hiding credential-stealing malware inside a WAV file.

- **[Open VSX Bug Let Malicious VS Code Extensions Bypass Pre-Publish Security Checks](https://thehackernews.com/2026/03/open-vsx-bug-let-malicious-vs-code.html)** (The Hacker News) — A now-patched flaw caused Open VSX's scanner pipeline to treat "no scanners configured" identically to "all scanners passed," allowing malicious extensions to clear vetting.

- **[Fake VS Code Alerts on GitHub Spread Malware to Developers](https://www.bleepingcomputer.com/news/security/fake-vs-code-alerts-on-github-spread-malware-to-developers/)** (BleepingComputer) — A large-scale campaign is posting fabricated Visual Studio Code security alerts in GitHub Discussions to trick developers into downloading malware.

- **[China Upgrades the Backdoor It Uses to Spy on Telcos Globally](https://www.darkreading.com/threat-intelligence/china-upgrades-backdoor-spy-telcos)** (Dark Reading) — Chinese APT Red Menshen's upgraded BPFdoor malware defeats traditional endpoint protections, with telcos left mainly to hunt for signs of compromise after the fact.

- **[AitM Phishing Targets TikTok Business Accounts Using Cloudflare Turnstile Evasion](https://thehackernews.com/2026/03/aitm-phishing-targets-tiktok-business.html)** (The Hacker News) — Adversary-in-the-middle phishing pages are hijacking TikTok for Business accounts by bypassing Cloudflare's bot protection, enabling follow-on malvertising campaigns.

- **[Google Sets 2029 Deadline for Quantum-Safe Cryptography](https://www.darkreading.com/application-security/google-2029-deadline-quantum-safe-cryptography)** (Dark Reading) — Google plans to complete its migration to post-quantum cryptography across its infrastructure by 2029, signaling an accelerating enterprise timeline for PQC adoption.

- **[Apple Sends Lock Screen Alerts to Outdated iPhones Over Active Web-Based Exploits](https://thehackernews.com/2026/03/apple-sends-lock-screen-alerts-to.html)** (The Hacker News) — Apple is proactively pushing on-device notifications warning users of active attacks targeting unpatched iOS versions, urging immediate updates.

- **[Agentic GRC: Teams Get the Tech. The Mindset Shift Is What's Missing.](https://www.bleepingcomputer.com/news/security/agentic-grc-teams-get-the-tech-the-mindset-shift-is-whats-missing/)** (BleepingComputer) — As agentic AI automates GRC workflows, the real gap is shifting security teams from operational execution to risk leadership and strategic oversight.

### USA

- **[Federal Judge Blocks Trump's Ban on Anthropic AI Models, Calls Security Risk Label "Orwellian"](https://the-decoder.com/federal-judge-blocks-trumps-ban-on-anthropic-ai-models-calls-security-risk-label-orwellian/)** (The Decoder) — Judge Rita F. Lin rejected the government's designation of Anthropic as a "potential adversary and saboteur," ruling the ban constituted illegal First Amendment retaliation for policy criticism.

- **[Why SoftBank's New $40B Loan Points to a 2026 OpenAI IPO](https://techcrunch.com/2026/03/27/why-softbanks-new-40b-loan-points-to-a-2026-openai-ipo/)** (TechCrunch AI) — Wall Street's involvement in an unsecured 12-month SoftBank loan is widely interpreted as financial positioning ahead of an OpenAI public offering later this year.

- **[OpenAI Shuts Down Sora While Meta Gets Shut Out in Court](https://techcrunch.com/video/openai-shuts-down-sora-while-meta-gets-shut-out-in-court/)** (TechCrunch AI) — OpenAI is discontinuing its Sora video generation product while broader tensions around AI infrastructure expansion and legal battles continue.

- **[The Latest in Data Centers, AI, and Energy](https://www.theverge.com/ai-artificial-intelligence/902546/data-centers-ai-energy-power-grids-controversy)** (The Verge AI) — The rapid buildout of AI data centers is sparking global disputes over power grid strain, utility costs, community impact, and environmental consequences.

- **[Meta's Own Supervisory Body Warns That Community Notes Are No Match for AI Disinformation](https://the-decoder.com/metas-own-supervisory-body-warns-that-community-notes-are-no-match-for-ai-disinformation/)** (The Decoder) — Meta's Oversight Board found Community Notes too slow, understaffed, and manipulable to combat AI-generated disinformation, recommending against rollout in certain countries.

- **[Meta's New AI Model Predicts How Your Brain Reacts to Images, Sounds, and Speech](https://the-decoder.com/metas-new-ai-model-predicts-how-your-brain-reacts-to-images-sounds-and-speech/)** (The Decoder) — Meta's multimodal brain-response model matches the typical brain reaction to stimuli more accurately than an actual scan of any single individual.

- **[Google's New Gemini Update Makes It Easy to Import Memories from ChatGPT and Claude](https://the-decoder.com/googles-new-gemini-update-makes-it-easy-to-import-memories-from-chatgpt-and-claude/)** (The Decoder) — Google and Anthropic are both enabling one-command export of saved user data, making it simpler for ChatGPT users to switch to competing assistants.

- **[OpenAI's Codex Gets a Plugin Marketplace for Slack, Notion, Figma, and More](https://the-decoder.com/openais-codex-gets-a-plugin-marketplace-for-slack-notion-figma-and-more/)** (The Decoder) — OpenAI is adding a plugin marketplace to Codex, integrating widely used productivity and design tools including Slack, Figma, Notion, Gmail, and Google Drive.

- **[Cohere Releases Open Source Model That Tops Speech Recognition Benchmarks](https://the-decoder.com/cohere-releases-open-source-model-that-tops-speech-recognition-benchmarks/)** (The Decoder) — Cohere's new open-source ASR model outperforms all competitors on standard benchmarks, including OpenAI's Whisper.

- **[Suno 5.5 Lets Users Sing Their Own AI-Generated Songs with a Personalized Voice Feature](https://the-decoder.com/suno-5-5-lets-users-sing-their-own-ai-generated-songs-with-a-personalized-voice-feature/)** (The Decoder) — Suno v5.5 allows users to train the model on their personal vocal style and automatically adapts generated outputs to match their taste and voice.

- **[Memory Chip Giant SK Hynix Could Help End 'RAMmageddon' with Blockbuster US IPO](https://techcrunch.com/2026/03/27/memory-chip-giant-sk-hynix-could-help-end-rammageddon-with-blockbuster-us-ipo/)** (TechCrunch AI) — SK Hynix's potential US listing targeting $10–$14 billion could fund capacity expansion to ease the AI-driven HBM memory shortage.

### Europe

- **[European Commission Investigating Breach After Amazon Cloud Account Hack](https://www.bleepingcomputer.com/news/security/european-commission-investigating-breach-after-amazon-cloud-account-hack/)** (BleepingComputer) — The EU's main executive body is probing an intrusion after a threat actor gained access to the Commission's Amazon Web Services cloud environment.

- **[Dutch Police Discloses Security Breach After Phishing Attack](https://www.bleepingcomputer.com/news/security/dutch-police-discloses-security-breach-after-phishing-attack/)** (BleepingComputer) — The Dutch National Police confirmed a limited-impact breach stemming from a successful phishing attack; citizen data was not affected.

### Japan (AI & Tech)

- **[Wikipedia Bans LLM-Generated Article Writing](https://www.itmedia.co.jp/news/articles/2603/27/news100.html)** (ITmedia AI+) — The Wikimedia Foundation published guidelines effectively prohibiting LLM use for creating or rewriting Wikipedia articles, allowing narrow exceptions only for self-correction of AI output and cross-language translation assistance.

- **[GitHub Copilot Data to Be Used for AI Training](https://www.itmedia.co.jp/aiplus/articles/2603/27/news092.html)** (ITmedia AI+) — Microsoft's GitHub announced it will use Copilot input and output data on individual plans for AI model training; users can opt out via account settings.

- **[Apple Provided "Hide My Email" Users' Real Names and Addresses to FBI](https://gigazine.net/news/20260327-apple-gives-fbi-user-real-name-hide-my-email/)** (Gigazine) — Despite Apple's privacy-preserving "Hide My Email" feature, the company disclosed users' real names and email addresses to federal law enforcement under a legal request, according to a report by 404 Media.

---

## Research Papers

### Benchmarks & Evaluation

- **[ARC-AGI-3: A New Challenge for Frontier Agentic Intelligence](https://arxiv.org/abs/2603.24621)** — Introduces a turn-based abstract benchmark requiring models to infer goals, model environments, and plan actions without explicit instructions — raising the bar beyond ARC-AGI-1/2 for measuring genuine agentic capabilities.

- **[RubricEval: A Rubric-Level Meta-Evaluation Benchmark for LLM Judges in Instruction Following](https://arxiv.org/abs/2603.25133)** — Proposes a meta-evaluation framework for rubric-based LLM judges, revealing fine-grained judgment gaps that coarser response-level evaluations miss.

- **[TRAJEVAL: Decomposing Code Agent Trajectories for Fine-Grained Diagnosis](https://arxiv.org/abs/2603.24631)** — Decomposes code agent execution into search, edit, and validation stages, replacing binary pass/fail metrics with interpretable failure analysis at each step.

- **[FinMCP-Bench: Benchmarking LLM Agents for Real-World Financial Tool Use under the Model Context Protocol](https://arxiv.org/abs/2603.24943)** — A 613-sample benchmark across 10 financial scenarios and 65 real MCP tools, evaluating LLM agents on actual tool invocation fidelity in financial workflows.

### Security & Adversarial

- **[AIP: Agent Identity Protocol for Verifiable Delegation Across MCP and A2A](https://arxiv.org/abs/2603.24775)** — A survey of ~2,000 MCP servers found zero with authentication; proposes a public-key verifiable delegation protocol for AI agent identity across Model Context Protocol and Agent-to-Agent frameworks.

- **[Malicious LLM-Based Conversational AI Makes Users Reveal Personal Information](https://arxiv.org/abs/2506.11680)** — Demonstrates that LLM chatbots can be deliberately engineered to elicit sensitive personal disclosures from users, establishing a novel and underexplored adversarial threat category.

- **[Beyond Content Safety: Real-Time Monitoring for Reasoning Vulnerabilities in Large Language Models](https://arxiv.org/abs/2603.25412)** — Identifies "reasoning safety" as orthogonal to content safety, proposing real-time monitoring of chain-of-thought reasoning chains for vulnerabilities beyond harmful output detection.

### Compliance & Regulation

- **[A Public Theory of Distillation Resistance via Constraint-Coupled Reasoning Architectures](https://arxiv.org/abs/2603.25022)** — Presents an architectural framework for preventing capability transfer via knowledge distillation without transferring governance constraints, addressing model extraction risks at the design level.

### Alignment & Safety

- **[Evaluating Language Models for Harmful Manipulation](https://arxiv.org/abs/2603.25326)** — A large-scale evaluation framework (10,101 participants across the US, UK, and a third locale) for measuring AI-driven manipulation in public policy, finance, and health contexts.

- **[Trust as Monitoring: Evolutionary Dynamics of User Trust and AI Developer Behaviour](https://arxiv.org/abs/2603.24742)** — Models user trust as reduced monitoring in repeated AI interactions and examines the evolutionary incentive dynamics that shape safe AI development and effective governance design.

### Applications

- **[The Competence Shadow: Theory and Bounds of AI Assistance in Safety Engineering](https://arxiv.org/abs/2603.25197)** — Develops a formal framework for AI assistance in safety analysis, arguing that safety engineering resists benchmark-driven evaluation and that AI assistance may introduce systematic blind spots that emerge only post-deployment.

### Guardrails & Robustness

- **[Mechanistically Interpreting Compression in Vision-Language Models](https://arxiv.org/abs/2603.25035)** — Uses causal circuit analysis and crosscoder feature comparisons to examine how model compression (pruning and quantization) alters safety-relevant behaviors and internal computations in VLMs.

---

## Key Themes

- **AI Governance Under Legal Pressure**: A federal judge's rebuke of the Trump administration's Anthropic ban and Wikimedia's LLM policy both reflect accelerating institutional pushback against AI regulation overreach — and underreach.
- **Supply Chain Attacks Target AI Tooling**: TeamPCP's compromised Telnyx PyPI package and the Open VSX scanner flaw illustrate how attackers are increasingly targeting AI/ML developer infrastructure specifically.
- **AI Infrastructure Race and Backlash**: From SK Hynix's IPO to data center land disputes, the physical and financial buildout for AI is generating real-world friction at every level.
- **Agentic AI Security Gaps**: Research on MCP server authentication failures, LangChain/LangGraph vulnerabilities, and reasoning-chain safety monitoring all point to a maturing but under-secured agentic AI ecosystem.
- **Model Capability Arms Race Continues**: The Claude Mythos leak and ARC-AGI-3 benchmark both signal that the frontier of AI capability — and the methods for measuring it — are advancing rapidly.

---
*For detailed summaries of selected research papers, see [papers.md](papers.md).*
