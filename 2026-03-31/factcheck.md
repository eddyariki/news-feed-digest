## Fact-Check Report — 2026-03-31

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Mistral AI Borrows $830M to Build Paris Data Center]** — Both the Highlights section and the Europe section title the article using "Build" ("Borrows $830M to Build Paris Data Center" / "Borrows $830M to Build Data Center Near Paris"). The source article (The Decoder) is titled "Mistral AI borrows 830 million dollars to **operate** a new data center near Paris." Mistral is borrowing to run/operate a facility, not to construct one from scratch. **Correction:** "Build" replaced with "Operate" in both locations.

**[Fortinet BIG-IP Vulnerability Reclassified as RCE, Under Exploitation]** — The news digest summary adds "attackers are deploying webshells on unpatched devices." This detail does not appear in the linked Dark Reading source summary, which only states "new information has revealed the bug is actually much more dangerous." The webshell detail is sourced from a separate BleepingComputer article about F5 BIG-IP (which covers the same CVE from a different angle). **Correction:** Webshell detail removed; summary updated to reflect the Dark Reading source.

**[Apple Adds macOS Terminal Warning to Block ClickFix Attacks]** — The digest summary says the feature "alerts users before potentially harmful commands are pasted into Terminal." The BleepingComputer source states it "blocks pasting and executing potentially harmful commands in Terminal and alerts users to possible risks." The blocking functionality — central to the feature — is omitted. **Correction:** Summary updated to include the blocking action.

**[CANGuard: A Spatio-Temporal CNN-GRU-Attention Architecture for Vehicle Network Intrusion Detection]** — Title in the Research Papers section drops "Hybrid" from the architecture name and rewrites the subtitle. Source title is "CANGuard: A Spatio-Temporal CNN-GRU-Attention **Hybrid** Architecture for Intrusion Detection **in In-Vehicle CAN Networks**." **Correction:** Full source title restored.

**[SkinGPT-X: A Self-Evolving Collaborative Multi-Agent System for Dermatological Diagnosis]** — Title in the Research Papers section drops "Transparent and Trustworthy." Source title is "SkinGPT-X: A Self-Evolving Collaborative Multi-Agent System for **Transparent and Trustworthy** Dermatological Diagnosis." These are key design properties of the system. **Correction:** Full source title restored.

**[The Accountability Paradox: How Platform API Restrictions Undermine AI Transparency]** — Title in the Research Papers section drops "Mandates." Source title is "The Accountability Paradox: How Platform API Restrictions Undermine AI Transparency **Mandates**." The paper is specifically about DSA transparency mandates, not transparency in general. **Correction:** "Mandates" restored.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All titles and ArXiv URLs in papers-2026-03-31.md match the digest and the source data. Author attributions and abstract-level claims are consistent with the source abstracts available in the feed. Note: papers.md correctly carries the full titles for SkinGPT-X and The Accountability Paradox (with "Transparent and Trustworthy" and "Mandates" respectively), unlike the digest's Research Papers section.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Source attribution throughout]** — The security digest consistently uses "Bleeping Computer" (two words) for articles from that outlet. The publication's correct name is "BleepingComputer" (one word), matching both the source feed metadata and the usage in the news digest. **Correction:** All instances updated to "BleepingComputer."

---

### Overall Summary

The three output artifacts are largely accurate and well-sourced. The most substantive error is the "Build" vs. "Operate" mischaracterization of Mistral's financing (Mistral is borrowing to run a data center, not construct one), which appears in both the Highlights and Europe sections of the digest. The news digest summary for the Fortinet BIG-IP article introduces a webshell detail sourced from a separate BleepingComputer/F5 article rather than the linked Dark Reading piece. The Apple Terminal summary understates a key behaviour (blocking, not just alerting). Three research paper titles in the digest's Research Papers section are truncated in ways that drop meaningful terms ("Hybrid," "Transparent and Trustworthy," "Mandates"); the papers.md summaries correctly preserve the full titles. The security digest is clean on facts but uses a spaced variant of the "BleepingComputer" outlet name throughout. All corrections have been applied inline to the respective files.
