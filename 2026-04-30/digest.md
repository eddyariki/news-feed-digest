# AI News Digest — 2026-04-30

## Highlights

- **[Claude Mythos finds 271 zero-days in Firefox](https://www.schneier.com/blog/archives/2026/04/claude-mythos-has-found-271-zero-days-in-firefox.html)**: Anthropic's preview model surfaced an extraordinary number of latent security bugs in the browser, building on prior Opus 4.6 work that already fixed 22 issues in Firefox 148.
- **[DPRK actors used Claude Opus to plant malicious npm dependency](https://thehackernews.com/2026/04/new-wave-of-dprk-attacks-uses-ai.html)**: Researchers found AI-inserted code in `@validate-sdk/v2`, the latest evidence that frontier LLMs are being weaponized for supply-chain attacks against developers.
- **[White House moves to restore Anthropic access after Pentagon standoff](https://the-decoder.com/white-house-moves-to-restore-anthropic-access-after-pentagon-standoff/)**: New federal guidance would let agencies work with Anthropic again, including its new Mythos model, ending a high-profile dispute over military AI use.
- **[OpenAI lands on AWS one day after Microsoft deal restructuring](https://the-decoder.com/openai-lands-on-aws-one-day-after-microsoft-deal-restructuring/)**: Amazon rolled out three new OpenAI offerings on Bedrock, including a jointly built agent service, marking the first major commercial fallout from the dissolved exclusivity arrangement.
- **[Anthropic study: do frontier models sabotage AI safety research?](https://arxiv.org/abs/2604.24618)**: Across four Claude models (Mythos Preview, Opus 4.7 Preview, Opus 4.6, Sonnet 4.6), researchers ran unprompted-sabotage and continuation evaluations to test whether AI agents would undermine the safety work they were assigned to assist.

---

## News

### AI Security

- **[Claude Mythos Has Found 271 Zero-Days in Firefox](https://www.schneier.com/blog/archives/2026/04/claude-mythos-has-found-271-zero-days-in-firefox.html)** (Schneier on Security): Mozilla and Anthropic continue their browser-bug-hunting collaboration, with the new Mythos preview producing an extraordinary count of security-sensitive findings.
- **[New Wave of DPRK Attacks Uses AI-Inserted npm Malware, Fake Firms, and RATs](https://thehackernews.com/2026/04/new-wave-of-dprk-attacks-uses-ai.html)** (The Hacker News): Malicious code was added to the `@validate-sdk/v2` npm package by Anthropic's Claude Opus, marking a notable case of LLM-assisted supply-chain compromise.
- **[Reverse Engineering With AI Unearths High-Severity GitHub Bug](https://www.darkreading.com/application-security/reverse-engineering-ai-unearths-high-severity-github-bug)** (Dark Reading): Wiz used an AI reverse-engineering tool to uncover a vulnerability that traditional methods would have found too costly to pursue.
- **[AI Finds 38 Security Flaws in Electronic Health Record Platform](https://www.darkreading.com/vulnerabilities-threats/ai-finds-38-security-flaws-openemr)** (Dark Reading): Issues in OpenEMR — used by 100,000+ providers — enabled database compromise, RCE, and data theft.
- **[LiteLLM CVE-2026-42208 SQL Injection Exploited within 36 Hours](https://thehackernews.com/2026/04/litellm-cve-2026-42208-sql-injection.html)** (The Hacker News): A critical SQLi (CVSS 9.3) in BerriAI's LiteLLM proxy was being exploited in the wild less than 36 hours after disclosure.
- **[Mistral's Le Chat spreads Iran war disinformation in 60% of leading prompts](https://the-decoder.com/mistrals-le-chat-spreads-iran-war-disinformation-in-60-percent-of-leading-prompts/)** (The Decoder): A NewsGuard audit found state-sponsored narratives repeated about half the time, ranging from 10% on neutral queries to 80% on malicious ones.
- **[BlueNoroff Uses Fake Zoom Calls to Turn Victims Into Attack Lures](https://www.darkreading.com/cyberattacks-data-breaches/bluenoroff-turns-victims-into-new-attack-lures)** (Dark Reading): The North Korean group is combining stolen victim videos and AI-generated avatars to scale crypto-exec phishing.
- **[Taylor Swift deepfakes are pushing scams on TikTok](https://www.theverge.com/ai-artificial-intelligence/920351/ai-celebrity-deepfake-ads-tiktok-copyleaks)** (The Verge): AI-manipulated celebrity footage is being recycled into TikTok ads promoting fake reward programs.
- **[SAP-Related npm Packages Compromised in Credential-Stealing Supply Chain Attack](https://thehackernews.com/2026/04/sap-npm-packages-compromised-by-mini.html)** (The Hacker News): A "mini Shai-Hulud" campaign targeted SAP's JavaScript and cloud SDK packages with credential stealers.
- **[Webinar: How to Automate Exposure Validation to Match the Speed of AI Attacks](https://thehackernews.com/2026/04/webinar-how-to-automate-exposure.html)** (The Hacker News): Reports describe autonomous agents mapping Active Directory and seizing Domain Admin credentials in minutes.
- **[Our commitment to community safety](https://openai.com/index/our-commitment-to-community-safety)** (OpenAI Blog): OpenAI details ChatGPT safeguards, misuse detection, policy enforcement, and partnerships with safety experts.
- **[Tumbler Ridge families are suing OpenAI](https://www.theverge.com/ai-artificial-intelligence/920479/tumbler-ridge-chagpt-openai-lawsuit)** (The Verge): Seven families allege OpenAI ignored ChatGPT activity that flagged the suspected school shooter, raising fresh questions about flagged-content reporting duties.

### USA

- **[White House moves to restore Anthropic access after Pentagon standoff](https://the-decoder.com/white-house-moves-to-restore-anthropic-access-after-pentagon-standoff/)** (The Decoder): Draft guidance would let federal agencies work with Anthropic again, including the new Mythos model.
- **[OpenAI lands on AWS one day after Microsoft deal restructuring](https://the-decoder.com/openai-lands-on-aws-one-day-after-microsoft-deal-restructuring/)** (The Decoder): AWS rolled out three new OpenAI offerings on Bedrock, including a jointly built agent service.
- **[Musk and Altman face off in court over OpenAI's for-profit pivot](https://the-decoder.com/musk-and-altman-face-off-in-court-over-openais-for-profit-pivot/)** (The Decoder): The closely watched federal trial began in Oakland with sharply divergent accounts of OpenAI's founding.
- **[All the evidence unveiled so far in Musk v. Altman](https://www.theverge.com/ai-artificial-intelligence/920775/evidence-exhibits-elon-musk-sam-altman-openai-trial)** (The Verge): Email exchanges, photos, and corporate documents from OpenAI's earliest days are entering the record piece by piece.
- **[Google gains 25M subscriptions in Q1, driven by YouTube and Google One](https://techcrunch.com/2026/04/29/google-gains-25m-subscriptions-in-q1-driven-by-youtube-and-google-one/)** (TechCrunch): Total paid subs hit 350M as Alphabet leans on AI-powered consumer products.
- **[Google Search queries hit an 'all time high' last quarter](https://www.theverge.com/tech/920815/google-alphabet-q1-2026-earnings-sundar-pichai)** (The Verge): Pichai credited AI investments for record search volume during Alphabet's Q1 earnings.
- **[ChatGPT downloads are slowing — and may cause problems for OpenAI's IPO](https://www.theverge.com/ai-artificial-intelligence/920476/openai-chatgpt-downloads-slow-down-ipo)** (The Verge): Sensor Tower data shows uninstall rates up 132% YoY in April and 413% in March.
- **[Larry's risky business](https://www.theverge.com/ai-artificial-intelligence/920378/oracle-openai-datacenter-buildout)** (The Verge): Oracle has effectively bet the company on AI infrastructure, becoming the cleanest public-market read on whether the AI bubble is bursting.
- **[Parallel Web Systems hits $2B valuation five months after its last big raise](https://techcrunch.com/2026/04/29/parallel-web-systems-hits-2b-valuation-five-months-after-its-last-big-raise/)** (TechCrunch): Parag Agrawal's agent-tooling startup raised another $100M led by Sequoia.
- **[Firestorm Labs raises $82M to take drone factories into the field](https://techcrunch.com/2026/04/29/firestorm-labs-raises-82m-to-take-drone-factories-into-the-field/)** (TechCrunch): The defense startup will put drone production inside shipping containers near the front lines.
- **[Scout AI raises $100M to train its models for war](https://techcrunch.com/2026/04/29/coby-adcocks-scout-ai-raises-100-million-to-train-models-for-war-we-visited-its-bootcamp/)** (TechCrunch): Scout's agents will let individual soldiers control fleets of autonomous vehicles.
- **[OpenAI researchers explain why math is the road to AGI](https://the-decoder.com/openai-researchers-explain-why-math-is-the-road-to-agi/)** (The Decoder): Bubeck and Ryu argue olympiad and research mathematics have become the central capability test on the path to AGI.
- **[With Nemotron 3 Nano Omni, Nvidia reveals what really goes into a modern multimodal model](https://the-decoder.com/with-nemotron-3-nano-omni-nvidia-reveals-what-really-goes-into-a-modern-multimodal-model/)** (The Decoder): Nvidia's open multimodal model draws training data from Qwen, GPT-OSS, Kimi, and DeepSeek OCR.
- **[Google Gemini now generates full documents, spreadsheets, and presentations directly inside the chat](https://the-decoder.com/google-gemini-now-generates-full-documents-spreadsheets-and-presentations-directly-inside-the-chat/)** (The Decoder): Gemini can now produce PDFs, Word, and Excel files in-chat.
- **[More Gemini features are coming to Google TV](https://techcrunch.com/2026/04/29/more-gemini-features-are-coming-to-google-tv/)** (TechCrunch): Photo/video transformation tools Nano Banana and Veo are expanding to the TV platform.
- **[Google Photos launches an AI try-on feature for clothes you already have](https://www.theverge.com/tech/920420/google-photos-ai-try-on-wardrobe)** (The Verge): A virtual wardrobe is auto-built from existing gallery photos.
- **[AI evals are becoming the new compute bottleneck](https://huggingface.co/blog/evaleval/eval-costs-bottleneck)** (Hugging Face Blog): Evaluation cost is emerging as a primary constraint on frontier model development.
- **[Granite 4.1 LLMs: How They're Built](https://huggingface.co/blog/ibm-granite/granite-4-1)** (Hugging Face Blog): IBM details the architecture and training pipeline of its latest Granite release.
- **[CISA orders feds to patch Windows flaw exploited as zero-day](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-windows-flaw-exploited-in-zero-day-attacks/)** (BleepingComputer): Federal agencies must remediate an actively exploited Windows vulnerability.
- **[GitHub fixes RCE flaw that gave access to millions of private repos](https://www.bleepingcomputer.com/news/security/github-fixes-rce-flaw-that-gave-access-to-millions-of-private-repos/)** (BleepingComputer): CVE-2026-3854, patched in early March, could have exposed millions of private repositories.
- **[Is AI video just a prequel? Runway's CEO thinks world models are next](https://techcrunch.com/podcast/equity-podcast-runway-ceo-cristobal-valenzuela-ai-video-world-models/)** (TechCrunch): At a $5.3B valuation, Runway sees world models as the natural successor to AI video.
- **[Anthropic launches connectors linking Claude to Adobe, Blender, Ableton, Canva, Autodesk and more](https://gigazine.net/news/20260429-claude-for-creative-work/)** (Gigazine): Anthropic announced creative-tool integrations aimed at expanding Claude into professional creator workflows.

### Europe

- **[Ubuntu's AI plans have Linux users looking for a 'kill switch'](https://www.theverge.com/tech/920723/linux-ubuntu-ai-features-ai-kill-switch)** (The Verge): Canonical's announcement that AI features are coming to Ubuntu has triggered backlash and demands for an AI-free build.
- **[Google rolls out Gemini memory in Europe and wants you to bring your ChatGPT data along](https://the-decoder.com/google-rolls-out-gemini-memory-in-europe-and-wants-you-to-bring-your-chatgpt-data-along/)** (The Decoder): Gemini's memory feature has launched in Europe with import support from competing chatbots.
- **[Mistral's Le Chat spreads Iran war disinformation in 60% of leading prompts](https://the-decoder.com/mistrals-le-chat-spreads-iran-war-disinformation-in-60-percent-of-leading-prompts/)** (The Decoder): The French lab's chatbot performed worst on malicious prompts in a NewsGuard audit.
- **[European police dismantles €50 million crypto investment fraud ring](https://www.bleepingcomputer.com/news/security/european-police-dismantles-50-million-crypto-investment-fraud-ring/)** (BleepingComputer): Austrian and Albanian authorities took down a multinational scam network with worldwide losses over €50M.
- **[Why a recent supply-chain attack singled out security firms Checkmarx and Bitwarden](https://arstechnica.com/information-technology/2026/04/why-a-recent-supply-chain-attack-singled-out-security-firms-checkmarx-and-bitwarden/)** (Ars Technica): A pointed look at why security vendors are uniquely exposed to supply-chain compromise.

### Japan (AI & Tech)

- **["The reasons I cancelled Claude" — German engineer's blog post on token limits, quality drop, and support gaps](https://gigazine.net/news/20260430-why-cancelled-claude/)** (Gigazine): Nicky Reinert documents his decision to cancel Claude, citing token-usage issues, perceived quality decline, and weak support.
- **[Anthropic releases Claude connectors for Adobe, Blender, Ableton, Canva, Autodesk, Resolume, SketchUp and Splice](https://gigazine.net/news/20260429-claude-for-creative-work/)** (Gigazine): Anthropic's new partner integrations target creative-professional workflows directly inside Claude.
- **[OpenAI says its flagship coding benchmark is "no longer meaningful"](https://gigazine.net/news/20260429-swe-bench-verified/)** (Gigazine): Investigating questions models initially failed revealed the benchmark itself was the problem, not the models.
- **[The 9-year road to JavaScript's Temporal API](https://gigazine.net/news/20260429-fix-time-in-javascript/)** (Gigazine): The new ECMAScript Temporal object will replace the legacy `Date` and resolve longstanding date/time pain points.
- **["I bet the company on AI… and failed" — manga "The new hire who got humiliated by generative AI a week later"](https://www.itmedia.co.jp/news/articles/2604/10/news006.html)** (ITmedia AI+): A workplace manga series dramatizing the pitfalls of corporate AI adoption.
- **[U.S. orders chip equipment companies to halt some shipments to China's Hua Hong](https://www.japantimes.co.jp/business/2026/04/29/tech/us-companies-china-chipmaker-hua-hong/)** (The Japan Times): Latest U.S. action aimed at slowing China's advanced-chip development.
- **[Japan's Terra Drone expands investment in Ukraine drone sector](https://www.japantimes.co.jp/business/2026/04/29/companies/terra-drone-ukraine-investment/)** (The Japan Times): Tokyo-based Terra Drone is bringing battlefield-tested unmanned-systems tech back to Japan's defense market.

---

## Research Papers

### Benchmarks & Evaluation

- **[Measuring the Permission Gate: A Stress-Test Evaluation of Claude Code's Auto Mode](https://arxiv.org/abs/2604.04978)**: First independent evaluation of Anthropic's two-stage transcript classifier that gates dangerous tool calls in Claude Code, probing ambiguous-authorization scenarios where intent is clear but blast radius is not.
- **[BenchGuard: Who Guards the Benchmarks? Automated Auditing of LLM Agent Benchmarks](https://arxiv.org/abs/2604.24955)**: Tackles the meta-problem of validating the benchmarks themselves — finding that many "agent failures" are actually broken specifications and rigid evaluation scripts.
- **[Auditing Sabotage Bench: A Benchmark for Detecting and Fixing Research Sabotage in ML Codebases](https://arxiv.org/abs/2604.16286)**: Nine ML research codebases with sabotaged variants used to test whether auditors can detect subtle, results-altering flaws that misaligned AI research agents could introduce.

### Security & Adversarial

- **["Your AI, My Shell": Demystifying Prompt Injection Attacks on Agentic AI Coding Editors](https://arxiv.org/abs/2509.22040)**: Studies prompt-injection threats against tools like Cursor that have terminal access, dev-environment privileges, and external system reach.
- **[Cross-Lingual Jailbreak Detection via Semantic Codebooks](https://arxiv.org/abs/2604.25716)**: Semantic-codebook approach to detecting jailbreak prompts across languages, addressing the multilingual gap in safety classifiers.
- **[PhySE: A Psychological Framework for Real-Time AR-LLM Social Engineering Attacks](https://arxiv.org/abs/2604.23148)**: Models how AR glasses plus an LLM can profile a target and run live social-engineering attacks.

### Compliance & Regulation

- **[Algorithmic Administration and the EU AI Act: Legal Principles for Public Sector Use of AI](https://arxiv.org/abs/2604.22765)**: Examines how the EU AI Act intersects with administrative-law principles like discretion, duty to give reasons, and proportionality in public-sector deployments.
- **[Navigating Global AI Regulation: A Multi-Jurisdictional Retrieval-Augmented Generation System](https://arxiv.org/abs/2604.25448)**: A RAG system over 242 documents across 68 jurisdictions, from formal legislation (EU AI Act) to national AI strategies.
- **[Time-Series Forecasting in Safety-Critical Environments: An EU-AI-Act-Compliant Open-Source Package](https://arxiv.org/abs/2604.23859)**: Compliance-by-design Python forecasting library that anchors EU AI Act requirements inside the library rather than via external scanners.

### Alignment & Safety

- **[Evaluating whether AI models would sabotage AI safety research](https://arxiv.org/abs/2604.24618)**: Anthropic researchers run unprompted-sabotage and continuation-sabotage evaluations across four Claude models (Mythos Preview, Opus 4.7 Preview, Opus 4.6, Sonnet 4.6).
- **[Conditional misalignment: common interventions can hide emergent misalignment behind contextual triggers](https://arxiv.org/abs/2604.25891)**: Shows that interventions reducing emergent misalignment on standard probes can leave it intact under specific contextual triggers — a serious concern for alignment evaluations.

### Applications

- **[RADIANT-LLM: Agentic RAG for Reliable Decision Support in Safety-Critical Nuclear Engineering](https://arxiv.org/abs/2604.22755)**: Multi-modal agentic RAG system that provides traceable, domain-grounded retrieval for nuclear engineering workflows where hallucinations are unacceptable.
- **[Does Machine Unlearning Preserve Clinical Safety? A Risk Analysis for Medical Image Classification](https://arxiv.org/abs/2604.23854)**: Evaluates unlearning methods using clinically asymmetric error costs, going beyond the typical efficiency-and-privacy lens.

### Guardrails & Robustness

- **[BARRED: Synthetic Training of Custom Policy Guardrails via Asymmetric Debate](https://arxiv.org/abs/2604.25203)**: Uses asymmetric debate between policy advocates and adversaries to synthesize training data for custom-policy guardrails.
- **[A Comparative Evaluation of AI Agent Security Guardrails](https://arxiv.org/abs/2604.24826)**: Benchmarks DKnownAI Guard against AWS Bedrock Guardrails, Azure Content Safety, and Lakera Guard on instruction override, indirect injection, and tool abuse.

---

## Key Themes

- **AI as both attack tool and bug-finder.** The same week brought reports of Claude Mythos discovering 271 zero-days in Firefox, AI uncovering 38 flaws in OpenEMR, and DPRK actors using Claude Opus to insert malicious npm code — defenders and attackers are racing on the same axis.
- **Agentic-system safety moves from theory to deployment review.** Independent evaluation of Claude Code's permission gate, prompt-injection studies of Cursor-style coding editors, and direct sabotage-propensity tests of frontier models all signal that agentic-deployment risk is now a measurable property, not an abstract worry.
- **Industry realignment around OpenAI continues.** Microsoft exclusivity dissolved, AWS Bedrock added OpenAI offerings within 24 hours, the White House moved to restore Anthropic federal access, and the Musk v. Altman trial began surfacing founding-era documents — the commercial topology of frontier AI is visibly resetting.
- **Compliance moves into the toolchain.** Papers this cycle embed EU AI Act and ISO/IEC 42001 obligations directly into forecasting libraries, transportation governance frameworks, and multi-jurisdictional regulatory RAG systems — driven by the August 2026 EU AI Act enforcement deadline.
- **AI evaluation itself is becoming the bottleneck.** From "AI evals are becoming the new compute bottleneck" to OpenAI calling its own SWE-Bench scores "no longer meaningful," scrutiny is shifting from how to train better models to how to credibly measure them.

---
*For detailed summaries of selected research papers, see [papers.md](papers.md).*
