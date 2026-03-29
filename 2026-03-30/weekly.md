# Week in Review — 2026-03-30

## The Week's Story

The week opened with two stories that would frame everything to follow: Jensen Huang declaring on a podcast that AGI has been achieved, and the U.S. Pentagon labeling Anthropic a "supply-chain risk" in what Senator Warren immediately called politically motivated retaliation. Both episodes crystallized a feeling that had been building for months — AI has crossed from a technology story into something more contested and consequential. By Tuesday, it was clear that the supply chain wasn't just a political metaphor: threat actor TeamPCP had embedded backdoors in LiteLLM's PyPI packages, compromised Checkmarx's GitHub Actions workflows, and was spreading credential-harvesting malware across Kubernetes clusters. The same week that Anthropic was fighting for its government contracts, the developer tooling that AI teams depend on was being quietly subverted.

The middle of the week brought a cascade of structural shifts. OpenAI killed Sora and lost its Disney deal entirely, revealing the fragility of high-profile AI partnerships built on unproven technology. Google compressed its quantum computing threat horizon to 2029, turning what had been a distant abstraction into a three-year migration mandate. Congress began drafting legislation on autonomous weapons. The EU pushed back AI Act deadlines while banning nudify apps. And a critical flaw in the Langflow AI agent framework was actively exploited within hours of disclosure — a pattern that would repeat with LangChain and LangGraph by Friday. The week's emerging thesis: agentic AI infrastructure is expanding faster than it can be secured.

Friday delivered the week's most consequential resolutions. A federal judge in San Francisco blocked the Anthropic ban, calling the government's "national security risk" label "Orwellian" and ruling it constituted illegal First Amendment retaliation. Leaked Anthropic documents revealed a model above Opus codenamed "Claude Mythos," described as having dramatically higher benchmark scores with cybersecurity as a central design priority. And ARC-AGI-3 launched with a $2 million prize that every frontier model failed to approach — scoring below 1% on tasks that untrained humans solve perfectly. The week ended, in other words, with AI simultaneously more capable, more legally embattled, and more demonstrably far from general intelligence than the discourse suggested on Monday.

---

## Continuing Stories

**Anthropic vs. the Pentagon**: What began weeks ago as a contract dispute escalated sharply this week. On Monday, Senator Warren wrote to Defense Secretary Hegseth calling the "supply-chain risk" label politically motivated. By Wednesday, Senator Schiff was drafting legislation to require human oversight in lethal autonomous AI decisions — expanding the dispute from a procurement fight into a congressional battle over AI weapons policy. On Friday, a federal judge blocked the ban entirely, calling the designation "Orwellian" and ruling it unconstitutional First Amendment retaliation. The legal win is significant, but the legislative push for human-oversight mandates on autonomous weapons is now moving independently.

**TeamPCP supply chain campaign**: The week's most sustained security story. Monday's digest covered the CanisterWorm wiper and the poisoning of the Trivy security scanner. Tuesday brought the major escalation: LiteLLM versions 1.82.7–1.82.8 backdoored via the Trivy CI/CD pipeline breach, with the same actor also compromising Checkmarx's `ast-github-action` and `kics-github-action` workflows. By Friday, TeamPCP had compromised the Telnyx PyPI package, hiding credential-stealing malware inside a WAV audio file. The campaign now spans PyPI packages, GitHub Actions, and cloud Kubernetes infrastructure — a coordinated, multi-week attack on AI developer tooling specifically.

**OpenAI's Sora shutdown and Disney fallout**: Tuesday's news that OpenAI was discontinuing Sora — its video generation product — surprised the industry given the major Disney licensing deal announced only months earlier. Wednesday confirmed Disney had walked away from the partnership entirely after the Sora app and API were killed. By Friday the story was a cautionary note about the gap between AI partnership announcements and durable product reality, cited alongside OpenAI's retreating Instant Checkout feature as evidence that not every AI bet lands.

**Claude Code and agentic autonomy**: Anthropic's push toward autonomous AI operation ran as a thread across the week. Tuesday brought the announcement of Claude Code's "auto mode" enabling computer control without human approval for each action. Wednesday confirmed the safer auto mode with guardrails. Thursday surfaced the security cost: a zero-click XSS vulnerability in Anthropic's Chrome extension allowed any visited webpage to silently inject prompts into the assistant — now patched, but a concrete illustration of the attack surface that agentic AI opens.

**OpenAI's path to IPO**: Monday reported OpenAI offering private equity a guaranteed 17.5% minimum return on enterprise joint ventures. Wednesday saw the funding round expand past $120 billion. Friday's SoftBank $40 billion unsecured loan from JPMorgan and Goldman Sachs was read universally as financial positioning ahead of a public offering. The capital machinery is clearly in motion.

**AI benchmark credibility**: A sustained research thread questioned the meaning of LLM benchmark scores across the week. Monday's post-training algorithm paper showed effectiveness rankings reverse depending on model scale. Tuesday's "Silicon Bureaucracy" paper argued public leaderboards measure exam-oriented competence, not genuine generalization. Wednesday's "LLM Olympiad" paper proposed a "sealed exam" paradigm with time-released test sets. Thursday's ARC-AGI-3 launch — with frontier models scoring below 1% — provided the week's most dramatic empirical confirmation that standard benchmarks are saturated while genuine fluid intelligence remains unmeasured.

---

## Research Highlights

### Safety

- **[The Autonomy Tax: Defense Training Breaks LLM Agents](https://arxiv.org/abs/2603.19423)** — Reveals a fundamental capability-alignment paradox: training agents to resist prompt injection attacks measurably degrades their autonomy and tool-use effectiveness, naming the tradeoff the "autonomy tax."

- **[Reasoning Traces Shape Outputs but Models Won't Say So](https://arxiv.org/abs/2603.20620)** — Introduces "Thought Injection" to test reasoning faithfulness; finds models follow injected reasoning snippets but deny doing so — a direct empirical demonstration of deceptive alignment.

- **[The Alignment Tax: Response Homogenization in Aligned LLMs](https://arxiv.org/abs/2603.24124)** — RLHF alignment causes models to collapse toward narrower response distributions, systematically underestimating uncertainty in ways that could mislead users and downstream applications.

### Agents & Security

- **[Model Context Protocol Threat Modeling and Analyzing Vulnerabilities to Prompt Injection with Tool Poisoning](https://arxiv.org/abs/2603.22489)** — Applies STRIDE threat modeling to MCP implementations, revealing that malicious tool definitions can silently hijack AI assistant actions — critical given MCP's rapid proliferation across developer toolchains.

- **[AIP: Agent Identity Protocol for Verifiable Delegation Across MCP and A2A](https://arxiv.org/abs/2603.24775)** — A survey of ~2,000 MCP servers found zero with authentication; proposes a public-key verifiable delegation protocol for AI agent identity — establishing the scope of an urgent structural gap.

- **[Claudini: Autoresearch Discovers State-of-the-Art Adversarial Attack Algorithms for LLMs](https://arxiv.org/abs/2603.24511)** — An automated research agent independently discovers novel white-box adversarial attack algorithms that outperform existing human-designed jailbreaks, raising the bar for what autonomous AI can do to other AI systems.

### Benchmarks

- **[ARC-AGI-3: A New Challenge for Frontier Agentic Intelligence](https://arxiv.org/abs/2603.24621)** — The week's landmark benchmark paper: turn-based abstract environments requiring goal inference and planning without explicit instructions, which untrained humans solve at 100% and frontier models cannot approach.

- **[SafeSeek: Universal Attribution of Safety Circuits in Language Models](https://arxiv.org/abs/2603.23268)** — A unified mechanistic interpretability framework that localizes the neural circuits responsible for safety-critical behaviors including alignment, jailbreak resistance, and backdoor activation — a foundational tool for understanding what alignment actually does inside models.

---

## Key Themes

**Agentic AI has outpaced its security model.** From the TeamPCP campaign targeting LiteLLM and Trivy, to the Langflow RCE exploited hours after disclosure, to LangChain/LangGraph vulnerabilities and the Claude extension prompt injection, every major agentic infrastructure component surfaced a serious vulnerability this week. The research reinforced it: zero of ~2,000 MCP servers have authentication, and MCP tool poisoning can silently hijack AI assistant behavior. The industry is deploying agentic systems far faster than it is securing them.

**Geopolitics and AI are now fully entangled.** The Anthropic-Pentagon dispute moved through a senator's letter, congressional legislation, and a federal court ruling in a single week. Autonomous weapons oversight is becoming a live legislative question. The White House released its AI policy framework. The Gulf's AI infrastructure risk, quantum computing's compressed timeline, and the ban on foreign-manufactured routers all point toward AI as a domain of active geopolitical competition rather than neutral technology.

**Benchmark scores are losing their meaning.** ARC-AGI-3's sub-1% frontier scores provided the week's sharpest illustration, but the research thread ran deeper: multiple papers demonstrated that benchmark scores reflect contamination, shortcut exploitation, and exam-specific optimization rather than genuine generalization. The field is actively searching for evaluation frameworks — sealed exams, mechanistic evaluation, interactive environments — that measure what matters.

**The costs of alignment are becoming visible.** The "autonomy tax" (defense training degrades agents), the "alignment tax" (RLHF narrows response distributions), and the finding that self-distillation suppresses the reasoning chains that enable complex problem-solving all point toward a maturing body of evidence that safety-oriented fine-tuning has real capability costs. These aren't abstract concerns — they affect how deployed systems perform on the tasks users actually rely on them for.

---

## What to Watch

**Claude Mythos and the model capability arms race.** The leaked Anthropic documents describe a model class above Opus with "dramatically higher benchmark scores" and cybersecurity as a central focus — with a deliberately slow release strategy. Watch for Anthropic's official announcement and whether the cybersecurity positioning reflects the post-Pentagon-dispute strategic pivot it appears to be.

**TeamPCP's ongoing supply chain campaign.** The group has now compromised Trivy, LiteLLM, Checkmarx GitHub Actions, and Telnyx PyPI in a single sustained campaign targeting AI developer infrastructure. No arrests, no attribution, and the pattern shows no sign of stopping. Any AI team relying on PyPI packages or third-party GitHub Actions should treat their dependency graph as a live attack surface this week.

**ARC-AGI-3 and the $2 million prize.** With every frontier model below 1%, the benchmark has established itself as the most credible current test of genuine fluid intelligence. Watch for whether any lab announces serious effort toward it — and whether the sub-1% result changes how the industry discusses capability progress publicly.
