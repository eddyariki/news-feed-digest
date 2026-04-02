# Security Digest — 2026-04-03

RSAC 2026 dominated this week's landscape as AI-driven threats took center stage alongside a wave of critical CVEs, active exploit campaigns, and a US executive order banning foreign-made consumer routers. AI safety researchers are publishing rapidly on jailbreaks, model merging vulnerabilities, and prompt injection evasion.

---

## AI Security Research

**[The Persistent Vulnerability of Aligned AI Systems](https://arxiv.org/abs/2604.00324)**
*ArXiv cs.AI*
A new thesis maps four open problems for deployed autonomous AI agents — detecting dangerous internal computations, removing embedded dangerous behaviors, pre-deployment vulnerability testing, and predicting when models act against deployers. Introduces ACDC for automated circuit discovery in transformers as a concrete step toward the first problem.

**[Bypassing Prompt Injection Detectors through Evasive Injections](https://arxiv.org/abs/2602.00750)**
*ArXiv cs.AI*
ML-based prompt injection detectors that analyze LLM activation shifts can be systematically evaded with crafted "evasive injections" — the paper demonstrates that current state-of-the-art defenses degrade significantly as context length grows and are vulnerable to adversarial circumvention.

**[Robust Multimodal Safety via Conditional Decoding](https://arxiv.org/abs/2604.00310)**
*ArXiv cs.AI*
Proposes CASA (Classification Augmented with Safety Attention), a conditional decoding strategy that uses internal MLLM representations to detect harmful queries that exploit cross-modal interactions — addressing the known failure mode where text-aligned models become unsafe when images are added.

**[When Safe Models Merge into Danger: Exploiting Latent Vulnerabilities in LLM Fusion](https://arxiv.org/abs/2604.00627)**
*ArXiv cs.CR*
Introduces TrojanMerge, a framework showing that model merging — widely used to combine fine-tuned LLMs — can be exploited to embed hidden backdoors that bypass safety alignment, even when each individual model appears safe. The attack surface is underexplored and broadly applicable.

**[AgentWatcher: A Rule-based Prompt Injection Monitor](https://arxiv.org/abs/2604.01194)**
*ArXiv cs.CR*
Proposes a rule-based monitoring layer for LLM agents that makes prompt injection detection explicit and auditable, addressing the opacity and context-length limitations of purely ML-based detectors.

**[Jailbreaking Generative AI: Multivector Phishing Threats and Transformer-based Defenses](https://arxiv.org/abs/2507.12185)**
*ArXiv cs.CR*
Empirical study showing that novices can bypass ChatGPT-4o-Mini's safeguards to generate complete multivector phishing attacks across email, web, SMS, and voice channels — highlights low barrier-to-entry for GenAI-assisted social engineering.

---

## Vulnerabilities & Exploits

**[Claude Code leak used to push infostealer malware on GitHub](https://www.bleepingcomputer.com/news/security/claude-code-leak-used-to-push-infostealer-malware-on-github/)**
*BleepingComputer*
Threat actors are exploiting the recent Claude Code source code leak via fake GitHub repositories to deliver Vidar infostealer malware to developers seeking access to the leaked code.

**[Cisco Patches 9.8 CVSS IMC and SSM Flaws Allowing Remote System Compromise](https://thehackernews.com/2026/04/cisco-patches-98-cvss-imc-and-ssm-flaws.html)**
*The Hacker News*
CVE-2026-20093 (CVSS 9.8) allows an unauthenticated remote attacker to bypass authentication in Cisco Integrated Management Controller and gain elevated privileges; Cisco has released patches for this and related high-severity SSM flaws.

**[Hackers Exploit CVE-2025-55182 to Breach 766 Next.js Hosts, Steal Credentials](https://thehackernews.com/2026/04/hackers-exploit-cve-2025-55182-to.html)**
*The Hacker News*
A Cisco Talos-tracked threat cluster used the React2Shell Next.js vulnerability to harvest database credentials, SSH keys, AWS secrets, Stripe API keys, and GitHub tokens at scale across 766 compromised hosts.

**[New Progress ShareFile flaws can be chained in pre-auth RCE attacks](https://www.bleepingcomputer.com/news/security/new-progress-sharefile-flaws-can-be-chained-in-pre-auth-rce-attacks/)**
*BleepingComputer*
Two vulnerabilities in Progress ShareFile (enterprise secure file transfer) can be chained for unauthenticated file exfiltration — enterprises relying on ShareFile for sensitive transfers should patch immediately.

**[Over 14,000 F5 BIG-IP APM instances still exposed to RCE attacks](https://www.bleepingcomputer.com/news/security/over-14-000-f5-big-ip-apm-instances-still-exposed-to-rce-attacks/)**
*BleepingComputer*
Shadowserver reports 14,000+ BIG-IP APM instances remain unpatched and actively targeted via a critical RCE vulnerability, exposing network access management infrastructure to full compromise.

**[Possible US Government iPhone Hacking Tool Leaked](https://www.schneier.com/blog/archives/2026/04/possible-us-government-iphone-hacking-tool-leaked.html)**
*Schneier on Security*
Google researchers disclosed "Coruna," a sophisticated iOS exploit kit using 23 vulnerabilities across five exploit chains capable of silently installing malware via a single website visit — believed to be a leaked US government tool.

**[Apple Expands iOS 18.7.7 Update to More Devices to Block DarkSword Exploit](https://thehackernews.com/2026/04/apple-expands-ios-1877-update-to-more.html)**
*The Hacker News*
Apple broadened the iOS 18.7.7 rollout to protect older devices from the actively exploited DarkSword exploit kit — users with automatic updates should verify they've received it.

**[Drift loses $280 million as hackers seize Security Council powers](https://www.bleepingcomputer.com/news/security/drift-loses-280-million-as-hackers-seize-security-council-powers/)**
*BleepingComputer*
In a planned, sophisticated operation, threat actors took control of Drift Protocol's Security Council administrative functions and drained at least $280 million in a DeFi governance attack.

**[Medtech giant Stryker fully operational after data-wiping attack](https://www.bleepingcomputer.com/news/security/medtech-giant-stryker-fully-operational-after-data-wiping-attack/)**
*BleepingComputer*
Stryker is back online three weeks after the Iranian-linked Handala hacktivist group wiped systems in a destructive attack on one of the world's largest medical technology companies.

**[WhatsApp Alerts 200 Users After Fake iOS App Installed Spyware](https://thehackernews.com/2026/04/whatsapp-alerts-200-users-after-fake.html)**
*The Hacker News*
Meta alerted ~200 users, primarily in Italy, who were socially engineered into installing a trojanized WhatsApp iOS app; an Italian firm is under investigation in connection with the spyware campaign.

---

## Policy & Compliance

**[US Bans All Foreign-Made Consumer Routers](https://www.schneier.com/blog/archives/2026/04/us-bans-all-foreign-made-consumer-routers.html)**
*Schneier on Security*
A new executive order prohibits sales of new consumer routers manufactured outside the US, citing supply chain vulnerabilities that could disrupt critical infrastructure and national defense — existing routers are unaffected.

**[RSAC 2026: AI Dominates, But Community Remains Key to Security](https://www.darkreading.com/cybersecurity-operations/rsac-2026-ai-dominates-community)**
*Dark Reading*
At this year's RSA Conference, experts debated AI automation vs. human oversight as the US government was notably absent; the consensus: AI amplifies defenders and attackers alike, but human judgment remains irreplaceable.

**[Geopolitics, AI, and Cybersecurity: Insights From RSAC 2026](https://www.darkreading.com/cybersecurity-operations/geopolitics-ai-cybersecurity-insights-rsac-2026)**
*Dark Reading*
RSAC 2026 panels surfaced geopolitical fragmentation as a core driver of AI-enabled threat escalation, with global leadership shifts changing the threat actor landscape and complicating international cyber norms.

**[Ransomware Will Hit Hospitals. Rehearsals Are Key to Defense](https://www.darkreading.com/cybersecurity-operations/ransomware-hospitals-preparation-key-defense)**
*Dark Reading*
A chief medical information officer argues that hospital ransomware preparedness must shift from prevention to rehearsal — practiced downtime procedures determine whether an attack causes hours or weeks of outages.
