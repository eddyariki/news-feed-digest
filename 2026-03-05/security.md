# Security Digest — 2026-03-05

AI-assisted attacks are accelerating on two fronts today: nation-state actors are using generative AI to mass-produce malware, while AI search surfaces are being weaponized to distribute infostealers via poisoned GitHub repositories.

---

## AI Security Research

**[Secure Semantic Communications via AI Defenses: Fundamentals, Solutions, and Future Directions](https://arxiv.org/abs/2602.22134)**
*ArXiv cs.CR — Lan Zhang et al.*
This survey examines how AI-native semantic communication systems introduce a new attack surface: adversarial perturbations, poisoned training data, and desynchronized priors can cause semantic failures even when lower-layer transmission and cryptography remain intact. The authors outline defense frameworks covering robustness, privacy, and authentication for next-generation semantic comm architectures.

**[Annotation-Efficient Universal Honesty Alignment](https://arxiv.org/abs/2510.17509)**
*ArXiv cs.CL — Shiyu Ni et al.*
Addresses a core safety concern for deployed LLMs: models that cannot recognize their own knowledge boundaries produce confidently wrong outputs. The paper proposes an annotation-efficient training approach to improve calibrated confidence expression, reducing the risk of high-stakes misuse from overconfident model responses.

---

## Vulnerabilities & Exploits

**[Bing AI promoted fake OpenClaw GitHub repo pushing info-stealing malware](https://www.bleepingcomputer.com/news/security/bing-ai-promoted-fake-openclaw-github-repo-pushing-info-stealing-malware/)**
*BleepingComputer — Bill Toulas*
Attackers planted fake OpenClaw installers on GitHub and exploited Microsoft Bing's AI-enhanced search to surface the malicious repositories to users. Victims who followed the instructions deployed information stealers and proxy malware, highlighting how AI search recommendations can be gamed as a distribution vector.

**[Nation-State Actor Embraces AI Malware Assembly Line](https://www.darkreading.com/cyberattacks-data-breaches/nation-state-actor-ai-malware-assembly-line)**
*Dark Reading — Jai Vijayan*
Pakistan's APT36 has adopted "vibe-coding" techniques to generate malware at scale, producing individually mediocre but volumetrically overwhelming samples. The shift signals a broader trend where nation-state groups trade per-sample sophistication for sheer throughput, threatening to saturate traditional signature-based defenses.
