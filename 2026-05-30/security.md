# Security Digest — 2026-05-30

AI is now visibly threaded through both sides of the security story: attackers are weaponizing ChatGPT and Gemini for real campaigns while researchers race to harden alignment, jailbreak detection, and the long tail of agent-introduced vulnerabilities. Meanwhile, classic infrastructure problems — a 17-million-device botnet, a 4.9-million-account telecom breach, and a fresh 23andMe lawsuit — keep showing up alongside the new AI-shaped threats.

---

## AI Security Research

### [Aligned but Fragile: Enhancing LLM Safety Robustness via Zeroth-Order Optimization](https://arxiv.org/abs/2605.29396)
*ArXiv cs.AI*
Safety alignment is shown to collapse under lightweight post-alignment perturbations like parameter noise, activation noise, or quantization. The authors propose a zeroth-order optimization approach that hardens models against these manipulations without sacrificing general utility.

### [Beyond Attack Success Rate: Temporal Logit Observability for LLM Safety Failures](https://arxiv.org/abs/2605.29629)
*ArXiv cs.AI*
A training-free diagnostic called TLO watches the compliance-refusal trajectory inside logits during generation, distinguishing jailbreaks that produce equally harmful outputs by very different paths. The technique reveals what a binary ASR metric hides and gives defenders a richer signal for triage.

### [Measuring Real-World Prompt Injection Attacks in LLM-based Resume Screening](https://arxiv.org/abs/2605.28999)
*ArXiv cs.AI*
The first large-scale empirical study of prompt injection in a deployed application, examining roughly a million real LLM-screened resumes. The work moves prompt injection out of academic demos and quantifies how often the attack actually appears in the wild.

### [Relevance as a Vulnerability: How Web Retrieval Degrades Safety Alignment in LLM Agents](https://arxiv.org/abs/2605.29224)
*ArXiv cs.AI*
The AgentREVEAL framework shows that adding web retrieval to LLM agents reliably weakens refusal behavior, with the most relevant retrieved content being the most dangerous. The finding implies that grounding pipelines may need their own dedicated safety layer rather than relying on the base model's alignment.

### [Audio Jailbreaks in Large Audio-Language Models: Taxonomy, Attack-Defense Analysis, and Cost-Aware Evaluation](https://arxiv.org/abs/2605.30031)
*ArXiv cs.AI*
A unified taxonomy of jailbreaks against speech-input models, covering attacks delivered via semantics, acoustic style, signal artifacts, and internal representations. The paper proposes a cost-aware evaluation protocol so that practical defenses can be compared fairly.

### [Minimal Prompt Perturbations Lead to Code Vulnerabilities](https://arxiv.org/abs/2605.29737)
*ArXiv cs.CR*
Token-level mutations to coding-assistant prompts not only break functional correctness but also introduce exploitable security flaws in the generated code. The authors find hidden-state signals that predict when a perturbation will cause a vulnerable output, suggesting a path for guardrails.

### [Enhancing Membership Inference Attacks on Diffusion Models from a Frequency-Domain Perspective](https://arxiv.org/abs/2505.20955)
*ArXiv cs.LG*
A new frequency-domain attack improves the ability to determine whether a specific image was in a diffusion model's training set, sharpening the privacy threat to copyrighted data. The unified analysis also formalizes prior MIAs into a common paradigm for easier comparison.

### [LoRA-Key: User-Centric LoRA Watermarking for Text-to-Image Diffusion Models](https://arxiv.org/abs/2605.29569)
*ArXiv cs.CR*
A watermarking scheme aimed at the LoRA-module ecosystem, where ownership and copyright now attach to small adapters rather than the base diffusion model. The approach is designed to survive redistribution and reuse of the LoRA itself.

---

## Vulnerabilities & Exploits

### [ChatGPhish Vulnerability Turns ChatGPT Web Summaries Into a Phishing Surface](https://thehackernews.com/2026/05/chatgphish-vulnerability-turns-chatgpt.html)
*The Hacker News*
Permiso Security disclosed a vulnerability in which ChatGPT's Markdown link and image renderer can be coerced via prompt injection into surfacing attacker-controlled phishing links inside trusted-looking responses. The technique converts the assistant itself into a delivery channel.

### [Attackers Use LLM Agent for Post-Exploitation After Marimo CVE-2026-39987 Exploit](https://thehackernews.com/2026/05/attackers-use-llm-agent-for-post.html)
*The Hacker News*
A threat actor exploited internet-reachable Marimo notebooks via CVE-2026-39987 and then handed off post-compromise actions to an LLM agent, which extracted cloud credentials from the compromised host. The incident is an early concrete example of LLM-driven hands-on-keyboard operations.

### [ChatGPT share links abused to host fake outage pages to deliver malware](https://www.bleepingcomputer.com/news/security/chatgpt-share-links-abused-to-host-fake-outage-pages-to-deliver-malware/)
*BleepingComputer*
Attackers are abusing ChatGPT's content-sharing feature to publish pages that mimic OpenAI outage notices and push users toward a fake ChatGPT desktop installer carrying malware. The lure leverages the legitimacy of the chatgpt.com domain.

### [New Russian-Linked GREYVIBE Targets Ukraine with AI-Powered Cyberattacks](https://thehackernews.com/2026/05/new-russian-linked-greyvibe-targets.html)
*The Hacker News*
WithSecure attributes a campaign of AI-generated lures and custom malware against Ukrainian entities, active since at least August 2025, to a Russian-speaking cluster dubbed GREYVIBE. Companion reporting at [BleepingComputer](https://www.bleepingcomputer.com/news/security/greyvibe-hackers-use-chatgpt-gemini-to-power-cyberattacks/) details the use of ChatGPT and Gemini for content generation and tooling.

### [Dutch govt disrupts malware botnet with 17 million infected devices](https://www.bleepingcomputer.com/news/security/dutch-govt-disrupts-malware-botnet-with-17-million-infected-devices/)
*BleepingComputer*
Dutch authorities seized more than 200 servers at a local provider and took down a botnet of about 17 million devices reportedly tied to a Russia-based residential proxy network. The takedown is one of the largest residential-proxy disruptions on record.

### [Charter Communications data breach affects 4.9 million accounts](https://www.bleepingcomputer.com/news/security/charter-communications-data-breach-affects-49-million-accounts/)
*BleepingComputer*
ShinyHunters stole personal data on 4.9 million Charter Communications accounts during an April intrusion, according to records that have surfaced on Have I Been Pwned. The disclosure adds another major US telecom to the extortion gang's victim list.

### [California AG sues 23andMe over 2023 breach exposing health data](https://www.bleepingcomputer.com/news/security/california-ag-sues-23andme-over-2023-breach-exposing-health-data/)
*BleepingComputer*
California Attorney General Rob Bonta filed suit against the entity now operating as Chrome Holding Co. for failing to safeguard the genetic and personal data exposed in the 2023 incident. The case is a notable example of post-breach state-level enforcement on consumer health data.

### [Malicious Sicoob NuGet Steals Banking Credentials as npm Packages Target Cloud Secrets](https://thehackernews.com/2026/05/malicious-sicoob-nuget-steals-banking.html)
*The Hacker News*
Socket found versions 2.0.0–2.0.4 of a NuGet package impersonating a Sicoob SDK exfiltrating client IDs and PFX certificates from one of Brazil's largest cooperative banking systems, while related npm packages target cloud secrets. The campaign continues the pattern of high-value supply-chain attacks against package registries.

### [Kimsuky Deploys HTTPSpy, Expands Arsenal with HelloDoor and VS Code Tunnels](https://thehackernews.com/2026/05/kimsuky-deploys-httpspy-expands-arsenal.html)
*The Hacker News*
North Korea's Kimsuky (Velvet Chollima) is running March–April 2026 attacks against South Korean military and corporate targets using spoofed security-software installers and a fake Webex page, deploying new tools HTTPSpy and HelloDoor. The group is also abusing VS Code remote tunnels to maintain access.

---

## Policy & Compliance

### [Few Japan firms take steps toward economic security, government paper finds](https://www.japantimes.co.jp/business/2026/05/29/companies/firms-economic-security-paper/)
*The Japan Times*
A government white paper finds only about 30% of Japanese companies have taken substantive economic-security steps such as diversifying procurement and strengthening cybersecurity. The result suggests slow corporate uptake of Tokyo's economic-security agenda.

### [Asia's Cyber Insurance Market Shows Signs of Life](https://www.darkreading.com/cloud-security/asias-cyber-insurance-market-shows-signs-of-life)
*Dark Reading*
After years of slow growth, the Asia cyber insurance market is seeing rising premiums and broader adoption as regional regulators tighten breach-disclosure requirements. The piece frames insurance as an emerging lever for compliance discipline in the region.

### [Chilling Effects](https://www.schneier.com/blog/archives/2026/05/chilling-effects.html)
*Schneier on Security*
Bruce Schneier examines how the second Trump administration's actions against campus speech — lawsuits, arrests, deportations, expulsions — are producing measurable self-censorship even where formal policy has not changed. He frames the dynamic as a cautionary case study in how legal pressure reshapes behavior far beyond what any specific rule requires.
