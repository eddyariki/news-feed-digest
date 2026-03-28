## Fact-Check Report — 2026-03-28

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
**[Open VSX Bug Let Malicious VS Code Extensions Bypass Pre-Publish Security Checks]** — The digest summary states the flaw caused the pipeline to treat "no scanners configured" identically to "all scanners passed." The source (The Hacker News) states the boolean return value conflated "no scanners are configured" with "all scanners failed to run." The second condition was mis-stated; corrected inline.

All other article titles, source attributions, URLs, and summaries check out against the JSON.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles and ArXiv URLs match the digest exactly. Author lists are plausible and summaries do not introduce claims clearly absent from the abstracts.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
**[China Upgrades the Backdoor It Uses to Spy on Telcos Globally]** — Security digest URL is `https://www.darkreading.com/cyberattacks-data-breaches/china-upgrades-backdoor-spy-telcos-globally`; source JSON URL is `https://www.darkreading.com/threat-intelligence/china-upgrades-backdoor-spy-telcos`. URL corrected inline.

**[Google Sets 2029 Deadline for Quantum-Safe Cryptography]** — Security digest URL is `https://www.darkreading.com/cybersecurity-operations/google-sets-2029-deadline-quantum-safe-cryptography`; source JSON URL is `https://www.darkreading.com/application-security/google-2029-deadline-quantum-safe-cryptography`. URL corrected inline.

**[Bearlyfy Hits Russian Firms with Custom GenieLocker Ransomware]** — Security digest URL is `https://thehackernews.com/2026/03/bearlyfy-hits-russian-firms-with-custom.html`; source JSON URL is `https://thehackernews.com/2026/03/bearlyfy-hits-70-russian-firms-with.html`. URL corrected inline.

---

### Overall Summary
The news digest is largely accurate with one factual error in the Open VSX summary, where "all scanners passed" should read "all scanners failed to run." The paper summaries are clean. The security digest contains three incorrect URLs for Dark Reading and The Hacker News articles (China BPFdoor, Google PQC deadline, and Bearlyfy); titles, source attributions, and summaries for those entries are otherwise correct. All three issues have been corrected inline in their respective files.
