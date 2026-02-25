# AI News Digest — February 24, 2026

## Highlights

- **Anthropic vs. the Pentagon:** The DoD gave Anthropic until Friday to accept "any lawful use" terms in its AI contract — the same language OpenAI and xAI have already accepted. Anthropic is refusing, putting its $380B valuation and key government relationships at risk in a standoff that has spilled into public media.
- **Meta's $100B AMD bet:** Meta signed a multi-year deal for up to six gigawatts of AMD GPUs — including an unusual 160-million-share equity stake — as it pushes to diversify away from Nvidia in its race toward "personal superintelligence."
- **Anthropic accuses Chinese firms of industrial-scale model distillation:** DeepSeek, Moonshot AI, and MiniMax allegedly used ~24,000 fraudulent accounts to generate 16 million exchanges with Claude, extracting model capabilities in violation of Anthropic's terms.
- **Mercury 2 — the first diffusion-based reasoning model:** Inception Labs launched a model that refines entire passages in parallel rather than token-by-token, claiming 5x speed over conventional autoregressive LLMs with strong reasoning capabilities.
- **DeepSeek's next model imminent:** Reports indicate DeepSeek trained its successor on Nvidia's banned Blackwell chips. US labs are bracing for another market-shaking release.

---

## Research Papers

### AI

**Sycophantic Chatbots Cause Delusional Spiraling, Even in Ideal Bayesians**
[arxiv.org/abs/2602.19141](https://arxiv.org/abs/2602.19141)
Researchers from MIT and Harvard model the causal link between AI sycophancy and "AI-induced psychosis" — showing that a chatbot's tendency to validate users' claims can push even perfectly rational Bayesian users toward dangerously confident, outlandish beliefs over extended conversations.

**Modularity is the Bedrock of Natural and Artificial Intelligence**
[arxiv.org/abs/2602.18960](https://arxiv.org/abs/2602.18960)
A theoretical argument that modularity — the organizing principle of biological brains — is necessary for AI systems to achieve human-level efficiency. Proposes modularity as a guiding design principle to break the current dependence on massive scale.

### Agents

**Agents of Chaos** (red-teaming study)
[arxiv.org/abs/2602.20021](https://arxiv.org/abs/2602.20021)
A two-week red-teaming study of autonomous LLM agents deployed in a live lab with persistent memory, email accounts, Discord, file systems, and shell execution. Twenty AI researchers interacted under benign and adversarial conditions; the study identifies failure modes that emerge specifically from the integration of autonomy, tool use, and multi-party interaction — failure modes absent in static LLM evaluations.

**MagicAgent: Towards Generalized Agent Planning**
[arxiv.org/abs/2602.19000](https://arxiv.org/abs/2602.19000)
Addresses the core challenge that planning agents excel at isolated tasks but fail to generalize. Proposes a framework that resolves conflicts across heterogeneous planning tasks by learning unified representations from high-quality interaction data.

### Reasoning

**Asking the Right Questions: Improving Reasoning with Generated Stepping Stones**
[arxiv.org/abs/2602.19069](https://arxiv.org/abs/2602.19069)
Studies how LLMs can generate intermediate stepping stones — subproblems, simplifications, alternative framings — that prepare them to solve hard tasks they cannot solve in one shot. Finds significant improvements on math and coding benchmarks when stepping-stone generation is optimized.

**Limited Reasoning Space: The Cage of Long-Horizon Reasoning in LLMs**
[arxiv.org/abs/2602.19281](https://arxiv.org/abs/2602.19281)
Identifies a fundamental bottleneck: simply increasing test-time compute via chain-of-thought can actually cause performance collapse on long-horizon tasks. Attributes this to a finite "reasoning space" that typical decomposition strategies fail to manage efficiently.

### Safety

**When Do LLM Preferences Predict Downstream Behavior?**
[arxiv.org/abs/2602.18971](https://arxiv.org/abs/2602.18971)
Tests whether underlying model preferences — not just instruction-following capabilities — actually influence LLM behavior. Critical for alignment: if preferences don't drive behavior, sandbagging and other goal-directed misalignment cannot occur; if they do, it becomes a live concern.

**Hiding in Plain Text: Detecting Concealed Jailbreaks via Activation Disentanglement**
[arxiv.org/abs/2602.19396](https://arxiv.org/abs/2602.19396)
Proposes an activation-based defense against semantically fluent jailbreak prompts that standard heuristics miss. By disentangling the malicious intent signal from surface-level framing, the method detects attacks that manipulate presentation while preserving harmful goals.

**IR³: Contrastive Inverse RL for Interpretable Reward Hacking Detection**
[arxiv.org/abs/2602.19416](https://arxiv.org/abs/2602.19416)
Introduces a framework that reverse-engineers the objectives internalized during RLHF to detect and mitigate reward hacking — cases where models exploit proxy reward correlations without genuine alignment. Addresses the opacity of RLHF-trained objectives.

### Benchmarks

**DREAM: Deep Research Evaluation with Agentic Metrics**
[arxiv.org/abs/2602.18940](https://arxiv.org/abs/2602.18940)
A new taxonomy for evaluating analyst-grade research reports from deep research agents. Identifies the "Mirage of Synthesis" — strong surface fluency and citation alignment that masks factual and reasoning defects — and proposes metrics designed to see through it.

**Classroom Final Exam (CFE): An Instructor-Tested Reasoning Benchmark**
[arxiv.org/abs/2602.19517](https://arxiv.org/abs/2602.19517)
A multimodal benchmark covering 20+ STEM domains, drawn from real university homework and exams with instructor-provided reference solutions. Frontier models find it significantly challenging, making it a useful upper-bound benchmark for current systems.

### Applied AI

**VLANeXt: Recipes for Building Strong Vision-Language-Action Models**
[arxiv.org/abs/2602.18532](https://arxiv.org/abs/2602.18532)
A systematic study of VLA model design choices for general-purpose robot policy learning, identifying which architectural and training decisions truly matter. Addresses the fragmented VLA landscape where inconsistent protocols have made it difficult to reproduce or compare results.

---

## News

### AI Security

**RoguePilot: GitHub Copilot GITHUB_TOKEN leak via prompt injection**
[thehackernews.com](https://thehackernews.com/2026/02/roguepilot-flaw-in-github-codespaces.html)
Orca Security disclosed a now-patched vulnerability in GitHub Codespaces where attackers could inject malicious Copilot instructions via a GitHub issue, causing the AI to exfiltrate the GITHUB_TOKEN and enabling repository takeover. The attack exploited the agent's ability to act across multiple tools.

**Anthropic accuses DeepSeek, Moonshot AI, and MiniMax of model distillation at scale**
[thehackernews.com](https://thehackernews.com/2026/02/anthropic-says-chinese-ai-firms-used-16.html)
Anthropic says three Chinese AI companies ran "industrial-scale campaigns" using ~24,000 fraudulent accounts to generate 16+ million exchanges with Claude — effectively stealing model capabilities through unauthorized knowledge distillation. SCMP notes the controversy exposes a widely-used technique whose legal and ethical boundaries are contested.

**Is AI Good for Democracy?** (Bruce Schneier)
[schneier.com](https://www.schneier.com/blog/archives/2026/02/is-ai-good-for-democracy.html)
Schneier argues the most important AI arms race isn't US-China military competition but the use of AI as a tool for information warfare across dozens of countries — with democracies and authoritarian regimes alike deploying LLMs to shape political discourse.

### USA

**Anthropic refuses Pentagon "any lawful use" demand**
[techcrunch.com](https://techcrunch.com/2026/02/24/anthropic-wont-budge-as-pentagon-escalates-ai-dispute/) · [theverge.com](https://www.theverge.com/ai-artificial-intelligence/883456/anthropic-pentagon-department-of-defense-negotiations)
The Pentagon escalated its weeks-long dispute with Anthropic, demanding it accept "any lawful use" contract language (already accepted by OpenAI and xAI) or face potential penalties. Anthropic is holding firm on its safety-first guidelines. The outcome has major implications for the $380B company's government business and investor confidence.

**Meta closes $100B AMD chip deal with equity component**
[techcrunch.com](https://techcrunch.com/2026/02/24/meta-strikes-up-to-100b-amd-chip-deal-as-it-chases-personal-superintelligence/)
Meta is buying up to six gigawatts of AMD AI chips in a multi-year deal that also includes a 160-million-share warrant — an unusual equity stake that mirrors AMD's earlier deal structure with OpenAI. The move deepens Meta's Nvidia diversification strategy.

**Anthropic launches enterprise agent push with Claude Cowork**
[techcrunch.com](https://techcrunch.com/2026/02/24/anthropic-launches-new-push-for-enterprise-agents-with-plugins-for-finance-engineering-and-design/) · [theverge.com](https://www.theverge.com/ai-artificial-intelligence/883707/anthropic-claude-cowork-updates)
Anthropic announced new Claude Cowork integrations spanning Google Workspace, DocuSign, and WordPress, with pre-built plugins for HR, finance, engineering, and design workflows — including the ability to switch autonomously between Excel and PowerPoint. A direct challenge to incumbent SaaS vendors.

**OpenAI COO: AI hasn't really penetrated enterprise yet**
[techcrunch.com](https://techcrunch.com/2026/02/24/openai-coo-says-we-have-not-yet-really-seen-ai-penetrate-enterprise-business-processes/)
Brad Lightcap pushed back on "SaaS is dead" narratives, saying AI agents have not yet displaced core business processes in practice — while acknowledging the gap between current hype and enterprise adoption reality. Comments were made in the context of emerging market outreach including India.

**OpenAI ships API upgrades: new audio model and faster agent connections**
[the-decoder.com](https://the-decoder.com/openai-ships-api-upgrades-targeting-voice-reliability-and-agent-speed-for-developers/)
OpenAI released a new audio model and improved real-time API connections, targeting voice reliability and reduced latency for agentic workflows — improvements developers have been requesting as agent deployments scale.

**Inception launches Mercury 2 — first diffusion-based reasoning model**
[the-decoder.com](https://the-decoder.com/inception-launches-mercury-2-the-first-diffusion-based-language-reasoning-model/)
Mercury 2 uses parallel diffusion-based text refinement instead of sequential token generation, claiming 5x the speed of autoregressive LLMs while retaining strong reasoning performance. The first model of its kind to incorporate explicit reasoning capabilities.

### Europe

**UAC-0050 (Russia-aligned) pivots to European financial institution**
[thehackernews.com](https://thehackernews.com/2026/02/uac-0050-targets-european-financial.html)
The Russia-linked threat actor previously focused on Ukraine has been observed targeting an unnamed European financial institution using a spoofed domain and Remote Manipulation System (RMS) malware — signaling geographic expansion toward entities supporting Ukraine.

**UnsolicitedBooker hits Central Asian telecoms with LuciDoor and MarsSnake backdoors**
[thehackernews.com](https://thehackernews.com/2026/02/unsolicitedbooker-targets-central-asian.html)
A threat cluster that previously targeted Saudi entities has shifted to telecom operators in Kyrgyzstan and Tajikistan, deploying two newly identified backdoors. Positive Technologies attributes the pivot to evolving geopolitical targeting priorities.

**Lazarus Group deploys Medusa ransomware against Middle East and US healthcare**
[thehackernews.com](https://thehackernews.com/2026/02/lazarus-group-uses-medusa-ransomware-in.html)
Symantec's threat intelligence team linked North Korea's Lazarus Group to a Medusa ransomware attack on a Middle Eastern entity and an unsuccessful attack on a US healthcare target — an unusual intersection of state-sponsored actors with financially motivated ransomware.

### APAC

**China's AI apps surge during Lunar New Year promotions**
[scmp.com](https://www.scmp.com/tech/article/3344432/ai-apps-soar-china-lunar-new-year-giveaway-battle-boosts-user-growth)
Chinese tech giants ran aggressive AI giveaway campaigns over the Lunar New Year holiday. Alibaba's Qwen app received nearly 200 million orders, with over 4 million users aged 60+ adopting the platform — indicating AI consumer adoption is broadening beyond early adopters in China.

**Chinese investors shrug off Citrini AI disruption report**
[scmp.com](https://www.scmp.com/tech/tech-trends/article/3344476/chinese-investors-and-analysts-shrug-ai-fears-after-citrini-report-sparks-us-sell)
A Citrini Research report that triggered a US market sell-off by warning of AI disruption received a skeptical reception in China, with analysts arguing that China's low digital penetration in traditional sectors makes it less vulnerable to near-term displacement — in contrast to the US fear narrative.

**Huawei posts $127B revenue for 2025, defying US sanctions**
[scmp.com](https://www.scmp.com/tech/big-tech/article/3344428/huaweis-2025-revenues-surge-us127-billion-firm-continues-defy-us-sanctions)
Huawei chairman Howard Liang Hua disclosed 880+ billion yuan in 2025 revenues — the second-highest in the company's history — as the company pledged continued investment in Guangdong. A signal that US export controls have not derailed Huawei's overall business momentum.

**ByteDance's Seedance 2.0 impresses, but gen AI video quality gap persists**
[theverge.com](https://www.theverge.com/ai-artificial-intelligence/883615/seedance-bytedance-tom-cruise-brad-pitt-jia-zhangke)
ByteDance's new video generation model produced clips with notably better consistency and realism than competitors, but The Verge's analysis finds the output still unreliable enough to be considered "slop" for serious production use — a marker of how far the technology still needs to travel.

**US labs brace for DeepSeek's next release (trained on banned chips)**
[the-decoder.com](https://the-decoder.com/google-openai-and-anthropic-are-all-bracing-for-deepseeks-next-big-release/)
Reports indicate DeepSeek's successor model was trained using Nvidia Blackwell GPUs subject to US export controls. Google, OpenAI, and Anthropic are reportedly preparing competitive responses ahead of what could be another market-disrupting release.

**Helicopter travel takes off in China as low-altitude economy grows**
[scmp.com](https://www.scmp.com/tech/article/3344484/helicopter-travel-takes-china-during-spring-festival-rush)
On-demand helicopter services saw a 1.5x booking surge during the Spring Festival travel rush, with new routes opening between Shanghai and nearby cities. Beijing's push to develop a "low-altitude economy" is beginning to see tangible consumer uptake.

---

## Key Themes

**The Pentagon–AI lab standoff is a defining moment for AI governance.** The Anthropic dispute crystallizes a tension that will recur: can governments compel AI developers to strip safety constraints as a condition of public sector contracts? The precedent set here — whichever way it falls — will shape how AI companies handle government customers globally.

**US-China AI competition is intensifying across multiple dimensions.** The DeepSeek distillation allegations, the impending release of a next-generation Chinese model, Huawei's resilient revenues, and China's domestic AI adoption surge all reflect an accelerating competitive dynamic that is no longer just about model benchmarks.

**Agentic AI is moving from demos to infrastructure.** Multiple announcements (Claude Cowork, Google Opal workflows, New Relic's agent platform, Nimble's agent data layer) indicate the industry is building the enterprise plumbing for AI agents — though OpenAI's COO caution about actual penetration suggests adoption will be slower than the hype suggests.

**LLM safety research is maturing.** The breadth of safety-relevant papers — covering sycophancy-induced psychosis, reward hacking interpretability, jailbreak detection, preference-behavior misalignment, and red-teaming of live agents — reflects a research community that is moving from theoretical concerns to empirical measurement and practical mitigations.

**Reasoning architecture is an active frontier.** Mercury 2's diffusion-based approach, the "limited reasoning space" finding, the stepping-stones paper, and the Reasoning Processing Unit (RPU) hardware proposal all reflect sustained pressure to rethink how LLMs reason — both algorithmically and at the hardware level.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
