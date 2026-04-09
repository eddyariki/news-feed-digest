# Security Digest — 2026-04-09

Nation-state actors dominate today's threat landscape with active campaigns from APT28, Iranian groups, and North Korean supply-chain operators, while new LLM research surfaces persistent jailbreak vectors and a 13-year-old RCE flaw in Apache ActiveMQ demands immediate attention.

---

## AI Security Research

**[Anthropic's Claude Mythos Finds Thousands of Zero-Day Flaws Across Major Systems](https://thehackernews.com/2026/04/anthropics-claude-mythos-finds.html)**
*The Hacker News*

Anthropic's Project Glasswing deployed a preview of Claude Mythos to autonomously discover and triage security vulnerabilities across major software systems, surfacing thousands of previously unknown zero-days. The initiative marks a significant escalation in AI-assisted offensive security research, raising questions about responsible disclosure at scale.

**[FreakOut-LLM: The Effect of Emotional Stimuli on Safety Alignment](https://arxiv.org/abs/2604.04992)**
*ArXiv cs.AI*

Researchers introduce FreakOut-LLM, a framework showing that emotionally charged prompts can bypass refusal training in safety-aligned LLMs, even when direct harmful requests are blocked. The findings suggest current alignment methods are brittle against social-engineering-style inputs targeting emotional context.

**[Gradient-Controlled Decoding: A Safety Guardrail for LLMs with Dual-Anchor Steering](https://arxiv.org/abs/2604.05179)**
*ArXiv cs.CL*

A new decoding-time defense steers LLM outputs away from jailbreak and prompt-injection attacks using dual-anchor gradient signals, reducing harmful outputs without the over-refusal penalties seen in most filter-based approaches. The method operates at inference time with no retraining required.

**[Phonetic Perturbations Reveal Tokenizer-Rooted Safety Gaps in LLMs](https://arxiv.org/abs/2505.14226)**
*ArXiv cs.AI*

The CMP-RT red-teaming probe shows that phonetic misspellings and code-mixed text can reliably bypass safety filters, because tokenizers treat phonetically equivalent strings as semantically distinct. This tokenizer-level blind spot undermines alignment that operates on surface-form representations.

**[Towards Reliable Forgetting: A Survey on Machine Unlearning Verification](https://arxiv.org/abs/2506.15115)**
*ArXiv cs.LG*

A comprehensive survey of machine unlearning verification techniques examines whether models have truly forgotten sensitive training data in response to GDPR and privacy compliance demands. The authors find that most current verification methods fail to provide strong guarantees, leaving unlearning claims largely unaudited.

**[Robust AI Security and Alignment: A Sisyphean Endeavor?](https://arxiv.org/abs/2512.10100)**
*ArXiv cs.AI*

Extending Gödel's incompleteness theorem to AI systems, this paper establishes information-theoretic limits on how robust any alignment or security mechanism can be. The authors argue practitioners should plan for fundamental adversarial gaps rather than assume they can be closed.

---

## Vulnerabilities & Exploits

**[N. Korean Hackers Spread 1,700 Malicious Packages Across npm, PyPI, Go, Rust](https://thehackernews.com/2026/04/n-korean-hackers-spread-1700-malicious.html)**
*The Hacker News*

The Contagious Interview campaign linked to North Korea has expanded to Go, Rust, and PHP ecosystems with 1,700 typosquatting packages designed to impersonate legitimate developer tools and steal credentials. The breadth of the campaign represents a significant escalation in DPRK supply-chain operations.

**[Python Supply-Chain Compromise](https://www.schneier.com/blog/archives/2026/04/python-supply-chain-compromise.html)**
*Schneier on Security*

A malicious `.pth` file was found embedded in `litellm` version 1.82.8 on PyPI, automatically executing on import to exfiltrate environment variables and credentials. The attack targets the popular LLM gateway library, putting AI application deployments at particular risk.

**[APT28 Deploys PRISMEX Malware in Campaign Targeting Ukraine and NATO Allies](https://thehackernews.com/2026/04/apt28-deploys-prismex-malware-in.html)**
*The Hacker News*

Russia's APT28 (Forest Blizzard) is running a spear-phishing campaign against Ukraine and NATO allies using a new malware suite called PRISMEX, which combines advanced exfiltration with lateral movement capabilities. The campaign signals continued Russian intelligence operations against Western defense infrastructure.

**[Iranian Threat Actors Disrupt US Critical Infrastructure Via Exposed PLCs](https://www.darkreading.com/ics-ot-security/iranian-threat-actors-us-critical-infrastructure-exposed-plcs)**
*Dark Reading*

Iranian-linked actors compromised Internet-facing operational technology devices across multiple US sectors, causing file manipulation, display tampering, and operational disruption with financial losses. The attacks exploited internet-exposed PLCs with weak or default credentials.

**[13-year-old bug in ActiveMQ lets hackers remotely execute commands](https://www.bleepingcomputer.com/news/security/13-year-old-bug-in-activemq-lets-hackers-remotely-execute-commands/)**
*BleepingComputer*

A newly disclosed RCE vulnerability in Apache ActiveMQ Classic has existed undetected for 13 years and can be exploited to execute arbitrary commands on affected systems. Organizations running ActiveMQ in messaging infrastructure should treat patching as urgent given the vulnerability's age and likely wide deployment.

**[New macOS stealer campaign uses Script Editor in ClickFix attack](https://www.bleepingcomputer.com/news/security/new-macos-stealer-campaign-uses-script-editor-in-clickfix-attack/)**
*BleepingComputer*

A new Atomic Stealer campaign targets macOS users by abusing Script Editor in a ClickFix variant that tricks victims into pasting and executing malicious Terminal commands. The technique bypasses traditional social engineering defenses by exploiting user trust in UI-prompted copy-paste flows.

**[New Chaos Variant Targets Misconfigured Cloud Deployments, Adds SOCKS Proxy](https://thehackernews.com/2026/04/new-chaos-variant-targets-misconfigured.html)**
*The Hacker News*

A new Chaos malware variant is actively scanning for misconfigured cloud deployments and has added SOCKS5 proxy capability to expand its command-and-control infrastructure. The botnet's cloud targeting signals a deliberate pivot toward higher-value, internet-facing enterprise environments.

---

## Policy & Compliance

**[CISA orders feds to patch exploited Ivanti EPMM flaw by Sunday](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-exploited-ivanti-epmm-flaw-by-sunday/)**
*BleepingComputer*

CISA issued a binding operational directive giving federal agencies four days to remediate a critical vulnerability in Ivanti Endpoint Manager Mobile (EPMM) that has been actively exploited since January. The tight deadline reflects CISA's assessment that the flaw poses immediate risk to government networks.

**[AI-Led Remediation Crisis Prompts HackerOne to Pause Bug Bounties](https://www.darkreading.com/application-security/ai-led-remediation-crisis-prompts-hackerone-pause-bug-bounties)**
*Dark Reading*

HackerOne is pausing bug bounty programs on several open-source projects after AI-automated vulnerability discovery outpaced human remediation capacity, creating a backlog that bounties cannot incentivize fixing. The move highlights an emerging policy gap: discovery economics have flipped, but remediation funding models have not.
