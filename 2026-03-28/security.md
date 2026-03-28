# Security Digest — 2026-03-28

Today's security landscape is defined by a surge in AI-framework vulnerabilities and supply chain attacks, while geopolitical cyber operations intensify across critical infrastructure and state-linked threat actors push nation-state-grade tooling into broader criminal markets.

---

## AI Security Research

**[Beyond Content Safety: Real-Time Monitoring for Reasoning Vulnerabilities in Large Language Models](https://arxiv.org/abs/2603.25412)**
*ArXiv cs.AI*
Chain-of-thought reasoning in LLMs introduces safety gaps that content-layer filters miss; this paper proposes real-time monitoring of the reasoning process itself to detect vulnerabilities before they manifest in outputs.

**[The System Prompt Is the Attack Surface: How LLM Agent Configuration Shapes Security and Creates Exploitable Vulnerabilities](https://arxiv.org/abs/2603.25056)**
*ArXiv cs.AI*
System prompt design can swing LLM email agents from near-total phishing blindness to near-perfect detection, demonstrating that agent configuration is a primary—and underappreciated—security variable.

**[PIDP-Attack: Combining Prompt Injection with Database Poisoning Attacks on Retrieval-Augmented Generation Systems](https://arxiv.org/abs/2603.25164)**
*ArXiv cs.AI*
A combined prompt-injection/database-poisoning attack against RAG pipelines that allows adversaries to corrupt retrieved knowledge and manipulate LLM outputs without direct model access.

**[DRIFT: Dynamic Rule-Based Defense with Injection Isolation for Securing LLM Agents](https://arxiv.org/abs/2506.12104)**
*ArXiv cs.AI*
DRIFT proposes runtime injection isolation for LLM-based agentic systems, dynamically enforcing rule boundaries to prevent compromised tool outputs from escalating privileges.

**[SABER: A Stealthy Agentic Black-Box Attack Framework for Vision-Language-Action Models](https://arxiv.org/abs/2603.24935)**
*ArXiv cs.RO*
A black-box adversarial framework targeting the natural-language instruction channel of VLA robotics models, enabling stealthy manipulation of robot behavior without access to model weights.

**[NeuroStrike: Neuron-Level Attacks on Aligned LLMs](https://arxiv.org/abs/2509.11864)**
*ArXiv cs.CR*
Fine-grained neuron-level perturbations can bypass RLHF safety alignment in LLMs, raising the alarm that current alignment techniques may not be robust against targeted model-layer manipulation.

**[LiteGuard: Efficient Task-Agnostic Model Fingerprinting with Enhanced Generalization](https://arxiv.org/abs/2603.24982)** / **[IrisFP: Adversarial-Example-based Model Fingerprinting](https://arxiv.org/abs/2603.24996)**
*ArXiv cs.CR*
Two complementary papers advance model IP protection: LiteGuard offers lightweight universal fingerprinting across task types, while IrisFP uses multi-boundary adversarial examples to improve fingerprint uniqueness and robustness against evasion.

**[Can You Tell It's AI? Human Perception of Synthetic Voices in Vishing Scenarios](https://arxiv.org/abs/2602.20061)**
*ArXiv cs.CR*
Modern TTS systems produce voice scams convincing enough to fool most humans; the study finds detection rates fall sharply when call context is realistic, underscoring the urgency of audio-deepfake detection tools.

**[Unveiling the Resilience of LLM-Enhanced Search Engines against Black-Hat SEO Manipulation](https://arxiv.org/abs/2603.25500)**
*ArXiv cs.CR*
Evaluates whether LLM-integrated search engines inherit traditional search engines' vulnerability to SEO poisoning attacks, finding that while LLMs add some resilience, they remain susceptible to carefully crafted adversarial content.

**[LangChain, LangGraph Flaws Expose Files, Secrets, Databases in Widely Used AI Frameworks](https://thehackernews.com/2026/03/langchain-langgraph-flaws-expose-files.html)**
*The Hacker News*
Three now-patched vulnerabilities in LangChain and LangGraph could expose filesystem data, environment secrets, and conversation histories—a reminder that the AI agent framework layer carries significant attack surface.

---

## Vulnerabilities & Exploits

**[Backdoored Telnyx PyPI Package Pushes Malware Hidden in WAV Audio](https://www.bleepingcomputer.com/news/security/backdoored-telnyx-pypi-package-pushes-malware-hidden-in-wav-audio/)** / **[TeamPCP Pushes Malicious Telnyx Versions to PyPI, Hides Stealer in WAV Files](https://thehackernews.com/2026/03/teampcp-pushes-malicious-telnyx.html)**
*BleepingComputer / The Hacker News*
TeamPCP—the same group behind earlier supply chain hits on Trivy, KICS, and litellm—has now poisoned the telnyx Python package on PyPI with credential-stealing malware concealed inside WAV audio files.

**[Apple Sends Lock Screen Alerts to Outdated iPhones Over Active Web-Based Exploits](https://thehackernews.com/2026/03/apple-sends-lock-screen-alerts-to.html)**
*The Hacker News*
Apple is pushing on-device lock screen notifications urging users on older iOS versions to update immediately, citing active web-based attacks targeting unpatched devices.

**[Fake VS Code Alerts on GitHub Spread Malware to Developers](https://www.bleepingcomputer.com/news/security/fake-vs-code-alerts-on-github-spread-malware-to-developers/)**
*BleepingComputer*
A large-scale campaign is abusing GitHub Discussions on popular repositories to post fake VS Code security alerts that lure developers into downloading malware—a high-trust vector targeting the software supply chain at its source.

**[Open VSX Bug Let Malicious VS Code Extensions Bypass Pre-Publish Security Checks](https://thehackernews.com/2026/03/open-vsx-bug-let-malicious-vs-code.html)**
*The Hacker News*
A now-patched flaw in Open VSX's pre-publish scanning pipeline could be exploited to slip malicious VS Code extensions past automated security review, threatening any developer who installs extensions from the open registry.

**[China Upgrades the Backdoor It Uses to Spy on Telcos Globally](https://www.darkreading.com/cyberattacks-data-breaches/china-upgrades-backdoor-spy-telcos-globally)**
*Dark Reading*
Chinese APT Red Menshen has significantly upgraded BPFdoor, a kernel-level backdoor used against global telecom providers; the new variant evades traditional security controls, leaving telcos with hunting as their primary defensive option.

**[European Commission Investigating Breach After Amazon Cloud Account Hack](https://www.bleepingcomputer.com/news/security/european-commission-investigating-breach-after-amazon-cloud-account-hack/)**
*BleepingComputer*
A threat actor gained access to the European Commission's Amazon cloud environment; the Commission has opened a formal investigation while assessing scope and impact.

**[AitM Phishing Targets TikTok Business Accounts Using Cloudflare Turnstile Evasion](https://thehackernews.com/2026/03/aitm-phishing-targets-tiktok-business.html)**
*The Hacker News*
Adversary-in-the-middle phishing pages designed to capture TikTok for Business credentials are leveraging Cloudflare Turnstile to evade bot-detection and extend campaign lifespan.

**[Bearlyfy Hits Russian Firms with Custom GenieLocker Ransomware](https://thehackernews.com/2026/03/bearlyfy-hits-russian-firms-with-custom.html)**
*The Hacker News*
Pro-Ukrainian hacktivist group Bearlyfy has conducted over 70 ransomware attacks against Russian businesses since January 2025 using their custom GenieLocker payload, continuing a trend of conflict-driven ransomware operations.

**[Dutch Police Discloses Security Breach After Phishing Attack](https://www.bleepingcomputer.com/news/security/dutch-police-discloses-security-breach-after-phishing-attack/)**
*BleepingComputer*
The Dutch National Police confirmed a breach stemming from a successful phishing attack, stating impact was limited and no citizen data was affected.

**[Coruna, DarkSword & Democratizing Nation-State Exploit Kits](https://www.darkreading.com/threat-intelligence/coruna-darksword-democratizing-nation-state-exploit-kits)**
*Dark Reading*
Nation-state-grade malware is appearing on the dark web and GitHub, putting sophisticated exploit capabilities in reach of ordinary criminal actors and significantly raising the baseline threat organizations must defend against.

**[Wartime Usage of Compromised IP Cameras Highlight Their Danger](https://www.darkreading.com/vulnerabilities-threats/wartime-usage-compromised-ip-cameras-highlight-danger)**
*Dark Reading*
Multiple countries are actively exploiting internet-connected cameras to conduct surveillance inside adversaries' networks, with the list of participating nations expanding—highlighting persistent risks of internet-exposed OT/IoT devices.

---

## Policy & Compliance

**[Google Sets 2029 Deadline for Quantum-Safe Cryptography](https://www.darkreading.com/cybersecurity-operations/google-sets-2029-deadline-quantum-safe-cryptography)**
*Dark Reading*
Google has committed to completing its post-quantum cryptography migration by 2029, signaling to the industry that the window for PQC transition planning is shorter than many assume.

**[We Are At War](https://thehackernews.com/2026/03/we-are-at-war.html)**
*The Hacker News*
An analysis of how rising geopolitical tensions are manifesting—and in some cases being preceded—by cyber operations, arguing that the security community must adopt a wartime posture given the scale and coordination of state-linked attacks.
