# Security Digest — 2026-05-27

Today's landscape is dominated by AI's double-edged role: a wave of research exposes jailbreaks, prompt injection, and privacy leaks in LLM agents, while attackers are weaponizing AI to accelerate exploitation — prompting regulators to demand sub-day patching. On the operational side, fresh zero-days, supply-chain worms, and large breach disclosures keep defenders busy.

---

## AI Security Research

### [Reasoning as an Attack Surface: Adaptive Evolutionary CoT Jailbreaks for LLMs](https://arxiv.org/abs/2605.24497)
*ArXiv cs.AI* — The explicit chain-of-thought mechanism in large reasoning models opens a new attack surface; the authors replace static jailbreak templates with an adaptive evolutionary approach that evolves diverse CoT prompts to reliably elicit harmful outputs.

### [Chain-of-Thought Hijacking](https://arxiv.org/abs/2510.26418)
*ArXiv cs.AI* — Contrary to the assumption that longer reasoning makes models safer, the authors show over-extended reasoning can be exploited as a simple black-box jailbreak that systematically erodes refusal behavior in large reasoning models.

### [StructBreak: Structural Cognitive Overload-Induced Safety Failures in MLLMs](https://arxiv.org/abs/2605.25534)
*ArXiv cs.AI* — Identifies "Structural Cognitive Overload," a brittleness arising from the tension between deep reasoning and safety alignment, and uses it to break multimodal LLMs without relying on typographic or pixel-level perturbations.

### [SoK: A Comprehensive Security Analysis of Jailbreak Resilience in GPT and DeepSeek Models](https://arxiv.org/abs/2506.18543)
*ArXiv cs.AI* — A systematization of knowledge comparing jailbreak robustness across proprietary GPT models and the emerging open-source DeepSeek systems, whose resilience has been under-examined despite rapid adoption.

### [Sparse Tokens Suffice: Jailbreaking Audio Language Models via Token-Aware Gradient Optimization](https://arxiv.org/abs/2605.04700)
*ArXiv cs.AI* — Shows that audio LLM jailbreaks don't require dense waveform perturbation: because gradient energy concentrates on a small subset of audio tokens, sparse token-aware optimization is enough to elicit unsafe generations.

### [IterInject: Indirect Prompt Injection Against LLM Agents via Feedback-Guided Iterative Optimization](https://arxiv.org/abs/2605.24659)
*ArXiv cs.LG* — Proposes an adaptive indirect prompt-injection attack that uses structured feedback to iteratively refine payloads embedded in retrieved data, overcoming the limits of static injection against defended tool-using agents.

### [Deep-Research Agents Can Be Poisoned via User-Generated Content](https://arxiv.org/abs/2605.24245)
*ArXiv cs.CR* — Demonstrates that multi-agent "deep research" pipelines repeatedly retrieve the same user-generated pages, letting attackers poison those pages to corrupt the synthesized reports and citations these systems produce.

### [Poisoning the Watchtower: Prompt Injection Attacks Against LLM-Augmented Security Operations Through Adversarial Log Content](https://arxiv.org/abs/2605.24421)
*ArXiv cs.LG* — Highlights a structural flaw in LLM-assisted SOCs: because log fields like user agents, URLs, and usernames are attacker-controlled, adversaries can smuggle instructions into telemetry to manipulate triage, summaries, and remediation advice.

### [Reframing LLM Agent Security as an Agent-Human Interaction Problem](https://arxiv.org/abs/2605.24309)
*ArXiv cs.CR* — A systematic analysis of 59 papers, 21 production agent systems, and 26 security plugins argues that the dominant human-centric controls (policy specs, runtime approval, scope configuration) make agent security fundamentally an interaction problem, not a purely algorithmic one.

### [Five Queries Are Enough: Query-Efficient and Surrogate-Free Membership Inference Attacks on RAG via Entailment](https://arxiv.org/abs/2605.24312)
*ArXiv cs.CR* — Introduces an entailment-based membership inference attack that needs only a handful of queries and no surrogate model to detect whether a sensitive document sits in a RAG system's retrieval corpus.

### [Measuring the Depth of LLM Unlearning via Activation Patching](https://arxiv.org/abs/2605.24614)
*ArXiv cs.AI* — Argues that output-level metrics overstate unlearning success and uses activation patching to audit whether "erased" knowledge remains recoverable from a model's internal representations.

### [Ellipsoid Control: A White-list Jailbreak Defense via Benign Latent Modeling](https://arxiv.org/abs/2605.24552)
*ArXiv cs.CR* — Flips representation-engineering defenses from black-list to white-list supervision, modeling the distribution of benign activations so robustness no longer depends on ever-incomplete catalogs of known jailbreak data.

### [Certified Robustness from Approximate Gaussian Mixture Structures in Pretrained Latent Spaces](https://arxiv.org/abs/2605.25352)
*ArXiv cs.AI* — Tightens overly conservative certified-robustness bounds against adversarial perturbations by exploiting approximate Gaussian-mixture structure in pretrained latent spaces.

### [Grounding-Driven Attack: Improving Encoder-based Adversarial Transferability against Large Vision-Language Models](https://arxiv.org/abs/2602.09431)
*ArXiv cs.CR* — Improves the transferability of efficient encoder-only adversarial attacks against vision-language models even when the surrogate vision encoder differs from the victim's.

### [Identifying People Using Wi-Fi Routers](https://www.schneier.com/blog/archives/2026/05/identifying-people-using-wi-fi-routers.html)
*Schneier on Security* — A look at "WiFi sensing," in which ambient WiFi signals reflected and scattered by people and objects can be analyzed to infer the physical environment — raising the prospect of identifying individuals from radio signals alone.

## Vulnerabilities & Exploits

### [KnowledgeDeliver LMS Flaw Exploited to Deploy Godzilla and Cobalt Strike](https://thehackernews.com/2026/05/knowledgedeliver-lms-flaw-exploited-to.html)
*The Hacker News* — CVE-2026-5426 (CVSS 7.5), stemming from hard-coded ASP.NET machine keys in the Japan-popular KnowledgeDeliver LMS, was exploited as a zero-day to deploy the Godzilla web shell and ultimately Cobalt Strike Beacon.

### [Microsoft Patches SharePoint RCE Flaw CVE-2026-45659 Across Server Versions](https://thehackernews.com/2026/05/microsoft-patches-sharepoint-rce-flaw.html)
*The Hacker News* — Microsoft fixed a SharePoint deserialization-of-untrusted-data flaw (CVE-2026-45659, CVSS 8.8) that allows remote code execution without specialized conditions; Dark Reading notes SharePoint compromise often hands attackers the keys to the kingdom.

### [Feeding Frenzy: 'Megalodon' Malware Infects Thousands of GitHub Repos](https://www.darkreading.com/application-security/megalodon-malware-infects-thousands-github-repos)
*Dark Reading* — In just six hours, the Megalodon campaign pushed malicious commits to more than 5,500 GitHub repositories, harvesting credentials and developer secrets in a fast-moving software-supply-chain attack.

### [The Hackers Behind Shai-Hulud: Lucky or Skilled?](https://www.darkreading.com/application-security/shai-hulud-hackers-teampcp-lucky-skilled)
*Dark Reading* — A profile of TeamPCP, the group behind the Shai-Hulud worm that has done significant damage to the open-source ecosystem, weighing how much of the impact stems from skill versus opportunism.

### [Charter confirms data breach after ShinyHunters extortion threat](https://www.bleepingcomputer.com/news/security/charter-confirms-data-breach-after-shinyhunters-extortion-threat/)
*BleepingComputer* — Telecom giant Charter Communications confirmed a data breach after the ShinyHunters extortion group threatened to leak stolen data unless a ransom is paid.

### [7-Eleven data breach exposes personal information of 185,000 people](https://www.bleepingcomputer.com/news/security/7-eleven-data-breach-exposes-personal-information-of-185-000-people/)
*BleepingComputer* — The same ShinyHunters gang stole the personal data of over 183,000 people after breaching convenience-store chain 7-Eleven in April, per Have I Been Pwned.

### [MuddyWater Uses DLL Side-Loading in Espionage Campaign Targeting 9 Countries](https://thehackernews.com/2026/05/muddywater-uses-dll-side-loading-in.html)
*The Hacker News* — Iranian group MuddyWater hit at least nine organizations across nine countries and four continents in Q1 2026, using DLL side-loading against manufacturing, education, public-sector, financial, and professional-services targets.

### [Iranian Hackers Deploy MiniFast and MiniJunk V2 via Phishing and SEO Poisoning](https://thehackernews.com/2026/05/iranian-hackers-deploy-minifast-and.html)
*The Hacker News* — State-sponsored actor Nimbus Manticore (UNC1549) launched a fresh campaign impersonating aviation and software organizations across the U.S., Europe, and the Middle East, delivering the MiniFast and MiniJunk V2 implants.

### [CISA orders feds to patch actively exploited Drupal vulnerability](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-actively-exploited-drupal-vulnerability/)
*BleepingComputer* — CISA gave U.S. agencies a hard deadline to remediate an actively exploited SQL injection vulnerability in the Drupal CMS.

### [MFA Prompt Bombing: Why Your Second Factor Isn't Saving You](https://thehackernews.com/2026/05/mfa-prompt-bombing-why-your-second.html)
*The Hacker News* — Examines how attackers bypass multi-factor authentication not by stealing the second factor but by fatiguing users with repeated push prompts until they approve one.

## Policy & Compliance

### [CERT-In Recommends 12-Hour Patching for Internet-Facing Flaws Amid AI-Assisted Attacks](https://thehackernews.com/2026/05/cert-in-mandates-12-hour-patching-for.html)
*The Hacker News* — India's CERT-In issued guidelines urging organizations to patch critical internet-exposed vulnerabilities within 12 hours where feasible, citing threat actors' use of AI and LLMs to automate vulnerability discovery and exploitation.

### [How Varonis Atlas integrates Claude Compliance API for AI governance](https://www.bleepingcomputer.com/news/security/how-varonis-atlas-integrates-claude-compliance-api-for-ai-governance/)
*BleepingComputer* — Varonis details how its Atlas platform uses Claude Compliance API data to give enterprises visibility into how AI tools interact with sensitive data, supporting usage monitoring, risk investigation, and compliance.
