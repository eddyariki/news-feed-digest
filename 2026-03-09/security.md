# Security Digest — 2026-03-09

Today's security landscape is dominated by state-sponsored espionage campaigns targeting communications apps and critical infrastructure, while the AI security frontier sees simultaneous advances in jailbreak techniques and defenses—and a major industry consolidation as OpenAI moves to own its own red-teaming toolchain.

---

## AI Security Research

- **[Depth Charge: Jailbreak Large Language Models from Deep Safety Attention Heads](https://arxiv.org/abs/2603.05772)** — *arXiv cs.CR*
  Researchers introduce an attack that bypasses alignment by targeting safety mechanisms embedded in deeper model layers rather than the prompt surface, exposing vulnerabilities that shallow-level defenses miss entirely.

- **[Knowing without Acting: The Disentangled Geometry of Safety Mechanisms in Large Language Models](https://arxiv.org/abs/2603.05773)** — *arXiv cs.CR*
  The paper proposes the Disentangled Safety Hypothesis (DSH), finding that LLMs can "recognize" harmful intent without triggering refusal—a structural decoupling that explains why jailbreaks keep working despite alignment training.

- **[Reasoned Safety Alignment: Ensuring Jailbreak Defense via Answer-Then-Check](https://arxiv.org/abs/2509.11629)** — *arXiv cs.CR*
  A novel alignment approach that lets models first generate an answer and then apply a reasoning step to catch jailbreak violations, outperforming conventional refusal-first methods on robustness benchmarks.

- **[When One Modality Rules Them All: Backdoor Modality Collapse in Multimodal Diffusion Models](https://arxiv.org/abs/2603.06508)** — *arXiv cs.CR*
  Attacking both text and image inputs simultaneously doesn't compound backdoor strength—one modality dominates and collapses the other's contribution, a surprising finding with implications for multimodal model security.

- **['InstallFix' Attacks Spread Fake Claude Code Sites](https://www.darkreading.com/cloud-security/installfix-attacks-fake-claude-code)** — *Dark Reading*
  A new campaign blends malvertising with ClickFix-style social engineering to lure developers into running malicious CLI commands via fake AI coding assistant sites, highlighting risks in the AI tooling supply chain.

- **[OpenAI to Acquire Promptfoo](https://openai.com/index/openai-to-acquire-promptfoo)** — *OpenAI*
  OpenAI is acquiring the AI red-teaming platform Promptfoo to build automated vulnerability testing—covering jailbreaks, prompt injections, and data leaks—directly into its Frontier enterprise product.

---

## Vulnerabilities & Exploits

- **[New Attack Against Wi-Fi (AirSnitch)](https://www.schneier.com/blog/archives/2026/03/new-attack-against-wi-fi.html)** — *Schneier on Security*
  AirSnitch exploits cross-layer identity desynchronization across Wi-Fi Layers 1 and 2 to enable a full bidirectional machine-in-the-middle attack without requiring any prior network access.

- **[Dutch Govt Warns of Signal, WhatsApp Account Hijacking Attacks](https://www.bleepingcomputer.com/news/security/dutch-govt-warns-of-signal-whatsapp-account-hijacking-attacks/)** — *BleepingComputer*
  Russian state-sponsored actors are running an active phishing campaign against government officials, military personnel, and journalists to hijack encrypted messaging accounts and access sensitive communications.

- **[Malicious npm Package Posing as OpenClaw Installer Deploys RAT, Steals macOS Credentials](https://thehackernews.com/2026/03/malicious-npm-package-posing-as.html)** — *The Hacker News*
  The `@openclaw-ai/openclawai` package, uploaded to npm on March 3, deploys a remote access trojan and harvests credentials from macOS hosts; it has been downloaded 178 times and remains live.

- **[UNC4899 Breached Crypto Firm After Developer AirDropped Trojanized File to Work Device](https://thehackernews.com/2026/03/unc4899-used-airdrop-file-transfer-and.html)** — *The Hacker News*
  North Korean threat actor UNC4899 (Jade Sleet / Slow Pisces) compromised a cryptocurrency organization by tricking a developer into AirDropping a trojanized file onto their work machine, resulting in millions in stolen crypto.

- **[Chrome Extension Turns Malicious After Ownership Transfer, Enabling Code Injection and Data Theft](https://thehackernews.com/2026/03/chrome-extension-turns-malicious-after.html)** — *The Hacker News*
  Two Chrome extensions became malicious post-ownership-transfer, pushing silent updates that inject arbitrary code and harvest user data—a reminder that extension supply chains remain a persistent attack surface.

- **[ShinyHunters Claims Ongoing Salesforce Aura Data Theft Attacks](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-ongoing-salesforce-aura-data-theft-attacks/)** — *BleepingComputer*
  The ShinyHunters extortion group claims to be exploiting a new bug in Salesforce Experience Cloud to exfiltrate data, beyond the misconfigured guest-access issue Salesforce is already warning customers about.

- **[Web Server Exploits and Mimikatz Used in Attacks Targeting Asian Critical Infrastructure](https://thehackernews.com/2026/03/web-server-exploits-and-mimikatz-used.html)** — *The Hacker News*
  Palo Alto Unit 42 attributes a years-long campaign against aviation, energy, telecom, and government sectors across South, Southeast, and East Asia to a previously undocumented Chinese threat group.

---

## Policy & Compliance

- **[Anthropic's Groundbreaking Lawsuit Challenges the Government's Power to Punish AI Safety Decisions](https://the-decoder.com/anthropics-groundbreaking-lawsuit-challenges-the-governments-power-to-punish-ai-safety-decisions/)** — *The Decoder*
  Anthropic has sued 17 US federal agencies, with a 48-page complaint revealing Claude's deep integration in classified Pentagon systems and alleging the government pressured the company with contradictory threats when it refused to drop safety guardrails.

- **[The DSA's Blind Spot: Algorithmic Audit of Advertising and Minor Profiling on TikTok](https://arxiv.org/abs/2603.05653)** — *arXiv*
  Researchers find that the EU Digital Services Act's narrow definition of "advertisement" leaves influencer marketing and other non-traditional ad formats outside its prohibition on profiling-based advertising to minors, creating a significant regulatory gap.

- **[FBI Warns of Phishing Attacks Impersonating US City, County Officials](https://www.bleepingcomputer.com/news/security/fbi-warns-of-phishing-attacks-impersonating-us-city-county-officials/)** — *BleepingComputer*
  The FBI issued an advisory warning that criminals are impersonating US local government officials to defraud businesses and individuals seeking city and county planning or zoning permits.
