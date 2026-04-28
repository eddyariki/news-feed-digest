# AI News Digest — 2026-04-29

## Highlights

- **[Anthropic's Mythos reshapes the cybersecurity landscape](https://www.schneier.com/blog/archives/2026/04/what-anthropics-mythos-means-for-the-future-of-cybersecurity.html)**: Bruce Schneier argues Anthropic's new Claude Mythos Preview — which can autonomously find and weaponize software vulnerabilities — collapses the patch-and-protect window that defenders have long relied on.
- **[Google signs Pentagon AI deal for "any lawful government purpose"](https://www.theverge.com/ai-artificial-intelligence/919494/google-pentagon-classified-ai-deal)**: Google inked a classified contract giving the DoD broad access to its AI models a day after 600+ employees demanded Sundar Pichai block the deal, and after Anthropic refused similar work.
- **[Microsoft and OpenAI end exclusivity; OpenAI lands on AWS](https://techcrunch.com/2026/04/28/amazon-is-already-offering-new-openai-products-on-aws/)**: Within a day of renegotiating the Azure-exclusive pact, OpenAI's GPT models, Codex, and Managed Agents went live on AWS — a dramatic restructuring of the cloud-AI landscape.
- **[Musk v. Altman OpenAI trial opens with bitter testimony](https://www.theverge.com/ai-artificial-intelligence/917052/elon-musk-takes-stand-trial-openai-sam-altman)**: Elon Musk took the stand to argue he is trying to "save humanity," kicking off a trial expected to expose the secrets of OpenAI's founding power struggle.
- **[Critical flaws in AI infrastructure exploited in the wild](https://thehackernews.com/2026/04/critical-cve-2026-25874-leaves-hugging.html)**: Hugging Face's LeRobot platform has an unpatched CVSS-9.3 unauthenticated RCE, while attackers are actively exploiting a pre-auth SQLi in the LiteLLM gateway (CVE-2026-42208) — AI tooling itself is now a target surface.

---

## News

### AI Security

- **GitHub CVE-2026-3854 RCE via single git push** — The Hacker News reports a CVSS-8.7 command-injection flaw on GitHub.com and Enterprise Server that lets an authenticated user with push access achieve remote code execution. ([link](https://thehackernews.com/2026/04/researchers-discover-critical-github.html))
- **LiteLLM pre-auth SQLi actively exploited** — Attackers are targeting sensitive data in the LiteLLM open-source LLM gateway via CVE-2026-42208. ([link](https://www.bleepingcomputer.com/news/security/hackers-are-exploiting-a-critical-litellm-pre-auth-sqli-flaw/))
- **Hugging Face LeRobot unauthenticated RCE** — CVE-2026-25874 (CVSS 9.3) stems from untrusted-data deserialization in the 24k-star robotics platform. ([link](https://thehackernews.com/2026/04/critical-cve-2026-25874-leaves-hugging.html))
- **Microsoft Entra ID role flaw enables takeover** — A privileged AI-agent administrator role could be abused for privilege escalation and identity takeover, per Silverfort. ([link](https://thehackernews.com/2026/04/microsoft-patches-entra-id-role-flaw.html))
- **Microsoft Windows Shell CVE-2026-32202 actively exploited** — Microsoft revised its advisory for the spoofing flaw to confirm in-the-wild attacks. ([link](https://thehackernews.com/2026/04/microsoft-confirms-active-exploitation.html))
- **VECT 2.0 ransomware destroys files instead of encrypting** — A nonce-handling bug means files over ~131KB are wiped on Windows, Linux, and ESXi — even paying victims can't recover. ([link](https://www.bleepingcomputer.com/news/security/broken-vect-20-ransomware-acts-as-a-data-wiper-for-large-files/))
- **GlassWorm VS Code extensions return** — A new wave of self-propagating malware is hitting Open VSX as benign-looking extensions. ([link](https://www.darkreading.com/application-security/fresh-glassworm-vs-code-extensions-supply-chain))
- **Vidar tops the infostealer market** — Vidar has filled the vacuum left by last year's Lumma and Rhadamanthys takedowns. ([link](https://www.darkreading.com/vulnerabilities-threats/vidar-top-chaotic-infostealer-market))
- **Feuding ransomware groups leak each other's data** — A spat between 0APT and KryBit exposed both gangs' infrastructure to defenders. ([link](https://www.darkreading.com/threat-intelligence/feuding-ransomware-groups-leak-data))
- **Vimeo confirms Anodot breach exposed user data** — Customer data was accessed via the third-party anomaly-detection vendor. ([link](https://www.bleepingcomputer.com/news/security/video-service-vimeo-confirms-anodot-breach-exposed-user-data/))
- **LAPSUS$ leaks Checkmarx's stolen GitHub data** — The application-security firm confirmed the exposure of its private repository. ([link](https://www.bleepingcomputer.com/news/security/checkmarx-confirms-lapsus-hackers-leaked-its-stolen-github-data/))
- **Brazilian LofyGang resurfaces with Minecraft LofyStealer** — A cybercrime group returns after three years, distributing malware disguised as a "Slinky" Minecraft hack. ([link](https://thehackernews.com/2026/04/brazilian-lofygang-resurfaces-after.html))
- **US charges Scattered Spider hacker arrested in Finland** — A 19-year-old dual US/Estonian citizen faces federal charges over the prolific hacking collective. ([link](https://www.bleepingcomputer.com/news/security/us-reportedly-charges-scattered-spider-hacker-arrested-in-finland/))
- **Chinese Silk Typhoon hacker extradited from Italy** — Xu Zewei faces US charges over COVID-research cyberattacks attributed to the state-sponsored group. ([link](https://thehackernews.com/2026/04/chinese-silk-typhoon-hacker-extradited.html))
- **NSA chief during Snowden affair reflects 13 years later** — Chris Inglis on what CISOs should learn about insider threat and "enculturation." ([link](https://www.darkreading.com/cyber-risk/nsa-chief-during-snowden-affair-13-years-later))
- **OPSEC playbooks now circulate among threat actors** — Flare details how attackers publish structured guides on identity separation and long-term evasion. ([link](https://www.bleepingcomputer.com/news/security/inside-an-opsec-playbook-how-threat-actors-evade-detection/))
- **Schneier on the Mythos era of cybersecurity** — A long-form analysis of how autonomous exploit generation rewrites incident-response timelines. ([link](https://www.schneier.com/blog/archives/2026/04/what-anthropics-mythos-means-for-the-future-of-cybersecurity.html))
- **The Verge on AI bug-finding "script kiddies"** — How DARPA's AIxCC primed both defenders and attackers for autonomous vulnerability discovery. ([link](https://www.theverge.com/ai-artificial-intelligence/915660/mythos-script-kiddies-hackers-attack-cybersecurity-ai))
- **"After Mythos" — patching alone no longer fits** — The Hacker News on why network-detection-and-response is becoming the last line of defense in a zero-window era. ([link](https://thehackernews.com/2026/04/after-mythos-new-playbooks-for-zero.html))
- **Microsoft to deprecate legacy TLS in Exchange Online** — POP/IMAP clients on old TLS versions will be blocked starting July 2026. ([link](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-deprecate-legacy-tls-in-exchange-online-starting-july/))

### USA

- **OpenAI products go live on AWS within 24 hours of MS deal change** — Amazon announced a slate of GPT, Codex, and a new Managed Agents service. ([link](https://techcrunch.com/2026/04/28/amazon-is-already-offering-new-openai-products-on-aws/) · [OpenAI](https://openai.com/index/openai-on-aws))
- **Microsoft and OpenAI renegotiate exclusivity** — Reuters via Yomiuri reports the new terms clear OpenAI to court Amazon and other rivals. ([link](https://japannews.yomiuri.co.jp/news-services/reuters/20260428-324868/))
- **Google signs classified Pentagon AI deal** — Reportedly grants the DoD use of Google models for "any lawful government purpose" after an Anthropic refusal. ([link](https://techcrunch.com/2026/04/28/google-expands-pentagons-access-to-its-ai-after-anthropics-refusal/) · [Verge](https://www.theverge.com/ai-artificial-intelligence/919494/google-pentagon-classified-ai-deal) · [Decoder](https://the-decoder.com/google-signs-ai-deal-with-the-pentagon-ignoring-protest-from-over-600-employees/))
- **Musk takes the stand against OpenAI** — Musk testified that all he wants to do is "save humanity"; jurors had pre-existing strong opinions of him. ([link](https://www.theverge.com/ai-artificial-intelligence/920048/elon-musk-testimony-save-humanity) · [Verge jury](https://www.theverge.com/tech/919469/elon-musk-dont-like) · [Vergecast](https://www.theverge.com/podcast/919534/musk-openai-trial-vergecast))
- **OpenAI misses Q1 2026 revenue targets** — Anthropic and Google are gaining ground while internal tensions over spending grow. ([link](https://the-decoder.com/openai-misses-revenue-targets-as-anthropic-and-google-close-in/))
- **Anthropic launches Claude creative connectors** — Direct integrations into Photoshop, Blender, Ableton, Affinity, Autodesk, and more. ([link](https://www.theverge.com/ai-artificial-intelligence/919648/anthropic-claude-creative-connectors-adobe-blender))
- **Amazon adds AI audio Q&A to product pages** — A new "Join the chat" feature delivers AI-generated audio answers about products. ([link](https://techcrunch.com/2026/04/28/amazon-launches-an-ai-powered-audio-qa-experience-on-product-pages/))
- **YouTube AI search rolls out to US Premium subscribers** — Opt-in feature delivers guided answers; sister "Ask YouTube" turns search into a chat. ([link](https://techcrunch.com/2026/04/28/youtube-is-testing-an-ai-powered-search-feature-that-shows-guided-answers/) · [Decoder](https://the-decoder.com/googles-ask-youtube-turns-video-search-into-a-conversation/))
- **GitHub Copilot moves to token-based billing** — From June 1, 2026 charges shift from premium-request counts to actual usage. ([link](https://the-decoder.com/github-copilot-switches-to-token-based-billing-in-june-2026/))
- **Mistral launches Workflows for enterprise AI orchestration** — Aimed at productionizing AI processes inside companies. ([link](https://the-decoder.com/mistral-ai-takes-on-enterprise-ai-orchestration-with-workflows/))
- **Lovable ships its vibe-coding app on iOS and Android** — Users can build web apps and sites on the go. ([link](https://techcrunch.com/2026/04/28/lovable-launches-its-vibe-coding-app-on-ios-and-android/))
- **Otter expands enterprise search across tools** — Connects Gmail, Google Drive, Notion, Jira, and Salesforce alongside meeting data. ([link](https://techcrunch.com/2026/04/28/otters-new-feature-lets-users-search-across-their-enterprise-tools/))
- **Red Hat container hardens enterprise OpenClaw deployments** — Tank OS gives agent fleets a more reliable, safer runtime. ([link](https://techcrunch.com/2026/04/28/red-hats-openclaw-maintainer-just-made-enterprise-claw-deployments-a-lot-safer/))
- **NVIDIA introduces Nemotron 3 Nano Omni** — Long-context multimodal model for documents, audio, and video agents. ([link](https://huggingface.co/blog/nvidia/nemotron-3-nano-omni-multimodal-intelligence))
- **Neurable seeks to license non-invasive BCI for wearables** — The startup pitches a consumer "mind-reading" sensor stack. ([link](https://techcrunch.com/2026/04/28/bci-startup-neurable-looks-to-license-its-mind-reading-tech-for-consumer-wearables/))
- **Taylor Swift trademarks her voice and likeness** — Filings target audio and image deepfakes; lawyers call it a long shot. ([link](https://www.theverge.com/ai-artificial-intelligence/919827/taylor-swift-trademarks-ai-copycats))
- **"Talkie" — a 13B model trained only on pre-1931 text** — Doubts a Second World War occurred and pictures 2026 as steamships and penny novels. ([link](https://the-decoder.com/here-is-what-an-llm-that-knows-nothing-after-1930-thinks-our-world-looks-like-in-2026/))
- **Researchers find AI text is making the web more uniform and cheerful** — Internet Archive analysis shows just how saturated public-web text has become. ([link](https://the-decoder.com/researchers-find-ai-text-is-making-the-internet-more-uniform-and-weirdly-cheerful/))
- **Humanitarian aid turns to AI as crises outpace capacity** — Purpose-built agents are being used to triage assistance for vulnerable populations. ([link](https://restofworld.org/2026/irc-signpost-humanitarian-ai-refugee-assistance/))
- **Trump administration fires entire National Science Board** — The 1950-era panel advised Congress and the president on science policy. ([link](https://www.japantimes.co.jp/news/2026/04/28/world/science-health/trump-national-science-board-fire/))
- **Google Translate turns 20** — Google highlights new live-translation features alongside the anniversary. ([link](https://blog.google/products-and-platforms/products/translate/fun-facts-google-translate-20-years/))

### Europe

- **EU pushes Google to open Android to rival AI services** — Brussels wants third-party access to voice activation and other core Android hooks; Google calls it "undue interference." ([link](https://gigazine.net/news/20260428-eu-android-ai-open/))

### Japan (AI & Tech)

- **Fujitsu CEO warns Japan's AI is falling behind** — Takahito Tokita's SusHi Tech 2026 keynote sounded the alarm on the country's current trajectory. ([link](https://japannews.yomiuri.co.jp/business/economy/20260428-324830/))
- **NTT to triple data-center capacity for AI** — President Akira Shimada says inference workloads are driving the buildout to 3× current power capacity by FY2033. ([link](https://www.itmedia.co.jp/news/articles/2604/28/news064.html))
- **Tokyo Electron exec on what's really behind the AI chip shortage** — A frank look at the supply-side dynamics from a major equipment maker. ([link](https://www.itmedia.co.jp/business/articles/2604/28/news099.html))
- **SusHi Tech Tokyo 2026 spotlights AI and robotics** — Business leaders and researchers debate the next phase of AI; experts praise Japan's high public acceptance. ([link](https://japannews.yomiuri.co.jp/business/economy/20260428-324832/) · [next phase](https://japannews.yomiuri.co.jp/business/economy/20260428-324869/))
- **DeNA, GO, GO Drive open-source 100+ AI study materials** — The three Japanese firms publish their internal AI training decks for free. ([link](https://www.itmedia.co.jp/aiplus/articles/2604/28/news106.html))
- **Singapore emerges as AI's "neutral ground"** — ITmedia analyzes how the city-state is becoming the third pole as US-China tech rivalry intensifies. ([link](https://www.itmedia.co.jp/aiplus/articles/2604/28/news095.html))
- **Zoom doubles down on conversational AI in Japan** — Marketing exec explains how Zoom plans to differentiate from Teams and Meet by focusing on phone calls and cost-performance. ([link](https://www.itmedia.co.jp/aiplus/articles/2604/28/news061.html))
- **"Vibe coding" security risks — three things companies must do** — ITmedia walks through the new attack surface created by AI-generated code. ([link](https://www.itmedia.co.jp/aiplus/articles/2604/28/news006.html))
- **OpenAI ends Microsoft exclusivity, lands on Amazon Bedrock** — ITmedia covers the reshaped distribution map for OpenAI's products. ([link](https://www.itmedia.co.jp/aiplus/articles/2604/28/news088.html))
- **OpenAI builds "Symphony" to manage Codex agents at scale** — Internal teams reportedly saw 5× pull-request volume after deploying the orchestration tool. ([link](https://gigazine.net/news/20260428-openai-symphony/))
- **Xiaomi releases MiMo-V2.5-Pro as open weights** — Positioned as surpassing Gemini 3.1 Pro and approaching Claude Opus 4.6. ([link](https://gigazine.net/news/20260428-xiaomi-mimo-v2-5-pro/))
- **Alibaba's HappyHorse 1.0 video AI opens to all** — Reportedly tops Artificial Analysis benchmarks and supports Japanese-language dialogue. ([link](https://gigazine.net/news/20260428-happyhorse-1-video-generation-ai-review/))
- **Google Research's TurboQuant explained** — A first-principles walkthrough of the new compression technique aimed at slashing AI memory footprints. ([link](https://gigazine.net/news/20260428-turboquant-a-first-principles-walkthrough/))
- **WordPress.com launches Studio Code agentic CLI** — Free beta for an AI coding tool focused on WordPress development. ([link](https://gigazine.net/news/20260428-wordpress-studio-code/))
- **OpenAI reportedly developing an AI-first iPhone competitor** — Supply-chain analyst Ming-Chi Kuo says hardware work is underway. ([link](https://gigazine.net/news/20260428-openai-ai-smartphone/))
- **Pre-Stuxnet US sabotage malware "fast16" discovered** — SentinelOne attributes the find to an earlier-generation sabotage tool predating the 2010 Stuxnet operation. ([link](https://gigazine.net/news/20260428-pre-stuxnet-sabotage-malware-fast16/))
- **Samsung Galaxy Glasses leaked** — Samsung's smart-glasses for late-2026 release have surfaced with apparent specs. ([link](https://gigazine.net/news/20260428-samsung-galaxy-glasses/))
- **Beijing blocks Meta's $2B Manus acquisition** — China's state planner cancels the AI-startup deal months after closing; Meta scrambles to unwind. ([link](https://gigazine.net/news/20260428-china-blocks-meta-acquire-manus/) · [Decoder](https://the-decoder.com/meta-scrambles-to-unwind-manus-deal-as-beijings-deadline-looms/))
- **Canva's AI silently swapped "Palestine" for other terms** — A bug in Canva's auto-rewrite feature replaced the word in user-facing text. ([link](https://gigazine.net/news/20260428-canva-apologizes-ai-replaces-palestine/))
- **Compromised Elementary Python CLI used to steal user credentials** — A 1M+ download/month open-source package was tampered with via a developer-account workflow flaw. ([link](https://gigazine.net/news/20260428-elementary-data-stole-user-credentials/))

---

## Research Papers

### Benchmarks & Evaluation

- **ProEval: Proactive Failure Discovery and Efficient Performance Estimation for Generative AI Evaluation** — A framework for cheap, proactive failure-mode discovery as model and benchmark counts explode. ([link](https://arxiv.org/abs/2604.23099))
- **Quantifying and Mitigating Self-Preference Bias of LLM Judges** — Shows the dominant LLM-as-a-Judge paradigm systematically favors its own outputs and proposes a bias-mitigation pipeline. ([link](https://arxiv.org/abs/2604.22891))

### Security & Adversarial

- **Evaluating Jailbreaking Vulnerabilities in LLMs Deployed as Assistants for Smart Grid Operations** — Builds a NERC-aligned benchmark exposing how LLM grid assistants buckle under prompt-based attacks. ([link](https://arxiv.org/abs/2604.23341))
- **From Stateless Queries to Autonomous Actions: A Layered Security Framework for Agentic AI Systems** — Threat-model and defense layering aimed at planning, persistent memory, tool use, and peer-agent coordination. ([link](https://arxiv.org/abs/2604.23338))
- **PARASITE: Conditional System Prompt Poisoning to Hijack LLMs** — A supply-chain attack that hides triggers in third-party system prompts pulled from public marketplaces. ([link](https://arxiv.org/abs/2505.16888))

### Compliance & Regulation

- **ComplianceNLP: Knowledge-Graph-Augmented RAG for Multi-Framework Regulatory Gap Detection** — Targets the 60,000+ regulatory events that financial institutions track annually; aims to surface compliance gaps automatically. ([link](https://arxiv.org/abs/2604.23585))

### Alignment & Safety

- **Jailbreaking Frontier Foundation Models Through Intention Deception** — Demonstrates that learned safety boundaries don't generalize against attackers who hide adversarial intent. ([link](https://arxiv.org/abs/2604.24082))
- **Structural Enforcement of Goal Integrity in AI Agents via Separation-of-Powers Architecture** — Borrows constitutional design to prevent agents from constructing and executing internal misaligned goals. ([link](https://arxiv.org/abs/2604.23646))

### Guardrails & Robustness

- **LAVA: Layered Audio-Visual Anti-tampering Watermarking for Robust Deepfake Detection and Localization** — Couples audio and visual watermark layers to harden deepfake detection on short-form video. ([link](https://arxiv.org/abs/2604.23957))
- **MERIT: Modular Framework for Multimodal Misinformation Detection with Web-Grounded Reasoning** — Decomposes verification into visual forensics, cross-modal alignment, and retrieval-augmented claim checking. ([link](https://arxiv.org/abs/2510.17590))

### Applications

- **One Size Fits None: Heuristic Collapse in LLM Investment Advice** — Finds LLMs collapse to a few generic strategies regardless of user financial context — a real-world risk in retail advice. ([link](https://arxiv.org/abs/2604.23837))
- **AI Safety Training Can be Clinically Harmful** — Warns that generic safety training degrades LLM mental-health support; only 16% of LLM-based chatbot interventions have undergone rigorous clinical testing. ([link](https://arxiv.org/abs/2604.23445))

---

## Key Themes

- **AI infrastructure is now a primary attack surface.** Critical RCE in Hugging Face LeRobot, exploited SQLi in LiteLLM, supply-chain compromise of an Elementary Python package, and a Microsoft Entra ID role flaw aimed at AI agents — the tooling stack itself is the perimeter.
- **Autonomous offense is here.** Anthropic's Claude Mythos Preview and Project Glasswing collapse the patch window; commentators across Schneier, The Verge, and The Hacker News are converging on "zero-window" defense playbooks.
- **The OpenAI–Microsoft monopoly era ends.** Renegotiated terms put OpenAI on AWS Bedrock within a day, while OpenAI misses Q1 revenue targets and faces growing pressure from Anthropic and Google.
- **AI militarization accelerates.** Google takes Pentagon classified work that Anthropic refused, despite open dissent from 600+ employees; legal experts note the "safety clauses" are not legally binding.
- **Agentic safety dominates the research agenda.** New papers tackle jailbreaks via intention deception, separation-of-powers goal integrity, layered agent security, and context-fragmented multi-agent violations.
- **Japan's AI position is at an inflection point.** Fujitsu's CEO warns Japan is falling behind, NTT is tripling data-center capacity for inference, and SusHi Tech 2026 frames the next phase as one Japan must actively invest in.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
