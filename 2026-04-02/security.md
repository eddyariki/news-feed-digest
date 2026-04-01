# Security Digest — 2026-04-02

Today's landscape is dominated by active exploitation campaigns leveraging phishing-as-a-service platforms and supply chain update mechanisms, while the research front sees a surge in adversarial fine-tuning attacks that bypass constitutional AI classifiers and prompt injection techniques targeting multimodal models.

---

## AI Security Research

**[GUARD-SLM: Token Activation-Based Defense Against Jailbreak Attacks for Small Language Models](https://arxiv.org/abs/2603.28817)**
*arXiv cs.CR*
Proposes a token activation-based defense mechanism to protect Small Language Models (SLMs) against jailbreak attacks, addressing a gap as SLMs increasingly replace larger models in resource-constrained deployments. The approach monitors internal activation patterns at inference time to detect and block adversarial inputs.

**[Trojan-Speak: Bypassing Constitutional Classifiers with No Jailbreak Tax via Adversarial Finetuning](https://arxiv.org/abs/2603.29038)**
*arXiv cs.CR*
Demonstrates that fine-tuning APIs expose a critical attack surface: adversarial fine-tuning can bypass Anthropic's Constitutional AI classifiers without degrading model capability (the "jailbreak tax"). The finding raises urgent questions about how AI providers gate and audit fine-tuning access.

**[Adversarial Prompt Injection Attack on Multimodal Large Language Models](https://arxiv.org/abs/2603.29418)**
*arXiv cs.CR*
Introduces new prompt injection techniques that exploit instruction-following behavior in multimodal LLMs, going beyond text-only methods to embed adversarial instructions in image content. Results show high attack success rates against leading MLLMs deployed in real-world pipelines.

**[Design Principles for a Benchmark Evaluating Security Operation Capabilities of Multi-agent AI Systems](https://arxiv.org/abs/2603.28998)**
*arXiv cs.CR*
Proposes a structured benchmark framework for measuring how well multi-agent LLM systems perform in cybersecurity operations roles, addressing the lack of standardized evaluation as organizations consider AI for SOC tasks. The work highlights capability gaps and safety concerns when agents are given offensive tool access.

**[AGFT: Alignment-Guided Fine-Tuning for Zero-Shot Adversarial Robustness of Vision-Language Models](https://arxiv.org/abs/2603.29410)**
*arXiv cs.CR*
Presents a fine-tuning method that preserves cross-modal alignment while improving adversarial robustness in vision-language models, addressing a known trade-off where existing adversarial training degrades zero-shot generalization. Evaluated across multiple VLMs and perturbation budgets.

---

## Vulnerabilities & Exploits

**[Hackers exploit TrueConf zero-day to push malicious software updates](https://www.bleepingcomputer.com/news/security/hackers-exploit-trueconf-zero-day-to-push-malicious-software-updates/)**
*BleepingComputer*
Attackers are exploiting an unpatched zero-day in TrueConf conference servers that allows them to execute arbitrary files on all connected endpoints by hijacking the software update mechanism. The supply-chain-style delivery gives attackers broad reach across any organization running TrueConf infrastructure.

**['NoVoice' Android malware on Google Play infected 2.3 million devices](https://www.bleepingcomputer.com/news/security/novoice-android-malware-on-google-play-infected-23-million-devices/)**
*BleepingComputer*
A newly discovered Android malware family dubbed NoVoice was distributed through more than 50 apps on the Google Play Store, accumulating at least 2.3 million installs before detection. The malware concealed itself within legitimate-looking utility and entertainment apps to evade store review processes.

**[CERT-UA Impersonation Campaign Spread AGEWHEEZE Malware to 1 Million Emails](https://thehackernews.com/2026/04/cert-ua-impersonation-campaign-spread.html)**
*The Hacker News*
The threat actor UAC-0255 sent roughly one million phishing emails impersonating Ukraine's CERT-UA to distribute AGEWHEEZE, a remote administration tool enabling persistent access to compromised systems. The campaign exploits trust in government cybersecurity communications to maximize open rates.

**[Microsoft Warns of WhatsApp-Delivered VBS Malware Hijacking Windows via UAC Bypass](https://thehackernews.com/2026/04/microsoft-warns-of-whatsapp-delivered.html)**
*The Hacker News*
Microsoft has flagged an active campaign, active since late February 2026, that delivers malicious Visual Basic Script files via WhatsApp messages to initiate a multi-stage infection chain and achieve persistence on Windows hosts via a UAC bypass. The use of WhatsApp as a delivery vector bypasses many enterprise email security controls.

**[New EvilTokens Service Fuels Microsoft Device Code Phishing Attacks](https://www.bleepingcomputer.com/news/security/new-eviltokens-service-fuels-microsoft-device-code-phishing-attacks/)**
*BleepingComputer*
EvilTokens is a new phishing-as-a-service kit that commoditizes device code phishing against Microsoft 365, automating token capture and account hijacking for business email compromise. The kit's built-in BEC features lower the skill bar for financially motivated attackers targeting enterprise accounts.

**[Routine Access Is Powering Modern Intrusions, a New Threat Report Finds](https://www.bleepingcomputer.com/news/security/routine-access-is-powering-modern-intrusions-a-new-threat-report-finds/)**
*BleepingComputer*
Blackpoint Cyber's threat report finds that most intrusions now begin with valid credentials and legitimate tool abuse — VPN access, RMM platforms, and social engineering — rather than zero-day exploits. The shift reinforces the urgency of identity-centric defenses over perimeter-focused approaches.

---

## Policy & Compliance

**[Is "Hackback" Official US Cybersecurity Strategy?](https://www.schneier.com/blog/archives/2026/04/is-hackback-official-us-cybersecurity-strategy.html)**
*Schneier on Security*
Bruce Schneier flags a notable sentence in the 2026 US "Cyber Strategy for America" that appears to authorize private-sector entities to "identify and disrupt adversary networks" — a significant escalation toward legitimizing hackback. While much of the document rehashes prior White House cyber strategy, this language could represent a formal policy shift with major legal and geopolitical implications.

**[FBI Warns Against Using Chinese Mobile Apps Due to Privacy Risks](https://www.bleepingcomputer.com/news/security/fbi-warns-against-using-chinese-mobile-apps-over-to-data-security-risks/)**
*BleepingComputer*
The FBI issued a public advisory warning Americans to avoid mobile applications developed by Chinese companies, citing data collection practices and the potential for compelled disclosure to Chinese authorities under national security laws. The warning extends the government's broader campaign to limit Chinese software and hardware in sensitive environments.
