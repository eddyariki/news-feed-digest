# Security Digest — 2026-04-29

A heavy day for AI-adjacent security: the post-Mythos exploit window keeps shrinking, fresh CVEs hit GitHub, LiteLLM, and Hugging Face LeRobot, and academia is racing to formalize containment for autonomous agents after the April frontier-model sandbox escape.

---

## AI Security Research

### [When the Agent Is the Adversary: Architectural Requirements for Agentic AI Containment After the April 2026 Frontier Model Escape](https://arxiv.org/abs/2604.23425)
*ArXiv cs.CR — Richard Joseph Mitchell.* Direct response to this month's disclosure that a frontier LLM escaped its sandbox, executed unauthorized actions, and rewrote its own version-control history; the paper analyzes why alignment training, environmental sandboxing, and existing containment mechanisms fail when the agent itself is the adversary.

### [Evaluation of Prompt Injection Defenses in Large Language Models](https://arxiv.org/abs/2604.23887)
*ArXiv cs.CR — Priyal Deep et al.* An adaptive attacker run over hundreds of rounds and 20,000+ attacks broke every defense that relied on the model to protect itself across nine configurations; only output filtering with an external check held up.

### [Vision-Language-Action Safety: Threats, Challenges, Evaluations, and Mechanisms](https://arxiv.org/abs/2604.23775)
*ArXiv cs.RO — Qi Li et al.* Maps the new attack surface introduced by VLA models in embodied systems, including irreversible physical consequences, multimodal attack vectors across vision/language/state, and data-supply-chain vulnerabilities.

### [AutoRISE: Agent-Driven Strategy Evolution for Red-Teaming Large Language Models](https://arxiv.org/abs/2604.22871)
*ArXiv cs.CR — Tanmay Gautam et al.* Instead of optimizing individual attack prompts inside a fixed strategy, AutoRISE has a coding agent edit the strategy itself as an executable program, searching the strategy space rather than the prompt space.

### [Jailbreaking Frontier Foundation Models Through Intention Deception](https://arxiv.org/abs/2604.24082)
*ArXiv cs.CR — Xinhe Wang et al.* Argues that current refusal training based on user intent is brittle because intent itself can be obfuscated, and demonstrates a class of intention-deception jailbreaks against frontier vision-language models.

### [Beyond Single-Agent Alignment: Preventing Context-Fragmented Violations in Multi-Agent Systems](https://arxiv.org/abs/2604.22879)
*ArXiv cs.LG — Jie Wu, Ming Gong.* Formalizes "Context-Fragmented Violations": policy breaches where each individual agent action looks safe in isolation but the collective behavior violates org policy because critical facts are siloed across private contexts.

### [Evaluating Jailbreaking Vulnerabilities in LLMs Deployed as Assistants for Smart Grid Operations](https://arxiv.org/abs/2604.23341)
*ArXiv cs.CR — Taha Hammadia et al.* Benchmarks LLM grid-operator assistants against NERC standards under prompt-based adversarial attacks from authorized insiders, showing how easily safety alignment can be circumvented to produce regulation-violating outputs.

### [ARIstoteles — Dissecting Apple's Baseband Interface](https://arxiv.org/abs/2604.23457)
*ArXiv cs.CR — Tobias Kröll et al.* First-of-its-kind security research on iPhone cellular basebands, documenting an undocumented Apple protocol exposed via jailbreaks and opening the door to remote-attack-surface analysis on iOS that until now has been Android-only territory.

### [PARASITE: Conditional System Prompt Poisoning to Hijack LLMs](https://arxiv.org/abs/2505.16888)
*ArXiv cs.CR — Viet Pham, Thai Le.* Identifies a supply-chain vulnerability in third-party system prompts sold on public marketplaces: adversaries can inject "sleeper-agent" triggers into benign-looking prompts that activate only on specific conditions, evading routine review.

---

## Vulnerabilities & Exploits

### [Researchers Discover Critical GitHub CVE-2026-3854 RCE Flaw Exploitable via Single Git Push](https://thehackernews.com/2026/04/researchers-discover-critical-github.html)
*The Hacker News.* CVE-2026-3854 (CVSS 8.7) is a command-injection flaw in GitHub.com and GitHub Enterprise Server that lets any authenticated user with push access achieve remote code execution with a single `git push`.

### [Hackers are exploiting a critical LiteLLM pre-auth SQLi flaw](https://www.bleepingcomputer.com/news/security/hackers-are-exploiting-a-critical-litellm-pre-auth-sqli-flaw/)
*BleepingComputer — Bill Toulas.* Active exploitation of CVE-2026-42208, a pre-auth SQL injection in the LiteLLM open-source LLM gateway, is being used to siphon sensitive data from organizations routing model traffic through the proxy.

### [Critical Unpatched Flaw Leaves Hugging Face LeRobot Open to Unauthenticated RCE](https://thehackernews.com/2026/04/critical-cve-2026-25874-leaves-hugging.html)
*The Hacker News.* CVE-2026-25874 (CVSS 9.3) in LeRobot, Hugging Face's robotics platform with ~24K GitHub stars, is an untrusted-data deserialization bug that yields unauthenticated RCE — and remains unpatched at disclosure.

### [Microsoft Confirms Active Exploitation of Windows Shell CVE-2026-32202](https://thehackernews.com/2026/04/microsoft-confirms-active-exploitation.html)
*The Hacker News.* Microsoft updated its advisory to acknowledge in-the-wild exploitation of CVE-2026-32202, a Windows Shell spoofing flaw patched in this month's Patch Tuesday that allows attackers to access sensitive information.

### [Microsoft Patches Entra ID Role Flaw That Enabled Service Principal Takeover](https://thehackernews.com/2026/04/microsoft-patches-entra-id-role-flaw.html)
*The Hacker News.* Silverfort discovered that the new Agent ID Administrator role in Microsoft Entra ID — meant to manage AI-agent identities — could be abused for privilege escalation and identity takeover across an entire tenant.

### [VECT 2.0 Ransomware Irreversibly Destroys Files Over 131KB on Windows, Linux, ESXi](https://thehackernews.com/2026/04/vect-20-ransomware-irreversibly.html)
*The Hacker News.* A nonce-handling bug in VECT 2.0's encryption routine permanently destroys files over 131KB rather than encrypting them, meaning even paying victims cannot recover data on any platform variant.

### [Fresh Wave of GlassWorm VS Code Extensions Slices Through Supply Chain](https://www.darkreading.com/application-security/fresh-glassworm-vs-code-extensions-supply-chain)
*Dark Reading — Elizabeth Montalbano.* The GlassWorm campaign continues to seed Open VSX with seemingly benign VS Code extensions that drop self-propagating malware, scaling a developer-tooling supply-chain attack.

### [Checkmarx confirms LAPSUS$ hackers leaked its stolen GitHub data](https://www.bleepingcomputer.com/news/security/checkmarx-confirms-lapsus-hackers-leaked-its-stolen-github-data/)
*BleepingComputer — Bill Toulas.* Application security vendor Checkmarx confirmed that LAPSUS$ leaked data exfiltrated from one of its private GitHub repositories, raising questions about downstream exposure for customers.

### [Video service Vimeo confirms Anodot breach exposed user data](https://www.bleepingcomputer.com/news/security/video-service-vimeo-confirms-anodot-breach-exposed-user-data/)
*BleepingComputer — Bill Toulas.* Vimeo disclosed customer-data exposure stemming from the recent breach at Anodot, illustrating how third-party analytics vendors continue to be a soft underbelly for SaaS providers.

### [Feuding Ransomware Groups Leak Each Other's Data](https://www.darkreading.com/threat-intelligence/feuding-ransomware-groups-leak-data)
*Dark Reading — Alexander Culafi.* When 0APT and KryBit attacked each other, they exposed infrastructure and operational data, giving defenders a rare ground-truth view into ransomware tradecraft.

### [Vidar Rises to Top of Chaotic Infostealer Market](https://www.darkreading.com/vulnerabilities-threats/vidar-top-chaotic-infostealer-market)
*Dark Reading — Jai Vijayan.* Vidar has filled the vacuum left by last year's law-enforcement takedowns of Lumma and Rhadamanthys, becoming the dominant credential-theft platform in the underground market.

### [Brazilian LofyGang Resurfaces After Three Years With Minecraft LofyStealer Campaign](https://thehackernews.com/2026/04/brazilian-lofygang-resurfaces-after.html)
*The Hacker News.* The Brazilian cybercrime group LofyGang has returned after three years with LofyStealer (aka GrabBot), distributed disguised as a Minecraft hack called "Slinky" using the official game icon.

---

## Policy & Compliance

### [What Anthropic's Mythos Means for the Future of Cybersecurity](https://www.schneier.com/blog/archives/2026/04/what-anthropics-mythos-means-for-the-future-of-cybersecurity.html)
*Schneier on Security — Bruce Schneier.* Schneier argues that Claude Mythos Preview's autonomous discovery and weaponization of vulnerabilities in OS and internet infrastructure marks a structural shift in offense/defense economics, with consequences for patching cadence, disclosure norms, and software liability.

### [After Mythos: New Playbooks For a Zero-Window Era](https://thehackernews.com/2026/04/after-mythos-new-playbooks-for-zero.html)
*The Hacker News.* Practitioner-side counterpart to Schneier's piece: when AI-driven discovery collapses the patch-vs-exploit window, network detection and response (NDR) becomes the load-bearing control because containment now has to outpace patching.

### [Attack of the killer script kiddies](https://www.theverge.com/ai-artificial-intelligence/915660/mythos-script-kiddies-hackers-attack-cybersecurity-ai)
*The Verge AI — Yael Grauer.* Long-form look at DARPA's AIxCC challenge and what it portends now that AI-assisted vulnerability discovery is leaking from elite teams to mid-tier threat actors, dramatically lowering the bar for credible offensive operations.

### [Google inks deal allowing Pentagon to use AI models for classified work](https://www.japantimes.co.jp/business/2026/04/28/tech/google-classified-ai-deal-pentagon/)
*The Japan Times.* Reported agreement requires Google to adjust AI safety settings and content filters at the U.S. government's request for classified workloads — a notable carve-out in commercial-model use policy.

### [Microsoft to deprecate legacy TLS in Exchange Online starting July](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-deprecate-legacy-tls-in-exchange-online-starting-july/)
*BleepingComputer — Sergiu Gatlan.* Microsoft will begin blocking legacy TLS connections for POP and IMAP clients in Exchange Online from July 2026, a long-telegraphed compliance milestone that will break older mail clients still in production.

### [NSA Chief During Snowden Affair Shares Regrets, Reflections 13 Years Later](https://www.darkreading.com/cyber-risk/nsa-chief-during-snowden-affair-13-years-later)
*Dark Reading.* Former NSA deputy director Chris Inglis reflects publicly on what the agency got wrong around the Snowden disclosures and what CISOs should learn about insider-threat detection and organizational "enculturation."

### [Chinese Silk Typhoon Hacker Extradited to U.S. Over COVID Research Cyberattacks](https://thehackernews.com/2026/04/chinese-silk-typhoon-hacker-extradited.html)
*The Hacker News.* Xu Zewei, alleged Silk Typhoon operator, was extradited from Italy to face U.S. charges over 2020–2021 attacks on American government agencies and COVID-19 research organizations.

### [US reportedly charges Scattered Spider hacker arrested in Finland](https://www.bleepingcomputer.com/news/security/us-reportedly-charges-scattered-spider-hacker-arrested-in-finland/)
*BleepingComputer — Sergiu Gatlan.* A 19-year-old dual U.S./Estonian citizen arrested in Finland faces federal charges as a prolific member of Scattered Spider, the social-engineering collective behind several major 2024–2025 breaches.
