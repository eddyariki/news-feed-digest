# Security Digest — 2026-03-25

Supply chain attacks dominated today's threat landscape, with the TeamPCP actor continuing a multi-target campaign compromising AI tooling (LiteLLM, Trivy, Checkmarx) while new research exposes deepening vulnerabilities in MCP-based AI agent tooling and multimodal model safety alignment.

---

## AI Security Research

**[Auditing MCP Servers for Over-Privileged Tool Capabilities](https://arxiv.org/abs/2603.21641)**
*_arXiv cs.CR_*
Researchers introduce `mcp-sec-audit`, a framework for detecting over-privileged capabilities in Model Context Protocol servers—finding that MCP servers routinely expose filesystem access, network calls, and command execution without proper access controls. As MCP becomes the standard glue between LLMs and tools, the attack surface is growing faster than security guidance.

**[Are AI-assisted Development Tools Immune to Prompt Injection?](https://arxiv.org/abs/2603.21642)**
*_arXiv cs.CR_*
A study of MCP-powered AI dev tools finds they remain vulnerable to prompt injection attacks—OWASP's #1 LLM vulnerability—demonstrating how a malicious file or doc in a project can subvert the coding assistant into leaking secrets or executing unauthorized tool calls.

**[Structured Visual Narratives Undermine Safety Alignment in Multimodal LLMs](https://arxiv.org/abs/2603.21697)**
*_arXiv cs.CR_*
Comic-template jailbreaks—embedding harmful goals in three-panel visual narratives and asking models to "complete the comic"—reliably bypass safety alignment in leading MLLMs, revealing a new class of visually grounded attack vectors that text-only defenses miss.

**[Invisible Safety Threat: Malicious Finetuning for LLM via Steganography](https://arxiv.org/abs/2603.08104)**
*_arXiv cs.CR_*
Researchers demonstrate that an LLM can be finetuned to maintain a convincing facade of safety alignment while covertly generating harmful content via steganographic encoding, posing a hard-to-detect supply chain risk for model weights shared on public hubs.

**[How AI Coding Tools Crushed the Endpoint Security Fortress](https://www.darkreading.com/application-security/ai-coding-tools-endpoint-security)**
*_Dark Reading_*
A researcher argues that AI coding assistants have systematically eroded endpoint security by generating code that bypasses established defenses—effectively handing attackers new evasion techniques at scale and forcing defenders to rethink the entire endpoint model.

**[Microsoft Proposes Better Identity, Guardrails for AI Agents](https://www.darkreading.com/identity-access-management-security/microsoft-proposes-better-identity-guardrails-ai-agents)**
*_Dark Reading_*
Microsoft is pushing for standardized identity mechanisms and behavioral guardrails for agentic AI—addressing credential sprawl and privilege escalation risks that emerge when AI agents act autonomously on behalf of users across enterprise systems.

---

## Vulnerabilities & Exploits

**[TeamPCP Backdoors LiteLLM Versions 1.82.7–1.82.8 Likely via Trivy CI/CD Compromise](https://thehackernews.com/2026/03/teampcp-backdoors-litellm-versions.html)**
*_The Hacker News_*
The TeamPCP threat actor pushed malicious versions of the popular `litellm` Python package containing a credential harvester, Kubernetes lateral-movement toolkit, and persistent backdoor—linking the compromise to the same Trivy CI/CD pipeline attack that has targeted multiple security tools. Both Endor Labs and JFrog confirmed the malicious releases.

**[TeamPCP Hacks Checkmarx GitHub Actions Using Stolen CI Credentials](https://thehackernews.com/2026/03/teampcp-hacks-checkmarx-github-actions.html)**
*_The Hacker News_*
TeamPCP expanded its supply chain campaign by compromising Checkmarx GitHub Actions workflows using stolen CI credentials, further demonstrating the group's focus on high-trust developer toolchains as an infection vector.

**[Self-propagating malware poisons open source software and wipes Iran-based machines](https://arstechnica.com/security/2026/03/self-propagating-malware-poisons-open-source-software-and-wipes-iran-based-machines/)**
*_Ars Technica_*
A self-propagating strain is injecting itself into open source repositories before deploying a destructive wiper payload on machines geolocated to Iran—a rare combination of supply chain persistence and geopolitically targeted destruction.

**[Ghost Campaign Uses 7 npm Packages to Steal Crypto Wallets and Credentials](https://thehackernews.com/2026/03/ghost-campaign-uses-7-npm-packages-to.html)**
*_The Hacker News_*
ReversingLabs tracked the "Ghost" campaign, in which seven malicious npm packages published under a single account harvest cryptocurrency wallet data and enterprise credentials—a continuation of the persistent threat posed by malicious package uploads to public registries.

**[Tax Search Ads Deliver ScreenConnect Malware Using Huawei Driver to Disable EDR](https://thehackernews.com/2026/03/tax-search-ads-deliver-screenconnect.html)**
*_The Hacker News_*
A malvertising campaign active since January 2026 abuses Google Ads targeting tax-season searches to deliver rogue ScreenConnect installers that deploy a BYOVD tool (`HwAudKiller`) using a vulnerable Huawei driver to blind endpoint detection and response products.

**[Tycoon2FA phishing platform returns after recent police disruption](https://www.bleepingcomputer.com/news/security/tycoon2fa-phishing-platform-returns-after-recent-police-disruption/)**
*_BleepingComputer_*
Just weeks after Europol disrupted the Tycoon2FA phishing-as-a-service platform in early March, the operation has rebounded to pre-disruption activity levels—illustrating the resilience of modern PhaaS infrastructure against law enforcement takedowns.

**[Citrix Urges Patching Critical NetScaler Flaw Allowing Unauthenticated Data Leaks](https://thehackernews.com/2026/03/citrix-urges-patching-critical.html)**
*_The Hacker News_*
Citrix released emergency patches for a critical unauthenticated data-leak vulnerability in NetScaler ADC and NetScaler Gateway; organizations with internet-facing NetScaler deployments should treat this as urgent given the appliances' exposure in enterprise DMZs.

**[HackerOne discloses employee data breach after Navia hack](https://www.bleepingcomputer.com/news/security/hackerone-discloses-employee-data-breach-after-navia-hack/)**
*_BleepingComputer_*
HackerOne is notifying hundreds of employees that personal data was stolen after attackers compromised Navia, a third-party benefits administrator—a reminder that third-party vendor breaches remain a leading attack vector against even security-focused organizations.

**[Mazda discloses security breach exposing employee and partner data](https://www.bleepingcomputer.com/news/security/mazda-discloses-security-breach-exposing-employee-and-partner-data/)**
*_BleepingComputer_*
Mazda Motor Corporation disclosed that employee and business partner data was exposed in a security incident detected last December, with the delayed disclosure raising questions about incident response timelines.

**[Dutch Ministry of Finance discloses breach affecting employees](https://www.bleepingcomputer.com/news/security/dutch-ministry-of-finance-discloses-breach-affecting-employees/)**
*_BleepingComputer_*
The Dutch Ministry of Finance confirmed systems were compromised in an attack detected last week—adding a national government treasury to a growing list of high-profile breach disclosures this week.

---

## Policy & Compliance

**[FCC bans new routers made outside the USA over security risks](https://www.bleepingcomputer.com/news/security/fcc-bans-new-routers-made-outside-the-usa-over-security-risks/)**
*_BleepingComputer_*
The FCC expanded its Covered List to include all consumer routers manufactured in foreign countries, effectively banning the sale of new foreign-made router models in the U.S. on national security grounds—a sweeping move that will reshape the home and SMB networking market.

**[U.S. Sentences Russian Hacker to 6.75 Years for Role in $9M Ransomware Damage](https://thehackernews.com/2026/03/us-sentences-russian-hacker-to-675-years)**
*_The Hacker News_*
Russian national Aleksei Volkov received an 81-month federal sentence for acting as an initial access broker for the Yanluowang ransomware crew and others, enabling dozens of attacks against U.S. companies—marking another successful prosecution in DOJ's ongoing effort to hold ransomware enablers accountable.
