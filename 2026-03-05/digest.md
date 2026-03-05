# AI & World News Digest — March 5, 2026

## Highlights

- **[U.S. Sinks Iranian Warship, NATO Intercepts Missile Targeting Turkey](https://www.japantimes.co.jp/news/2026/03/05/world/us-iran-warship-nato-missile-turkey/)**: A major military escalation in the U.S.-Iran conflict saw a U.S. strike sink an Iranian warship while NATO forces intercepted an Iranian missile headed for Turkey, as a power succession struggle begins inside Iran.
- **[Seven Tech Giants Sign Trump's Data Center Rate Payer Protection Pledge](https://www.theverge.com/news/889578/data-center-power-pledge-white-house-google-meta-microsoft)**: Google, Meta, Microsoft, Oracle, OpenAI, Amazon, and xAI committed to a White House pledge aimed at preventing AI data center buildout from driving up consumer electricity costs.
- **[Check Point Exposes Critical Claude Code Vulnerabilities](https://www.itmedia.co.jp/enterprise/articles/2603/05/news035.html)**: Researchers found that malicious project configuration files can trigger remote code execution and API key exfiltration in Claude Code — simply opening an untrusted project is enough to initiate an attack.
- **[Cloudflare: 2.3 Trillion Threat Observations Reveal Attacks Now Come From Within](https://www.itmedia.co.jp/enterprise/articles/2603/05/news037.html)**: Cloudflare's global threat report details the evolution of cyberattack methods and attacker use of AI, warning that conventional defenses are reaching their limits.

---

## News

### AI Security

- **[Claude Codeの重大な脆弱性を分析 — 開発者への3つの影響とは？](https://www.itmedia.co.jp/enterprise/articles/2603/05/news035.html)** (ITmedia AI+): Check Point reported a detailed analysis of critical vulnerabilities in Claude Code. Malicious configuration files can enable remote code execution and API key leakage; the firm warns that simply opening an unvetted project initiates the attack surface.

- **[攻撃はもう外から来ない？ 2300億件の脅威観測から見えた事実](https://www.itmedia.co.jp/enterprise/articles/2603/05/news037.html)** (ITmedia AI+): Cloudflare released its global threat report, providing detailed analysis of evolving cyberattack techniques and real-world attacker use of AI, recommending a strategic shift as traditional defenses approach their limits.

### USA

- **[Seven Tech Giants Signed Trump's Pledge to Keep Electricity Costs From Spiking Around Data Centers](https://www.theverge.com/news/889578/data-center-power-pledge-white-house-google-meta-microsoft)** (The Verge): Leaders from Google, Meta, Microsoft, Oracle, OpenAI, Amazon, and xAI met with President Trump to sign a "rate payer protection pledge," addressing bipartisan concerns about AI infrastructure buildout driving up household energy bills.

- **[U.S. Senate Backs Trump on Iran Strikes, Blocks Bid to Limit His War Powers](https://www.japantimes.co.jp/news/2026/03/05/world/politics/us-senate-trump-iran-war-powers/)** (The Japan Times): The Senate voted 53–47 largely along party lines not to advance a war powers resolution that would have constrained the president's ability to conduct strikes against Iran.

- **[U.S. Sinks Iranian Warship, NATO Downs Iranian Missile Heading for Turkey](https://www.japantimes.co.jp/news/2026/03/05/world/us-iran-warship-nato-missile-turkey/)** (The Japan Times): U.S. forces sank an Iranian warship as NATO intercepted an Iranian missile aimed at Turkey; the escalation coincides with a leadership succession struggle following the death of Iran's supreme leader.

- **[Iran Conflict Could Divert U.S. Weapons From Ukraine](https://www.japantimes.co.jp/news/2026/03/05/world/politics/iran-us-weapons-ukraine/)** (The Japan Times): Growing demands on PAC-3 Patriot interceptors in the Iran theater raise concerns about supply constraints for Ukraine, which depends on the same systems to defend critical infrastructure.

### Japan

- **[生成AI、7割が生産性向上を実感 なのに「毎日使う」はわずか6％](https://www.itmedia.co.jp/enterprise/articles/2603/05/news031.html)** (ITmedia AI+): A PwC survey highlights a stark gap in Japanese enterprises: 70% of workers report productivity gains from generative AI, yet only 6% use it daily, revealing organizational culture barriers that differ markedly from global peers.

- **[回転するジンバルカメラ搭載スマホ「HONOR Robot Phone」は2026年後半に登場予定](https://gigazine.net/news/20260305-honor-robot-phone-launch-2026/)** (Gigazine): Announced at MWC 2026 in Spain, HONOR's Robot Phone features a rotating gimbal camera and can perform dance moves synchronized to music; the device is slated for release in the second half of 2026.

---

## Research Papers

### Benchmarks

- **[HSSBench: Benchmarking Humanities and Social Sciences Ability for Multimodal Large Language Models](https://arxiv.org/abs/2506.03922)**: Proposes a new benchmark filling a gap in MLLM evaluation — existing benchmarks over-index on STEM and step-by-step reasoning, while this work targets horizontal, interdisciplinary thinking characteristic of the humanities and social sciences.

### Applied AI

- **[Training-Free Multi-Concept Image Editing](https://arxiv.org/abs/2602.20839)**: Introduces Concept-guided diffusion editing that achieves zero-shot multi-concept edits without training, preserving fine-grained identity details (facial structure, material texture, geometry) that text-based optimization methods struggle to capture.

- **[From Pairs to Sequences: Track-Aware Policy Gradients for Keypoint Detection](https://arxiv.org/abs/2602.20630)**: Reframes keypoint detection as a sequential decision-making problem, using policy gradients to optimize long-term trackability across image sequences — improving on methods trained only on pairs, with benefits for Structure-from-Motion and SLAM pipelines.

### AI

- **[DRESS: A Continuous Framework for Structural Graph Refinement](https://arxiv.org/abs/2602.20833)**: Addresses the computational bottleneck of scaling beyond 1-WL graph isomorphism testing; the DRESS equation offers a parameter-free, continuous approach to structural graph refinement that avoids the O(n³–n⁴) tensor operations required by 3-WL and higher.

---

## Key Themes

- **AI infrastructure & energy policy**: The White House data center electricity pledge marks a notable moment of Big Tech-government coordination on AI's energy footprint.
- **AI security risks for developers**: Claude Code vulnerabilities and Cloudflare's threat report both underscore how AI tooling is becoming an active attack surface, not just a defensive asset.
- **U.S.-Iran escalation**: Multiple overlapping developments — warship strikes, a Senate war powers vote, NATO involvement, and supply chain concerns for Ukraine — signal a rapidly evolving geopolitical situation.
- **Japan's generative AI adoption gap**: Despite high reported productivity gains, Japan's enterprise AI daily usage rate lags far behind global averages, pointing to cultural and organizational barriers.
- **Multimodal evaluation gaps**: HSSBench highlights that current MLLM benchmarks systematically underweight interdisciplinary, humanistic reasoning.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
