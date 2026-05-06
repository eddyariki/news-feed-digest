# AI News Digest — 2026-05-07

## Highlights

- **[Anthropic takes 220,000 GPUs at SpaceX Colossus-1](https://the-decoder.com/anthropic-taps-spacexs-colossus-1-data-center-for-220000-gpus-to-power-claude/)**: Anthropic absorbs the full 300+ MW of SpaceX's Colossus-1 data center to power Claude, doubling Claude Code rate limits and dramatically raising Opus API limits.
- **[OpenAI ships MRC networking protocol with chip giants](https://openai.com/index/mrc-supercomputer-networking)**: OpenAI, AMD, Broadcom, Intel, Microsoft, and NVIDIA released MRC, an open multipath protocol that wires 100,000+ GPUs through two switch layers instead of three or four.
- **[Palo Alto PAN-OS RCE under active exploitation](https://thehackernews.com/2026/05/palo-alto-pan-os-flaw-under-active.html)**: CVE-2026-0300 (CVSS 9.3) is being exploited in the wild against the User-ID Authentication Portal, with no patch available at disclosure.
- **[Rowhammer attack gives full control of NVIDIA GPUs](https://www.schneier.com/blog/archives/2026/05/rowhammer-attack-against-nvidia-chips.html)**: Two independent research teams demonstrated GDDR bit-flips on Ampere-generation cards that escalate to full system compromise of the host.
- **[Anthropic commits $200B to Google Cloud over five years](https://the-decoder.com/anthropic-commits-200-billion-to-google-cloud-over-five-years/)**: The deal accounts for more than 40 percent of Google's entire cloud backlog, underscoring the scale of frontier-AI capex commitments.

---

## News

### AI Security

- **[Palo Alto PAN-OS RCE under active exploitation](https://thehackernews.com/2026/05/palo-alto-pan-os-flaw-under-active.html)**: An unauthenticated buffer-overflow in the User-ID Authentication Portal (CVE-2026-0300, CVSS 9.3) is being weaponized in the wild before a patch exists; [BleepingComputer](https://www.bleepingcomputer.com/news/security/palo-alto-networks-warns-of-actively-exploited-firewall-zero-day/) flagged it as an open zero-day.
- **[Rowhammer Attack Against NVIDIA Chips](https://www.schneier.com/blog/archives/2026/05/rowhammer-attack-against-nvidia-chips.html)**: New research shows GDDR bit-flips on Ampere-generation NVIDIA cards yield full control of CPU memory and host compromise when IOMMU is disabled (the default).
- **[Critical vm2 sandbox bug lets attackers execute code on hosts](https://www.bleepingcomputer.com/news/security/critical-vm2-sandbox-bug-lets-attackers-execute-code-on-hosts/)**: A critical flaw in the popular Node.js sandboxing library vm2 allows escape and arbitrary code execution on the host.
- **[Yet Another Way to Bypass Google Chrome's Encryption Protection](https://www.darkreading.com/endpoint-security/yet-another-way-bypass-google-chromes-encryption-protection)**: VoidStealer authors found a bypass for Chrome's App-Bound Encryption (ABE), reopening the door for credential-stealing infostealers.
- **[Mirai-Based xlabs_v1 Botnet Exploits ADB to Hijack IoT Devices](https://thehackernews.com/2026/05/mirai-based-xlabsv1-botnet-exploits-adb.html)**: A new Mirai variant, xlabs_v1, harvests internet-exposed Android Debug Bridge endpoints to power DDoS attacks.
- **[DAEMON Tools devs confirm breach, release malware-free version](https://www.bleepingcomputer.com/news/security/daemon-tools-devs-confirm-breach-release-malware-free-version/)**: Disc Soft confirmed DAEMON Tools Lite was trojanized in a supply chain attack and shipped a clean rebuild.
- **[MuddyWater Uses Microsoft Teams as a False-Flag Ransomware Vector](https://thehackernews.com/2026/05/muddywater-uses-microsoft-teams-to.html)**: Iran-linked MuddyWater leveraged Teams social engineering and disguised intrusions as Chaos ransomware to obscure attribution; [BleepingComputer covers the campaign](https://www.bleepingcomputer.com/news/security/muddywater-hackers-use-chaos-ransomware-as-a-decoy-in-attacks/).
- **[New Cisco DoS flaw requires manual reboot to revive devices](https://www.bleepingcomputer.com/news/security/new-cisco-dos-flaw-requires-manual-reboot-to-revive-devices/)**: A patched Crosswork/NSO denial-of-service bug knocks devices offline until they are physically rebooted.
- **[Windows Phone Link Exploited by CloudZ RAT to Steal Credentials and OTPs](https://thehackernews.com/2026/05/windows-phone-link-exploited-by-cloudz.html)**: CloudZ RAT plus a new Pheno plugin pivot through the Windows–phone bridge to steal SMS messages and bypass 2FA, per [Dark Reading](https://www.darkreading.com/cyberattacks-data-breaches/attacks-abuse-windows-phone-link-texts-bypass-2fa).
- **[Instructure Breach Exposes Schools' Vendor Dependence](https://www.darkreading.com/cyberattacks-data-breaches/instructure-breach-exposes-schools-vendor-dependence)**: ShinyHunters' attack on the operator of the Canvas LMS raises hard questions about EdTech vendor risk.
- **[Hackers abuse Google ads for GoDaddy ManageWP login phishing](https://www.bleepingcomputer.com/news/security/hackers-abuse-google-ads-for-godaddy-managewp-login-phishing/)**: Google sponsored search results are being used to harvest credentials for the platform that manages WordPress fleets.
- **[Google's Android Apps Get Public Verification to Stop Supply Chain Attacks](https://thehackernews.com/2026/05/android-apps-get-public-verification.html)**: Google extended Binary Transparency to Android with a public ledger so devices can verify Google apps match the published builds.
- **[Middle East Cyber Battle Field Broadens — Especially in UAE](https://www.darkreading.com/cyberattacks-data-breaches/middle-east-cyber-battle-field-broadens-uae)**: Breach attempts targeting the UAE tripled in weeks, with critical infrastructure as the principal target.
- **[Your AI Agents Are Already Inside the Perimeter](https://thehackernews.com/2026/05/your-ai-agents-are-already-inside.html)**: Gartner's first Guardian Agents guide warns that enterprise AI agent rollouts are outrunning identity-governance controls.
- **[Why ransomware attacks succeed even when backups exist](https://www.bleepingcomputer.com/news/security/why-ransomware-attacks-succeed-even-when-backups-exist/)**: Acronis details how operators destroy backup infrastructure before encryption, leaving no recovery path.

### USA

- **[Anthropic taps SpaceX's Colossus-1 for 220,000 GPUs](https://the-decoder.com/anthropic-taps-spacexs-colossus-1-data-center-for-220000-gpus-to-power-claude/)**: Anthropic takes the full Colossus-1 capacity online within a month and lifts Opus and Claude Code limits.
- **[Anthropic commits $200 billion to Google Cloud over five years](https://the-decoder.com/anthropic-commits-200-billion-to-google-cloud-over-five-years/)**: The commitment covers >40% of Google's entire cloud backlog and pairs with similar OpenAI flows to AWS/Azure/Oracle.
- **[OpenAI built MRC networking with AMD, Broadcom, Intel, Microsoft, NVIDIA](https://the-decoder.com/openai-built-a-networking-protocol-with-amd-broadcom-intel-microsoft-and-nvidia-to-fix-ai-supercomputer-bottlenecks/)**: An [open OCP-released spec](https://openai.com/index/mrc-supercomputer-networking) cuts switch layers from 3–4 to 2 across 100K+ GPUs, already in use on Stargate.
- **[Is xAI a neocloud now?](https://techcrunch.com/2026/05/06/is-xai-a-neocloud-now/)**: Reporting suggests xAI's actual business is data-center buildout, not just model training.
- **[SpaceX may spend up to $119B on 'Terafab' chip factory in Texas](https://techcrunch.com/2026/05/06/spacex-may-spend-up-to-119-billion-on-terafab-chip-factory-in-texas/)**: A "multi-phase, vertically integrated" semiconductor and compute fab is in the proposal stage.
- **[How David Sacks crashed and burned in the White House](https://www.theverge.com/column/925487/david-sacks-trump-administration-ai-model-review)**: Verge column dissects the AI/policy fallout from Sacks's tenure as AI advisor.
- **[Mira Murati: she "couldn't trust Sam Altman's words"](https://www.theverge.com/ai-artificial-intelligence/925338/openai-musk-v-altman-mira-murati)**: Murati testified under oath in the Musk v. Altman trial that Altman misrepresented model safety review to her; Greg Brockman also gave [his account of Musk's exit](https://techcrunch.com/2026/05/06/how-elon-musk-left-openai-according-to-greg-brockman/).
- **[Apple to pay $250M to settle Siri AI delays lawsuit](https://techcrunch.com/2026/05/06/apple-to-pay-250m-to-settle-lawsuit-over-siris-delayed-ai-features/)**: Class-action settled over overpromised Apple Intelligence features.
- **[Google speeds up Gemma 4 threefold with multi-token prediction](https://the-decoder.com/google-speeds-up-gemma-4-threefold-with-multi-token-prediction/)**: A small drafter model proposes several tokens that the main model verifies in one pass.
- **[ChatGPT ads now open to small businesses](https://the-decoder.com/chatgpt-ads-are-now-open-to-small-businesses-as-openai-builds-a-full-self-serve-ad-platform/)**: OpenAI dropped the $50K ad minimum, targeting $2.5B in 2026 ad revenue.
- **[Google updates AI search to quote Reddit and forums](https://techcrunch.com/2026/05/06/google-updates-ai-search-to-include-expert-advice-from-reddit-and-other-web-forums/)**: AI Overviews surface "perspectives" from social media and discussion boards; [The Verge](https://www.theverge.com/tech/924993/google-ai-search-mode-overviews-update-reddit-links) covers the rollout.
- **[Google and Meta race to ship personal AI agents](https://the-decoder.com/google-and-meta-race-to-build-personal-ai-agents-as-anthropic-and-openai-pull-further-ahead/)**: Internal projects "Remy" and "Hatch" pivot away from browser agents toward email/calendar/shopping integrations as Anthropic and OpenAI lead.
- **[Genesis AI unveils GENE-26.5 robotic foundation model](https://techcrunch.com/2026/05/06/khosla-backed-robotics-startup-genesis-ai-has-gone-full-stack-demo-shows/)**: The Khosla-backed startup demoed a full-stack robotic-hands manipulation model after raising a $105M seed.
- **[Match Group slows hiring to fund AI tooling spend](https://techcrunch.com/2026/05/06/tinder-owner-match-group-is-slowing-hiring-to-pay-for-its-increased-use-of-ai-tools/)**: Tinder's parent says AI "costs a lot of money" and headcount is being reallocated.
- **[Microsoft's Office and LinkedIn chief now runs Teams](https://www.theverge.com/tech/924931/microsoft-office-copilot-windows-reorg-shuffle)**: Ryan Roslansky absorbs Teams under a new "Work" group in Microsoft's latest reshuffle.
- **[Chrome's AI features may be hogging 4GB of storage](https://www.theverge.com/tech/924933/google-chrome-4gb-gemini-nano-ai-features)**: Users report Chrome silently downloading a ~4GB Gemini Nano weights.bin to system folders.
- **[Marc Lore says AI will let anyone open a restaurant](https://techcrunch.com/2026/05/05/marc-lore-says-that-ai-will-soon-enable-anyone-open-a-restaurant/)**: Wonder pitches its robotic kitchens as AI-driven "restaurant factories" launchable from a prompt.
- **[OpenAI launches ChatGPT Futures: Class of 2026](https://openai.com/index/introducing-chatgpt-futures-class-of-2026)**: OpenAI showcases 26 student innovators using ChatGPT for research and product work.
- **[How frontier enterprises are building an AI advantage](https://openai.com/index/introducing-b2b-signals)**: OpenAI's B2B Signals research details Codex agentic-workflow adoption patterns.
- **[Ethos raises $22.75M from a16z for expert network](https://techcrunch.com/2026/05/06/ethos-raises-22-75m-from-a16z-for-its-expert-network-with-voice-onboarding/)**: Voice-onboarding-first network claims 35,000 expert sign-ups per week.
- **[Peter Sarlin's QuTwo hits $380M valuation in angel round](https://techcrunch.com/2026/05/05/peter-sarlins-qutwo-reaches-380m-valuation-in-angel-round/)**: Finland-based enterprise-AI/quantum startup raises with "AI is the north star" pitch.
- **[DeepSeek nears $45B valuation as China state chip fund leads](https://the-decoder.com/deepseek-nears-45-billion-valuation-as-chinas-state-chip-fund-leads-round/)**: First investment round priced by FT reporting; [TechCrunch](https://techcrunch.com/2026/05/06/deepseek-could-hit-45b-valuation-from-its-first-investment-round/) covers the milestone.

### Europe

- **[Peter Sarlin's QuTwo reaches $380M valuation in angel round](https://techcrunch.com/2026/05/05/peter-sarlins-qutwo-reaches-380m-valuation-in-angel-round/)**: Finnish enterprise AI/quantum startup attracts angel investors with an unusually large pre-seed.

### Japan (AI & Tech)

- **[Government to launch AI pilot program across 39 agencies](https://www.japantimes.co.jp/news/2026/05/06/japan/japan-government-agencies-ai/)**: "Gennai", a generative AI platform built for civil servants, will be deployed broadly across the Japanese government.
- **[Samsung hits $1 trillion valuation, joining TSMC](https://www.japantimes.co.jp/business/2026/05/06/tech/samsung-1t-valuation-tsmc/)**: Memory-chip demand from AI more than quadrupled Samsung's stock over a year, making it the second Asian $1T tech firm; TechCrunch [tracks the implications](https://techcrunch.com/2026/05/06/ai-boom-pushes-samsung-to-1t/).
- **[Nvidia is facing more competition and it's spooking investors](https://www.japantimes.co.jp/business/2026/05/06/nvidia-competition-investors/)**: Japan Times reports Nvidia's AI-processor lead is increasingly threatened by both rival chipmakers and large customers.
- **[Meta、AIで13歳未満を自動検出](https://www.itmedia.co.jp/news/articles/2605/06/news033.html)**: Meta is rolling out under-13 detection AI on Facebook and Instagram and lobbying for OS-level age verification mandates.
- **[Google Chrome 148: Gemini Nano usable from web pages](https://gigazine.net/news/20260506-google-chrome-148/)**: Chrome 148 ships container-query naming, lazy media loading, and exposes the on-device Gemini Nano model to web sites.
- **[Mayo Clinic's pancreatic-cancer AI spots tumors 3 years early](https://gigazine.net/news/20260506-ai-cancer/)**: An AI trained on routine CT imagery flags subtle changes preceding visible tumors.
- **[Google Pixel 10a hands-on: the camera bump is gone](https://gigazine.net/news/20260506-google-pixel-10a-appearance/)**: First look at the under-¥80,000 Pixel 10a, with a flat back replacing the signature camera bar.
- **[AMD Ryzen AI 7 350 in Acer Swift Air 16 (990g)](https://gigazine.net/news/20260506-swift-air-16-benchmark/)**: Benchmark, battery, and thermal review of an ultra-light Ryzen-AI laptop.
- **[Xbox CEO: no Copilot for game consoles](https://gigazine.net/news/20260506-microsoft-copilot-no-longer-consoles-xbox-ceo/)**: Asha Sharma says Microsoft will not bring Copilot to its consoles.
- **[Cherri: a programming language for Apple Shortcuts](https://gigazine.net/news/20260506-cherri/)**: A textual DSL compiles to Apple Shortcuts so complex automations stay readable.

---

## Research Papers

### Benchmarks & Evaluation

- **[PhysicianBench: Evaluating LLM Agents in Real-World EHR Environments](https://arxiv.org/abs/2605.02240)**: Benchmark grounding LLM physicians in actual EHR systems, measuring composite long-horizon clinical workflows beyond static knowledge recall.
- **[Reward Hacking Benchmark: Measuring Exploits in LLM Agents with Tool Use](https://arxiv.org/abs/2605.02964)**: Suite for quantifying how often RL-trained tool-using agents game their reward signals when deployed in coding/research settings.
- **[Evaluating Agentic AI in the Wild: Failure Modes, Drift Patterns, and a Production Evaluation Framework](https://arxiv.org/abs/2605.01604)**: Argues lab benchmarks (HELM, MT-Bench, AgentBench) miss compounding errors, tool-failure cascades, and output drift in production agents, and proposes a framework that captures them.

### Security & Adversarial

- **[RouteHijack: Routing-Aware Attack on Mixture-of-Experts LLMs](https://arxiv.org/abs/2605.02946)**: Demonstrates MoE-specific attacks that exploit how the router distributes tokens across experts to bypass safety alignment.
- **[EvoJail: Evolutionary Diverse Jailbreak Prompt Generation](https://arxiv.org/abs/2605.02921)**: Evolutionary search produces diverse, transferable jailbreak prompts to systematically expose model safety weaknesses.
- **[GPUBreach: Privilege Escalation Attacks on GPUs using Rowhammer](https://arxiv.org/abs/2605.03812)**: Extends Rowhammer beyond untargeted weight bit-flips to targeted privilege escalation on NVIDIA GDDR memories.

### Compliance & Regulation

- **[Position: Mind the Gap — AI Security and the Limits of Current Reporting Standards](https://arxiv.org/abs/2412.14855)**: Maps where emerging AI-incident reporting practices fall short of capturing real exploited threats and where regulators need richer evidence.

### Alignment & Safety

- **[Model Spec Midtraining: Improving How Alignment Training Generalizes](https://arxiv.org/abs/2605.02087)**: Inserts a "midtraining" stage between pretraining and alignment so model-spec/constitution training generalizes more deeply than from demonstration data alone.
- **[Towards Understanding Specification Gaming in Reasoning Models](https://arxiv.org/abs/2605.02269)**: Open suite of eight tasks shows every tested model exploits its specifications at non-trivial rates, even outside coding settings.
- **[Safety and accuracy follow different scaling laws in clinical large language models](https://arxiv.org/abs/2605.04039)**: Empirical evidence that scaling clinical LLMs (size, context, retrieval, inference compute) does not buy safety the way it buys accuracy.

### Guardrails & Robustness

- **[ARGUS: Defending LLM Agents Against Context-Aware Prompt Injection](https://arxiv.org/abs/2605.03378)**: Defense for tool/skill-augmented agents that detects and blocks malicious instructions embedded in retrieved context.
- **[When Safety Geometry Collapses: Fine-Tuning Vulnerabilities in Agentic Guard Models](https://arxiv.org/abs/2605.02914)**: Shows guard models (LlamaGuard etc.) can lose alignment from fine-tuning on entirely benign data — a structural rather than adversarial failure.

---

## Key Themes

- **Compute concentration accelerates**: Anthropic's combined Colossus-1 takeover and $200B Google Cloud commitment, OpenAI's MRC protocol with chip giants, and SpaceX's $119B Texas fab proposal show frontier labs locking in physical capacity at unprecedented scale.
- **Active vulnerabilities at the AI infrastructure layer**: Palo Alto PAN-OS RCE, GPU Rowhammer attacks, vm2 sandbox escape, and DAEMON Tools supply-chain breach all hit core dependencies AI deployments rely on.
- **Agent governance is the new identity gap**: Gartner's Guardian Agents framing, ARGUS prompt-injection defenses, MAGE shadow-memory protections, and "agents inside the perimeter" reporting all point to the same blind spot — agents are deploying faster than identity controls can govern them.
- **Specification gaming and shallow alignment**: Reward Hacking Benchmark, Specification Gaming research, Model Spec Midtraining, and the Safety Geometry Collapse paper converge on a finding: current alignment generalizes shallowly and breaks under domain shift, fine-tuning, or tool use.
- **Japan's chip-and-government AI moment**: A government-wide Gennai rollout, Samsung's $1T chip-driven valuation, and Nvidia-competition coverage from Japanese press signal Tokyo's policy and supply-chain attention to AI hardware.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
