# Security Digest — 2026-03-21

Today's threat landscape is dominated by critical RCE vulnerabilities under active exploitation, a second supply-chain compromise of the widely-used Trivy scanner, and coordinated law enforcement actions taking down major DDoS botnets and ransomware infrastructure.

---

## AI Security Research

**[The Importance of Behavioral Analytics in AI-Enabled Cyber Attacks](https://thehackernews.com/2026/03/the-importance-of-behavioral-analytics.html)**
*The Hacker News*

Cybercriminals are using AI to generate personalized phishing emails, deepfakes, and evasive malware that bypass legacy security models by impersonating normal user activity. The piece argues that behavioral analytics is now essential to detect threats that signature-based tools miss.

---

## Vulnerabilities & Exploits

**[Oracle pushes emergency fix for critical Identity Manager RCE flaw](https://www.bleepingcomputer.com/news/security/oracle-pushes-emergency-fix-for-critical-identity-manager-rce-flaw/)**
*BleepingComputer*

Oracle released an out-of-band patch for CVE-2026-21992, a critical unauthenticated remote code execution flaw in Identity Manager and Web Services Manager. Attackers can execute arbitrary code without authentication if either product is exposed to the internet.

**[Critical Langflow Flaw CVE-2026-33017 Triggers Attacks within 20 Hours of Disclosure](https://thehackernews.com/2026/03/critical-langflow-flaw-cve-2026-33017.html)**
*The Hacker News*

A CVSS 9.3 vulnerability in the Langflow AI workflow platform—missing authentication combined with code injection—was weaponized within 20 hours of public disclosure. The flaw allows unauthenticated remote code execution via the `/api/v1` endpoint.

**[Trivy Security Scanner GitHub Actions Breached, 75 Tags Hijacked to Steal CI/CD Secrets](https://thehackernews.com/2026/03/trivy-security-scanner-github-actions.html)**
*The Hacker News*

Aqua Security's Trivy was compromised a second time within a month, with attackers hijacking 75 GitHub Actions tags in `aquasecurity/trivy-action` and `aquasecurity/setup-trivy` to deliver malware that exfiltrated CI/CD secrets from pipelines.

**[Interlock Ransomware Targets Cisco Enterprise Firewalls](https://www.darkreading.com/threat-intelligence/interlock-ransomware-targets-cisco-enterprise-firewalls)**
*Dark Reading*

The Interlock double-extortion ransomware gang exploited a critical Cisco firewall vulnerability weeks before it was publicly disclosed. The group's server exposure also revealed systematic targeting of network backups as a core tactic.

**[Magento PolyShell Flaw Enables Unauthenticated Uploads, RCE and Account Takeover](https://thehackernews.com/2026/03/magento-polyshell-flaw-enables.html)**
*The Hacker News*

Sansec disclosed "PolyShell," a critical Magento REST API flaw allowing unauthenticated attackers to upload arbitrary executables disguised as images, achieving code execution and full account takeover. No active exploitation has been confirmed yet.

**[FBI links Signal phishing attacks to Russian intelligence services](https://www.bleepingcomputer.com/news/security/fbi-links-signal-phishing-attacks-to-russian-intelligence-services/)**
*BleepingComputer*

The FBI issued a PSA warning that Russian intelligence-linked actors are actively running phishing campaigns against Signal and WhatsApp users, having already compromised thousands of accounts. Targets include individuals of intelligence value to Russian state services.

**[Cyber OpSec Fail: Beast Gang Exposes Ransomware Server](https://www.darkreading.com/threat-intelligence/opsec-beast-gang-exposes-ransomware-server)**
*Dark Reading*

Files on a publicly exposed cloud server used by the Beast ransomware group revealed the gang's systematic, aggressive strategy of attacking network backups as a primary tactic to maximize extortion leverage.

**[International joint action disrupts world's largest DDoS botnets](https://www.bleepingcomputer.com/news/security/aisuru-kimwolf-jackskid-and-mossad-botnets-disrupted-in-joint-action/)**
*BleepingComputer*

US, German, and Canadian authorities took down the command-and-control infrastructure for the Aisuru, KimWolf, JackSkid, and Mossad botnets—collectively among the largest IoT-based DDoS networks in operation.

**[Musician admits to $10M streaming royalty fraud using AI bots](https://www.bleepingcomputer.com/news/security/musician-pleads-guilty-to-10m-streaming-fraud-powered-by-ai-bots/)**
*BleepingComputer*

North Carolina musician Michael Smith pleaded guilty to orchestrating a $10M streaming royalty fraud scheme using AI-generated music and bot networks to fake streams across Spotify, Apple Music, Amazon Music, and YouTube Music.

---

## Policy & Compliance

**[CISA orders feds to patch max-severity Cisco flaw by Sunday](https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-max-severity-cisco-flaw-by-sunday/)**
*BleepingComputer*

CISA issued an emergency directive requiring federal agencies to patch CVE-2026-20131, a maximum-severity vulnerability in Cisco Secure Firewall Management Center, by March 22. The urgency is underscored by Interlock ransomware's prior exploitation of Cisco firewall flaws.

**[Proton Mail Shared User Information with the Police](https://www.schneier.com/blog/archives/2026/03/proton-mail-shared-user-information-with-the-police.html)**
*Schneier on Security*

Proton Mail provided subscriber payment metadata to the Swiss government, which then forwarded it to the FBI. Bruce Schneier notes this is legal and expected behavior—even privacy-centric services can be compelled to share metadata under Swiss law.

**[Google Adds 24-Hour Wait for Unverified App Sideloading to Reduce Malware and Scams](https://thehackernews.com/2026/03/google-adds-24-hour-wait-for-unverified.html)**
*The Hacker News*

Google announced a mandatory 24-hour waiting period for Android apps sideloaded from unverified developers, part of a broader developer verification mandate aimed at slowing the distribution of malware and scam applications.
