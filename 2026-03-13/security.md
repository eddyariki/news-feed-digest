# Security Digest — 2026-03-13

A busy day across the threat landscape: active zero-day exploitation in Chrome, nine newly disclosed Linux kernel privilege-escalation flaws, a China-linked espionage campaign targeting militaries, and a sweeping INTERPOL operation that sinkholed 45,000 malicious IPs.

---

## AI Security Research

**[Patch Me If You Can: AI Codemods for Secure-by-Default Android Apps](https://engineering.fb.com/2026/03/13/android/ai-codemods-secure-by-default-android-apps-meta-tech-podcast/)**
*Engineering at Meta*
Meta describes using AI-powered code modification tools to automatically remediate entire classes of security vulnerabilities across millions of lines of Android code. The approach applies secure-by-default API migrations at scale without requiring individual engineer intervention.

**[Will AI Save Consumers From Smartphone-Based Phishing Attacks?](https://www.darkreading.com/mobile-security/will-ai-save-consumers-smartphone-phishing-attacks)**
*Dark Reading — Hollie Hennessy, Aaron West*
New Omdia research finds that sophisticated phishing campaigns are bypassing on-device protections with increasing frequency, raising the question of whether AI-driven defenses can keep pace with attackers who are themselves leveraging AI to craft more convincing lures.

---

## Vulnerabilities & Exploits

**[Google Fixes Two Chrome Zero-Days Exploited in the Wild Affecting Skia and V8](https://thehackernews.com/2026/03/google-fixes-two-chrome-zero-days.html)**
*The Hacker News*
Google pushed emergency updates for CVE-2026-3909 (out-of-bounds write in Skia, CVSS 8.8) and a second high-severity V8 flaw, both actively exploited in the wild. Users should update Chrome immediately.

**[Nine CrackArmor Flaws in Linux AppArmor Enable Root Escalation, Bypass Container Isolation](https://thehackernews.com/2026/03/nine-crackarmor-flaws-in-linux-apparmor.html)**
*The Hacker News*
Qualys TRU disclosed nine "confused deputy" vulnerabilities in the Linux kernel's AppArmor module (collectively dubbed CrackArmor) that allow unprivileged users to escalate to root and escape container boundaries.

**[Chinese Hackers Target Southeast Asian Militaries with AppleChris and MemFun Malware](https://thehackernews.com/2026/03/chinese-hackers-target-southeast-asian.html)**
*The Hacker News*
Palo Alto Networks Unit 42 (tracking the cluster as CL-STA-1087) has detailed a sustained Chinese state-sponsored espionage campaign against Southeast Asian military organizations, active since at least 2020, deploying novel malware families AppleChris and MemFun.

**[Storm-2561 Spreads Trojan VPN Clients via SEO Poisoning to Steal Credentials](https://thehackernews.com/2026/03/storm-2561-spreads-trojan-vpn-clients.html)**
*The Hacker News*
Microsoft detailed a credential-theft campaign in which threat actor Storm-2561 uses SEO poisoning to redirect enterprise users searching for Ivanti, Cisco, and Fortinet VPN software to digitally signed trojan installers that harvest VPN credentials.

**[INTERPOL Dismantles 45,000 Malicious IPs, Arrests 94 in Global Cybercrime Crackdown](https://thehackernews.com/2026/03/interpol-dismantles-45000-malicious-ips.html)**
*The Hacker News*
Operation Synergia III, spanning 72 countries, sinkholed 45,000 IP addresses and servers tied to phishing, malware, and ransomware campaigns, resulting in 94 arrests and significant disruption to global cybercriminal infrastructure.

**[Fake PoCs, Misunderstood Risks Cause Cisco SD-WAN Chaos](https://www.darkreading.com/vulnerabilities-threats/fake-pocs-risks-cisco-sd-wan)**
*Dark Reading — Nate Nelson*
Buzz around Cisco's latest SD-WAN vulnerabilities has produced a wave of fraudulent proof-of-concept exploits and widespread misunderstanding of actual risk, leaving defenders struggling to prioritize real remediation.

**[FBI Seeks Victims of Steam Games Used to Spread Malware](https://www.bleepingcomputer.com/news/security/fbi-seeks-victims-of-steam-games-used-to-spread-malware/)**
*BleepingComputer — Lawrence Abrams*
The FBI is requesting victims to come forward as part of an investigation into eight malicious games uploaded to Steam that were used as a delivery vector for malware.

**[Real-Time Banking Trojan Strikes Brazil's Pix Users](https://www.darkreading.com/application-security/real-time-banking-trojan-strikes-brazils-pix-users)**
*Dark Reading — Alexander Culafi*
A new banking Trojan campaign targeting Brazil's Pix instant payment system combines automated malware with a live human operator who intervenes in real time at the moment of transaction to maximize theft.

**[Poland's Nuclear Research Centre Targeted by Cyberattack](https://www.bleepingcomputer.com/news/security/polands-nuclear-research-centre-targeted-by-cyberattack/)**
*BleepingComputer — Bill Toulas*
Poland's National Centre for Nuclear Research (NCBJ) confirmed its IT infrastructure was targeted by hackers; the attack was detected and contained before causing any operational impact.

**[Starbucks Discloses Data Breach Affecting Hundreds of Employees](https://www.bleepingcomputer.com/news/security/starbucks-discloses-data-breach-affecting-hundreds-of-employees/)**
*BleepingComputer — Sergiu Gatlan*
Starbucks disclosed unauthorized access to Partner Central accounts affecting hundreds of employees, continuing a trend of credential-based breaches at large consumer brands.

**[Most Google Cloud Attacks Start With Bug Exploitation](https://www.darkreading.com/cloud-security/google-cloud-attacks-bug-exploitation)**
*Dark Reading — Robert Lemos*
New research shows vulnerability exploitation — not stolen credentials or misconfigurations — is now the top initial access vector for cloud compromises, as AI accelerates attacker ability to find and weaponize bugs faster than patching cycles allow.

---

## Policy & Compliance

**[Meta to Shut Down Instagram End-to-End Encrypted Chat Support Starting May 2026](https://thehackernews.com/2026/03/meta-to-shut-down-instagram-end-to-end.html)**
*The Hacker News*
Meta announced it will discontinue E2EE chat support on Instagram after May 8, 2026, raising concerns among privacy advocates about the rollback of a security feature that had only recently been expanded.

**[The $32B Acquisition That One VC Is Calling the 'Deal of the Decade'](https://techcrunch.com/video/the-32b-acquisition-that-one-vc-is-calling-the-deal-of-the-decade/)**
*TechCrunch AI — Theresa Loconsolo*
Google's $32 billion acquisition of cybersecurity startup Wiz — the largest venture-backed acquisition in history — closed after navigating antitrust review on both sides of the Atlantic, signaling massive consolidation in the cloud security market.
