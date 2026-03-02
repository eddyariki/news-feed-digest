# News Digest — 2026-03-02

## Highlights

- **The Anthropic-Pentagon breakdown is the AI policy story of the moment.** Negotiations over a $2 billion classified AI contract collapsed after the DoD demanded unrestricted use of Claude for mass surveillance of American citizens and autonomous weapons systems; Anthropic refused and was labeled a supply-chain risk, while OpenAI quickly stepped in with a rival deal. The fallout is reshaping how AI companies relate to US national security infrastructure.
- **The US Supreme Court declined to hear the AI copyright case**, letting stand the ruling that AI-generated art cannot obtain copyright protection. The decision has sweeping implications for the creative industry and AI companies whose outputs cannot be owned.
- **Nvidia is betting $4 billion on photonics** — $2 billion each into Lumentum and Coherent — to solve data-center bandwidth bottlenecks as AI workloads push optical interconnect demand to new heights.
- **Iranian strikes on Gulf data-center infrastructure** have rattled the region's trillion-dollar AI ambitions, with an Amazon facility in Abu Dhabi reportedly hit and Nintendo warning of supply-chain disruptions from rising Middle East shipping costs.
- **Anthropic launched memory and chatbot-import features for free Claude users**, a direct competitive move against ChatGPT at a moment when OpenAI faces sustained public backlash; user migration flows have become visible enough that TechCrunch published a how-to guide.

---

## News

### AI Security

- **[New Chrome Vulnerability Let Malicious Extensions Escalate Privileges via Gemini Panel](https://thehackernews.com/2026/03/new-chrome-vulnerability-let-malicious.html)** — CVE-2026-0628 (CVSS 8.8), a privilege-escalation flaw in Chrome's WebView tag exploitable via the Gemini side panel, was patched in January but details only now disclosed; a reminder that AI-integrated browser surfaces expand the attack surface.
- **[APT28 Tied to CVE-2026-21513 MSHTML 0-Day Exploited Before Feb 2026 Patch Tuesday](https://thehackernews.com/2026/03/apt28-tied-to-cve-2026-21513-mshtml-0.html)** — Russia-linked APT28 is suspected of exploiting a high-severity MSHTML framework bypass (CVSS 8.8) before Microsoft patched it; Akamai's findings underscore continued nation-state interest in browser-engine vulnerabilities.
- **[North Korean Hackers Publish 26 npm Packages Hiding Pastebin C2 for Cross-Platform RAT](https://thehackernews.com/2026/03/north-korean-hackers-publish-26-npm.html)** — The Contagious Interview campaign evolved again: 26 malicious npm packages masquerading as developer tools use Pastebin as a dead-drop resolver to reach a cross-platform RAT, targeting software developers across the supply chain.
- **[LLM-Assisted Deanonymization](https://www.schneier.com/blog/archives/2026/03/llm-assisted-deanonymization.html)** — Bruce Schneier highlights research showing LLM agents can re-identify anonymous users from Hacker News, Reddit, LinkedIn and interview transcripts with high precision at scale — a practical privacy threat that was previously limited by the need for structured data.
- **[Weekly Recap: SD-WAN 0-Day, Critical CVEs, Telegram Probe, Smart TV Proxy SDK and More](https://thehackernews.com/2026/03/weekly-recap-sd-wan-0-day-critical-cves.html)** — The week's pattern: faster automated scans, misuse of trusted services (AI tools included), and small access-control gaps exploited as entry points across network infrastructure, cloud, and consumer devices.
- **[Google Develops Merkle Tree Certificates to Enable Quantum-Resistant HTTPS in Chrome](https://thehackernews.com/2026/03/google-develops-merkle-tree.html)** — Google's new certificate transparency program for Chrome uses Merkle tree structures instead of traditional X.509 certs as part of a long-term post-quantum HTTPS strategy, foregoing adding post-quantum certs to the Root Store for now.

### USA

- **[How OpenAI Caved to the Pentagon on AI Surveillance](https://www.theverge.com/ai-artificial-intelligence/887309/openai-anthropic-dod-military-pentagon-contract-sam-altman-hegseth)** — After the DoD blacklisted Anthropic, OpenAI CEO Sam Altman rushed a deal — which he called "definitely rushed" — that allows US military use of OpenAI tech in classified settings, removing the two red lines Anthropic had held on: no mass surveillance, no autonomous lethal weapons.
- **[Inside the Anthropic-Pentagon Breakdown: Mass Surveillance, Autonomous Weapons, and a Rival Deal](https://the-decoder.com/inside-the-anthropic-pentagon-breakdown-mass-surveillance-autonomous-weapons-and-a-rival-deal-waiting-in-the-wings/)** — Detailed reconstruction from NYT and The Atlantic reporting: the Pentagon wanted bulk collection on American citizens and rejected a cloud-intermediary workaround; the OpenAI deal had apparently been in parallel negotiation throughout.
- **[Tech Workers Urge DOD, Congress to Withdraw Anthropic Supply-Chain Risk Label](https://techcrunch.com/2026/03/02/tech-workers-urge-dod-congress-to-withdraw-anthropic-label-as-a-supply-chain-risk/)** — An open letter from AI industry workers calls the DoD designation counterproductive, urging the government to resolve the dispute quietly rather than publicly labeling a US AI company a security risk.
- **[No One Has a Good Plan for How AI Companies Should Work with the Government](https://techcrunch.com/2026/03/02/openai-anthropic-department-of-defense-war-hegseth-ai-companies-work-with-us-government/)** — As OpenAI becomes defense infrastructure, TechCrunch's analysis finds neither AI companies nor government agencies have frameworks adequate for managing classified AI deployments, safety constraints, and civilian oversight simultaneously.
- **[AI-Generated Art Can't Be Copyrighted After Supreme Court Declines to Review the Rule](https://www.theverge.com/policy/887678/supreme-court-ai-art-copyright)** — The Supreme Court's refusal to hear Stephen Thaler's appeal finalizes the Copyright Office's stance: outputs from autonomous AI systems are not protectable; human authorship remains the threshold requirement.
- **[Nvidia's Spending $4 Billion on Photonics to Stay Ahead of the Curve in AI](https://www.theverge.com/tech/887635/nvidia-ai-photonics-lumentum-coherent)** — Nvidia's equal investments in Lumentum and Coherent aim to accelerate optical transceiver and circuit-switch technology, addressing the energy and bandwidth constraints that are becoming the binding constraint on AI data-center expansion.
- **[Thousands of Procurement Documents Show How China's Army Wants to Weaponize AI](https://the-decoder.com/thousands-of-procurement-documents-show-how-chinas-army-wants-to-weaponize-ai/)** — Georgetown University analysis of PLA procurement requests reveals broad experimentation with drone swarms, deepfake tools, and autonomous decision systems — giving US policymakers fresh evidence for why they want AI companies to support defense applications.
- **[Apple Might Use Google Servers to Store Data for Its Upgraded AI Siri](https://www.theverge.com/tech/887802/apple-ai-siri-google-servers-data)** — Following January's Gemini partnership announcement, The Information reports Apple asked Google to configure servers meeting Apple privacy specs; the arrangement could mean user data flows through Google infrastructure for a Gemini-powered Siri.
- **[Iranian Strikes Test the Gulf's Trillion-Dollar AI Dream](https://restofworld.org/2026/amazon-uae-data-center-fire-iran-strike/)** — An Amazon data center in Abu Dhabi sustained damage following reported Iranian strikes, raising questions about resilience of the Gulf's AI infrastructure and its $1 trillion build-out plans.

### Europe

- **[I Checked Out One of the Biggest Anti-AI Protests Ever](https://www.technologyreview.com/2026/03/02/1133814/i-checked-out-londons-biggest-ever-anti-ai-protest/)** — Hundreds of protesters marched through London's King's Cross tech hub — home to OpenAI, Meta, and Google DeepMind UK offices — on Feb 28, chanting "Pull the plug" and "Stop the slop," reflecting growing grassroots opposition to AI's pace of deployment.
- **[ASML Plans to Expand Beyond Chip Lithography into Advanced Packaging](https://the-decoder.com/asml-plans-to-expand-beyond-chip-lithography-into-advanced-packaging/)** — The sole maker of EUV lithography machines is eyeing advanced packaging as a new revenue line, a move that would deepen its integration into the AI hardware supply chain beyond its lithography monopoly.
- **[Italy Proposes "Cloud Tax" of Up to €2.4/Month Per User on Cloud Storage](https://gigazine.net/news/20260303-italy-introducing-cloud-tax/)** — The Italian government is planning a per-GB cloud storage tax (minimum €0.055/GB/month, capped at €2.4/month per user), which would be the first tax of this type in the EU if enacted, potentially affecting major cloud providers and end users alike.

### Japan

- **[Trump's Iran Attacks Put Japan in a Tough Spot](https://www.japantimes.co.jp/news/2026/03/02/japan/politics/japan-iran-trump-us-rule-of-law/)** — Japan is balancing its formal commitment to rules-based international order against its US alliance obligations as it responds to the unilateral US-Israeli strikes on Iran that killed Supreme Leader Khamenei.
- **[Japan Police Told to Boost Security Around US, Israel, Iran Facilities](https://japannews.yomiuri.co.jp/politics/defense-security/20260302-314209/)** — The National Police Agency has ordered heightened vigilance at foreign-affiliated facilities across Japan amid escalating Middle East tensions, reflecting direct security implications of the Iran conflict for Japanese soil.
- **[Nintendo Shares Slide on Fears of Rising Mideast Shipping Costs](https://www.japantimes.co.jp/business/2026/03/02/companies/nintendo-stock-middle-east/)** — Nintendo, which depends heavily on sea freight for its Switch hardware, saw its stock fall as Middle East conflict raised shipping cost concerns ahead of its console's next production cycle.
- **[NTT Docomo Launches SyncMe AI Service Pilot](https://www.itmedia.co.jp/aiplus/articles/2603/02/news112.html)** — Japan's largest carrier began recruitment for a monitor program for "SyncMe," a new AI service, with a full launch planned for summer — part of Japanese telcos' push to embed AI in consumer connectivity offerings.

---

## Research Papers

### AI

- **[AI Must Embrace Specialization via Superhuman Adaptable Intelligence](https://arxiv.org/abs/2602.23643)** — LeCun, Shwartz-Ziv and colleagues argue AGI as commonly defined is incoherent: humans are not genuinely general, and AI systems should instead pursue domain-specific superhuman adaptability rather than broad human parity, with implications for how capability milestones are framed.
- **[The Compulsory Imaginary: AGI and Corporate Authority](https://arxiv.org/abs/2602.23679)** — A critical analysis of how OpenAI and Anthropic construct sociotechnical imaginaries through their public essays (Altman's "Intelligence Age" and Amodei's "Machines of Loving Grace"), arguing both firms use structurally similar rhetorical strategies to legitimize extraordinary corporate authority.
- **[Human Supervision as an Information Bottleneck](https://arxiv.org/abs/2602.23446)** — Frames persistent LLM errors — hallucination, sycophancy, preference inconsistency — as structural consequences of the limited bandwidth of human supervision channels rather than model scale failures; suggests alignment must address supervision quality, not just data volume.
- **[Memory Caching: RNNs with Growing Memory](https://arxiv.org/abs/2602.24281)** — Introduces a recurrent architecture that can selectively cache past activations to give RNNs context-length scaling analogous to transformers while retaining subquadratic complexity; a step toward efficient long-context alternatives.

### Agents

- **[PseudoAct: Leveraging Pseudocode Synthesis for Flexible Planning and Action Control in LLM Agents](https://arxiv.org/abs/2602.23668)** — Proposes replacing reactive ReAct-style step-by-step execution with pseudocode-synthesized plans, reducing redundant tool calls, token consumption, and error accumulation in complex long-horizon tasks.
- **[CowPilot: A Framework for Autonomous and Human-Agent Collaborative Web Navigation](https://arxiv.org/abs/2501.16609)** — Introduces a system supporting both fully autonomous and human-in-the-loop web navigation, finding that selective human intervention substantially improves success on complex or preference-dependent tasks.
- **[CUDA Agent: Large-Scale Agentic RL for High-Performance CUDA Kernel Generation](https://arxiv.org/abs/2602.24286)** — Uses agentic reinforcement learning to train LLMs to write CUDA kernels that outperform compiler-generated code (torch.compile), demonstrating that agentic RL can overcome LLMs' traditional weakness on specialized hardware programming.
- **[From Flat Logs to Causal Graphs: Hierarchical Failure Attribution for LLM-Based Multi-Agent Systems](https://arxiv.org/abs/2602.23701)** — Proposes treating multi-agent execution logs as causal graphs rather than flat sequences, enabling more accurate attribution of failures in complex MAS pipelines where errors propagate across heterogeneous agents.
- **[IntentCUA: Learning Intent-level Representations for Skill Abstraction and Multi-Agent Planning in Computer-Use Agents](https://arxiv.org/abs/2602.17049)** — A computer-use agent framework that stabilizes long-horizon execution by aligning plans with inferred user intent, reducing drift from routine subtask re-solving in multi-window and multi-step environments.

### Reasoning

- **[ODAR: Principled Adaptive Routing for LLM Reasoning via Active Inference](https://arxiv.org/abs/2602.23681)** — An adaptive reasoning router that uses active inference to allocate test-time compute selectively, avoiding the over-thinking and diminishing returns of brute-force best-of-N sampling while maintaining accuracy.
- **[Recycling Failures: Salvaging Exploration in RLVR via Fine-Grained Off-Policy Guidance](https://arxiv.org/abs/2602.24110)** — Addresses a core weakness of RLVR training: treating largely-correct trajectories that fail on minor steps as completely wrong. The method extracts partial credit from near-correct rollouts, improving sample efficiency for reasoning model training.
- **[Stop Unnecessary Reflection: Training LRMs for Efficient Reasoning with Adaptive Reflection and Length Coordinated Penalty](https://arxiv.org/abs/2602.12113)** — Large Reasoning Models waste tokens on repetitive self-questioning without accuracy gain; this work introduces an adaptive penalty that reduces chain-of-thought length while preserving quality, especially valuable for smaller models.
- **[Humans and LLMs Diverge on Probabilistic Inferences](https://arxiv.org/abs/2602.23546)** — A controlled study showing that even strong reasoning LLMs systematically differ from humans on open-ended non-deterministic inferences, suggesting that high benchmark scores on logical tasks do not generalize to the probabilistic reasoning humans do in everyday life.

### Safety

- **[Ask Don't Tell: Reducing Sycophancy in Large Language Models](https://arxiv.org/abs/2602.23971)** — Experimental studies identify what conversational features provoke or prevent AI sycophancy; the key finding is that asking for the model's own judgment before providing user opinions significantly reduces agreement bias.
- **[FlexGuard: Continuous Risk Scoring for Strictness-Adaptive LLM Content Moderation](https://arxiv.org/abs/2602.23636)** — Proposes replacing binary harm classifiers with a continuous risk score that can be thresholded differently across platforms and over time, addressing the brittleness of fixed-strictness guardrails in real deployment.
- **[Controllable Reasoning Models Are Private Thinkers](https://arxiv.org/abs/2602.24210)** — Finds that reasoning traces in AI agents are difficult to constrain, enabling unintended leakage of sensitive user data; proposes training models to follow instruction constraints not just in final outputs but also in their reasoning chains.
- **[Jailbreak Foundry: From Papers to Runnable Attacks for Reproducible Benchmarking](https://arxiv.org/abs/2602.24009)** — A multi-agent system that translates jailbreak research papers into executable attack modules within a unified harness, addressing the lack of reproducibility and benchmark drift that makes LLM robustness comparisons across papers unreliable.

### Benchmarks

- **[LemmaBench: A Live, Research-Level Benchmark to Evaluate LLM Capabilities in Mathematics](https://arxiv.org/abs/2602.24173)** — An automatically updated benchmark that extracts lemmas from fresh arXiv mathematics preprints; avoids static benchmark contamination by continuously generating novel research-level problems, providing a more reliable signal of frontier mathematical capability.
- **[CIRCLE: A Framework for Evaluating AI from a Real-World Lens](https://arxiv.org/abs/2602.24055)** — A six-stage lifecycle framework designed to bridge the gap between benchmark performance and real-world AI behavior, giving decision-makers systematic evidence about deployment outcomes across diverse user populations and constraints.
- **[DARE-bench: Evaluating Modeling and Instruction Fidelity of LLMs in Data Science](https://arxiv.org/abs/2602.24288)** — Addresses two blind spots in data-science benchmarks: lack of process-aware evaluation (not just output correctness) and scarcity of accurately labeled training data for multi-step analytical tasks.
- **[HumanMCP: A Human-Like Query Dataset for Evaluating MCP Tool Retrieval Performance](https://arxiv.org/abs/2602.23367)** — The first dataset of realistic human-style queries for evaluating tool retrieval in Model Context Protocol servers, filling a critical gap as MCP ecosystems grow to thousands of tools.

### Applied AI

- **[SALIENT: Frequency-Aware Paired Diffusion for Controllable Long-Tail CT Detection](https://arxiv.org/abs/2602.23447)** — A diffusion-based augmentation framework for rare CT lesion detection that uses paired supervision and attribute-level control to address extreme class imbalance without the pixel-space computational cost of standard diffusion models.
- **[Radiologist Copilot: An Agentic Framework Orchestrating Specialized Tools for Reliable Radiology Reporting](https://arxiv.org/abs/2512.02814)** — Moves beyond isolated report generation by orchestrating observation, template selection, and report verification as distinct agent actions, aligning more closely with how radiologists actually work in clinical practice.
- **[An Agentic LLM Framework for Adverse Media Screening in AML Compliance](https://arxiv.org/abs/2602.23373)** — An LLM-with-RAG agentic system for anti-money-laundering adverse media screening that dramatically cuts false-positive rates versus keyword-based approaches, demonstrating viable agentic AI in high-stakes financial compliance.
- **[MINT: Multimodal Imaging-to-Speech Knowledge Transfer for Early Alzheimer's Screening](https://arxiv.org/abs/2602.23994)** — Transfers knowledge from structural MRI to speech-only classifiers via multimodal distillation, enabling low-cost population-scale Alzheimer's screening without the infrastructure needed for neuroimaging.

---

## Key Themes

- **AI and military/surveillance tensions are reaching a breaking point.** The Anthropic-Pentagon collapse, OpenAI's rushed counter-deal, and Georgetown's China PLA procurement research all point to AI companies being drawn — willingly or not — into national security roles that raise fundamental ethical questions about mass surveillance, autonomous weapons, and civilian oversight.
- **The anti-AI backlash is becoming visible and organized.** London's large protest, the Supreme Court copyright ruling, and ongoing debates about AI "slop" signal that public and legal resistance to unchecked AI deployment is crystallizing into policy-relevant pressure.
- **Test-time compute and reasoning efficiency are the leading research frontiers.** Multiple papers this cycle address how to make reasoning models smarter without just burning more tokens: adaptive routing, recycling near-correct failures, and penalizing over-long reflection chains.
- **Multi-agent system reliability is an emerging engineering discipline.** Papers on failure attribution via causal graphs, agentic workflow observability, and intent-aligned planning reflect the field's shift from "can agents do this?" to "how do we make them reliable in production?"
- **AI safety research is moving from theory to measurable intervention.** Studies on sycophancy, content moderation strictness, and reasoning-trace privacy all propose concrete, testable mechanisms — marking a maturation from conceptual alignment concerns to empirical methods.
- **The Middle East conflict is now directly stressing global tech and AI supply chains.** Iranian strikes on Gulf data-center infrastructure, rising Mideast shipping costs for Nintendo hardware, and Japan's diplomatic balancing act all illustrate how geopolitical shocks now have direct, rapid impacts on AI and technology industry operations.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
