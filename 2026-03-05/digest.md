# AI News Digest — March 5, 2026

## Highlights

- **[Bing AI Promoted Fake OpenClaw Repo Pushing Malware](https://www.bleepingcomputer.com/news/security/bing-ai-promoted-fake-openclaw-github-repo-pushing-info-stealing-malware/)**: Microsoft Bing's AI-enhanced search surfaced a fake GitHub repository whose installers deployed info-stealing and proxy malware on unsuspecting users' machines.
- **[Nation-State Actor Embraces AI Malware Assembly Line](https://www.darkreading.com/cyberattacks-data-breaches/nation-state-actor-ai-malware-assembly-line)**: Pakistan's APT36 threat group is using vibe-coding to mass-produce malware at a scale that could overwhelm traditional defenses.
- **[Annotation-Efficient Universal Honesty Alignment](https://arxiv.org/abs/2510.17509)**: New training-based method enables LLMs to recognize knowledge boundaries and express calibrated confidence with far fewer correctness annotations.
- **[FlowCorrect: Interactive Correction of Generative Flow Policies for Robotics](https://arxiv.org/abs/2602.22056)**: A modular approach lets humans correct near-miss robot manipulation failures at deployment time with sparse relative corrections — no retraining required.

---

## News

### AI Security

- **[Bing AI Promoted Fake OpenClaw GitHub Repo Pushing Info-Stealing Malware](https://www.bleepingcomputer.com/news/security/bing-ai-promoted-fake-openclaw-github-repo-pushing-info-stealing-malware/)** (BleepingComputer): Microsoft Bing's AI search feature directed users to fake OpenClaw installers that ran commands deploying information stealers and proxy malware — a stark example of AI-assisted search becoming an attack vector.

- **[Nation-State Actor Embraces AI Malware Assembly Line](https://www.darkreading.com/cyberattacks-data-breaches/nation-state-actor-ai-malware-assembly-line)** (Dark Reading): Pakistan's APT36 has adopted "vibe-coding" to rapidly generate mediocre-but-voluminous malware, trading quality for sheer scale to overwhelm security defenses.

### Japan

- **[Ibaraki Pref.'s 1st Foreign Bus Driver Hired in Tsukuba](https://japannews.yomiuri.co.jp/society/general-news/20260306-314648/)** (The Japan News): Amid acute labor shortages in Japan's transportation sector, Ibaraki Prefecture welcomed its first foreign bus driver — hired under the specified skilled workers visa — who now drives a school bus in Tsukuba.

- **[CHROが"AI責任者"になる時代 — 新・組織論](https://www.itmedia.co.jp/business/articles/2603/06/news013.html)** (ITmedia AI+): As generative AI becomes embedded in workforces, CHROs are emerging as the natural owners of AI strategy. The article argues that true competitive advantage requires restructuring organizations around AI as labor, not merely adopting AI as a tool.

- **[イスラエルのレーザー兵器「IRON BEAM」によるミサイル迎撃](https://gigazine.net/news/20260306-israel-laser-weapon/)** (Gigazine): Footage has emerged online appearing to show Israel's IRON BEAM directed-energy weapon intercepting an incoming missile immediately after launch — potentially the first documented operational use of the system.

---

## Research Papers

### Safety

- **[Annotation-Efficient Universal Honesty Alignment](https://arxiv.org/abs/2510.17509)**: Proposes a training-based calibration framework that enables LLMs to recognize knowledge boundaries and express calibrated uncertainty without requiring exhaustive correctness annotations — a step toward more trustworthy AI deployment.

- **[Secure Semantic Communications via AI Defenses](https://arxiv.org/abs/2602.22134)**: Surveys vulnerabilities unique to AI-native semantic communication systems — adversarial perturbations, corrupted training data, desynchronized priors — and proposes defense strategies beyond conventional cryptographic protections.

### Applied AI

- **[FlowCorrect: Efficient Interactive Correction of Generative Flow Policies for Robotic Manipulation](https://arxiv.org/abs/2602.22056)**: Introduces a modular interactive imitation learning framework enabling deployment-time adaptation of flow-matching manipulation policies from sparse human corrections, without retraining — addressing near-miss failure modes in robotic manipulation.

- **[Momentum Memory for Knowledge Distillation in Computational Pathology](https://arxiv.org/abs/2602.21395)**: Tackles the challenge of scarce paired histology-genomics data in cancer diagnosis by using momentum-based knowledge distillation to transfer genomic supervision into histopathology-only models, improving clinical translation.

- **[Automatic Map Density Selection for Locally-Performant Visual Place Recognition](https://arxiv.org/abs/2602.21473)**: Addresses long-term deployment of visual place recognition by automatically tuning reference map density to meet user-specified local performance requirements, rather than optimizing only for global averages.

### Benchmarks

- **[Meenz bleibt Meenz, but LLMs Do Not Speak Its Dialect](https://arxiv.org/abs/2602.16852)**: Evaluates current LLMs on Meenzerisch, the endangered dialect of Mainz, Germany, finding significant gaps — and motivating NLP research as a tool for dialect preservation and revival.

---

## Key Themes

- **AI as an attack vector**: Both the Bing/OpenClaw incident and APT36's AI-assisted malware production show that AI is now actively weaponized in the threat landscape — from search poisoning to code generation at scale.
- **AI in organizational design**: Japanese industry is grappling with how to restructure organizations when AI is treated as a productive workforce, elevating HR leadership into technology strategy roles.
- **Robustness and alignment in deployed AI**: Papers on honesty alignment, robotic correction, and semantic communication security all converge on a common challenge: making AI systems that behave reliably and safely outside of training conditions.
- **AI for preservation and healthcare**: LLM dialect research and computational pathology distillation highlight growing use of AI for social and medical good, in domains where labeled data is scarce.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
