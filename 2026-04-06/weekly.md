# Week in Review — 2026-04-06

## The Week's Story

The week opened with friction and closed with consolidation. On Monday, a California judge blocked the Pentagon from labeling Anthropic a supply chain risk — an early signal that AI companies were no longer just technology firms but contested geopolitical actors. By Tuesday, that framing had been overtaken by a more immediate supply chain story: the Axios npm package serving 100 million downloads weekly had been compromised by North Korean operatives, injecting cross-platform remote access trojans into the developer ecosystem. The same day, OpenAI announced a $122 billion funding round at an $852 billion valuation, signaling that whatever the security risks, the infrastructure race was accelerating without pause. The week's opening tension — between the maturity of AI deployment and the immaturity of its security posture — never resolved; it compounded.

Anthropic's week illustrated the tension most vividly. A packaging error on Tuesday exposed Claude Code source code, which by Wednesday had been forked over 8,000 times and was actively being used by threat actors to push infostealer malware through GitHub repositories by Thursday. The incident grew from an embarrassing internal slip into a case study in AI tooling supply chain risk, drawing industry-wide calls to treat AI development infrastructure as critical infrastructure. Yet by Friday, Anthropic had pivoted sharply: a $400 million acquisition of biotech startup Coefficient Bio, a new political action committee, and the launch of desktop computer-use capabilities across Claude Code and Cowork. The same company that spent three days in incident response mode ended the week making the most aggressive strategic moves of any AI lab.

By Friday, two structural stories had fully crystallized. The first was the normalization of agentic AI attack surfaces: OpenClaw's unauthenticated admin-access vulnerability, the ShadowPrompt Chrome extension flaw, Google DeepMind's taxonomy of six agent hijacking patterns, and Vertex AI's over-privilege problem collectively described an industry where autonomous systems were being deployed far faster than the security frameworks to govern them. The second was hardware geopolitics: DeepSeek v4's announcement that it would run exclusively on Huawei chips — as Chinese domestic AI accelerators crossed 41% market share — marked a concrete inflection point in China's semiconductor independence, not a future aspiration. Taken together, the week suggested that the AI industry's center of gravity was shifting from model capability to infrastructure, security, and geopolitical positioning.

---

## Continuing Stories

**Anthropic's "month" of internal incidents**: What began before the digest window as a leaked internal blog post about the unreleased "Mythos" model escalated dramatically. Tuesday's Claude Code source leak (via an npm packaging error) became Wednesday's 8,000-fork GitHub proliferation story, then Thursday's active malware distribution campaign leveraging leaked credentials. By Friday the story had extended further, with Dark Reading framing the incident as a wake-up call for the entire industry's approach to AI tooling supply chain oversight. Anthropic's public communication remained limited; the "Anthropic is having a month" framing from TechCrunch captured the mood. The story ends the week unresolved: the source code is circulating, the malware campaigns are ongoing, and the systemic question — how AI labs handle secrets management and developer tooling security — remains unanswered.

**OpenAI's capital and product pivot**: The $122 billion raise confirmed on Tuesday (after pre-announcement on Monday) included a $455 billion infrastructure order with Oracle and $3 billion from retail investors ahead of a signaled IPO. The official announcement reframed ChatGPT as a "super app" rather than a chat product — a hard pivot away from API-first. By Thursday, OpenAI was also restructuring its C-suite (COO Brad Lightcap taking on special projects, AGI deployment head Fidji Simo on medical leave) and acquiring business talk show TBPN to build an in-house media operation. The week confirmed that OpenAI's ambitions have expanded well beyond language models into media, enterprise infrastructure, and consumer platform dominance.

**AI supply chain security escalation**: The Axios npm attack story ran across four days. Monday surfaced the vulnerability; Tuesday brought the North Korean attribution from Google (group UNC1069); Wednesday deepened the analysis with LiteLLM's compromise enabling the Mercor breach; Thursday saw the Claude Code incident widen the supply chain concern from npm to AI tooling broadly; Friday brought Chainguard's Factory 2.0 announcement as an industry response. The arc of the week moved from individual incident to systemic risk category.

**AI infrastructure energy buildout**: Meta's Hyperion datacenter powering up with ten new natural gas plants (Wednesday) was followed by a broader TechCrunch analysis on Friday documenting that Meta, Microsoft, and Google are all committing to new fossil fuel generation capacity to power AI workloads. The story connects to Mistral's $830M debt facility (Monday) and OpenAI's Oracle infrastructure deal — the industry is now at the scale where its energy decisions are macroeconomic events. Analysts warned of long-term fossil-fuel lock-in risk; none of the companies disclosed firm timelines for renewable transitions.

**China's hardware independence milestone**: Thursday's report that Chinese domestic AI accelerators had captured 41% of China's market was followed immediately Friday by DeepSeek v4's confirmation that it would run exclusively on Huawei chips, with hundreds of thousands of units already ordered and Nvidia excluded from testing. These two data points in 48 hours marked the transition from "China is trying to build domestic AI chips" to "China has built domestic AI chips capable of running frontier inference." The geopolitical and commercial implications for Nvidia extend well beyond China's domestic market.

---

## Research Highlights

### Safety

- **[Reward Hacking as Equilibrium under Finite Evaluation](https://arxiv.org/abs/2603.28063)** — Proves under five minimal axioms that any optimized AI agent will systematically under-invest in quality dimensions not covered by its evaluation system, establishing reward hacking as a structural inevitability rather than a correctable bug — the most theoretically significant safety result of the week.

- **[SafetyDrift: Predicting When AI Agents Cross the Line Before They Actually Do](https://arxiv.org/abs/2603.27148)** — Models multi-step agent safety trajectories as absorbing Markov chains, enabling predictive rather than reactive oversight of autonomous systems accumulating individually-safe-looking actions.

- **[Finding and Reactivating Post-Trained LLMs' Hidden Safety Mechanisms](https://arxiv.org/abs/2604.00012)** — Demonstrates that fine-tuning suppresses but does not erase safety guardrails, and that dormant mechanisms can be reactivated without retraining — directly relevant to the LoRA compositionality vulnerability published the same week.

### Security & Adversarial

- **[Kill-Chain Canaries: Stage-Level Tracking of Prompt Injection Across Attack Surfaces and Model Safety Tiers](https://arxiv.org/abs/2603.28013)** — Uses cryptographic canary tokens to instrument prompt injection attacks across four kill-chain stages on five frontier LLM agents, producing the most granular map yet of where specific models' defenses activate or fail.

- **[Colluding LoRA: A Compositional Vulnerability in LLM Safety Alignment](https://arxiv.org/abs/2603.12681)** — Shows that individually benign LoRA adapters can unlock harmful behaviors when linearly composed, a novel threat to the shared-adapter ecosystem that has no obvious mitigation within current deployment practices.

### Benchmarks & Evaluation

- **[Beyond pass@1: A Reliability Science Framework for Long-Horizon LLM Agents](https://arxiv.org/abs/2603.29231)** — Distinguishes capability (single-attempt success) from production reliability (consistency across repeated runs), arguing that current benchmarks measure only the former and are therefore insufficient for deployment decisions.

- **[FormalProofBench: Can Models Write Graduate Level Math Proofs That Are Formally Verified?](https://arxiv.org/abs/2603.26996)** — Tests whether AI can produce Lean 4 proofs accepted by a formal checker on qualifying-exam problems, targeting the gap between LLM mathematical fluency and verified correctness.

### Applications

- **[Towards a Medical AI Scientist](https://arxiv.org/abs/2603.28589)** — The first autonomous system for clinical medicine that generates hypotheses, designs experiments, and drafts manuscripts — extending the "AI Scientist" paradigm to a domain where evidence grounding and safety standards raise the bar considerably.

---

## Key Themes

**AI tooling supply chains are the new attack surface**: The week made concrete what had been theoretical. Three distinct incidents — the Axios npm compromise, the Claude Code leak weaponized for malware, and OpenClaw's unauthenticated admin access — confirmed that AI development infrastructure is now a high-value, under-secured target. The attack surface has moved upstream from AI outputs to the tools, packages, and credentials that developers use to build AI systems.

**Benchmarks are not keeping pace with deployment**: Research this week attacked evaluation validity from multiple directions — probing CoT faithfulness, measuring redundancy in benchmark suites, correcting labeling errors that deflate agent scores, and distinguishing single-attempt capability from production reliability. The convergence on this critique, across independent research groups, signals that the field's evaluation infrastructure has become a first-order problem rather than a footnote.

**Capital concentration is reshaping the competitive structure**: OpenAI's $122 billion raise, Anthropic's $400 million acquisition, Microsoft's $10 billion Japan commitment, and Meta's natural gas infrastructure buildout collectively describe an industry where the limiting resource is no longer model architecture but capital access and physical infrastructure. The gap between companies that can build their own power plants and those that cannot is widening faster than model capability gaps.

**Agentic AI is being deployed ahead of its security maturity**: Google DeepMind's six agent hijacking patterns, Vertex AI's over-privilege vulnerability, the ShadowPrompt Chrome extension flaw, and OpenClaw's privilege escalation all appeared within a single week — not as isolated incidents but as a pattern. The research community is beginning to map the failure modes of real-world agentic deployment; the industry is deploying anyway.

---

## What to Watch

**Anthropic's Coefficient Bio integration**: A $400 million acquisition of a stealth biotech AI startup is Anthropic's most significant strategic move beyond language models. What Coefficient Bio actually built — and how Claude's capabilities will be applied to drug discovery, protein modeling, or clinical data — will shape whether this is a genuine life sciences pivot or a talent acquisition. Expect details to emerge in the next two to four weeks.

**DeepSeek v4 launch timeline**: With hundreds of thousands of Huawei units already ordered and Nvidia excluded from testing, DeepSeek v4 is the first genuine test of whether China's domestic chip ecosystem can support frontier-scale inference at release quality. If v4 performs competitively on international benchmarks while running entirely on Huawei hardware, the geopolitical implications for US export controls — and for Nvidia's revenue assumptions — are substantial.

**EU AI Act August 2026 compliance deadline**: Two research papers this week (on Article 50's structural incompatibility with current generative AI architectures, and on t-norm operators for risk classification) pointed to compliance gaps that cannot be closed by policy guidance alone. With four months remaining before the dual-transparency mandate takes effect, the question is whether the Commission will enforce, delay, or quietly reinterpret requirements that current technology cannot meet.
