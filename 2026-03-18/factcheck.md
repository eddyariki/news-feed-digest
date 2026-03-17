## Fact-Check Report — 2026-03-18

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Microsoft Restructures AI Division to Chase Superintelligence]** — Two summary lines use "AGI" where the source title and article body explicitly say "superintelligence" ("all the way up to superintelligence"). AGI and superintelligence are distinct concepts; the source is unambiguous.
- *Highlights section*: "all the way to AGI" → corrected to "all the way to superintelligence"
- *News / USA section*: "toward AGI" → corrected to "toward superintelligence"

**[Mistral Forge and Mistral Small 4 at GTC 2026 (Europe section)]** — Title is fabricated: the linked URL (`techcrunch.com/…/mistral-forge-nvidia-gtc-build-your-own-ai-enterprise/`) covers only Mistral Forge; Mistral Small 4 is a separate article from The Decoder, already listed in the USA section. The summary ("two significant products … a custom training platform and an upgraded compact model") introduces content from the second article that is not in the linked URL. Corrected to reflect the actual TechCrunch article only.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles and ArXiv URLs in `papers-2026-03-18.md` match the digest exactly. Summaries and Key Takeaways are internally consistent and stay within plausible abstract claims; no obviously invented specifics detected. (TheraAgent, 2603.13676, appears in the digest but was not selected for the summaries file — expected curation, not an error.)

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[AI Flaws in Amazon Bedrock, LangSmith, and SGLang Enable Data Exfiltration and RCE]** — URL truncated to domain only (`https://thehackernews.com`); correct URL verified from source JSON: `https://thehackernews.com/2026/03/ai-flaws-in-amazon-bedrock-langsmith.html`. Corrected.

**[New font-rendering trick hides malicious commands from AI tools]** — URL truncated to domain only (`https://www.bleepingcomputer.com`); correct URL verified from source JSON: `https://www.bleepingcomputer.com/news/security/new-font-rendering-trick-hides-malicious-commands-from-ai-tools/`. Corrected.

**[Europe sanctions Chinese and Iranian firms for cyberattacks]** — URL truncated to domain only (`https://www.bleepingcomputer.com`); correct URL verified from source JSON: `https://www.bleepingcomputer.com/news/security/europe-sanctions-chinese-and-iranian-firms-for-cyberattacks/`. Corrected.

**[AI is Everywhere, But CISOs are Still Securing It with Yesterday's Skills and Tools]** — URL truncated to domain only (`https://thehackernews.com`); correct URL verified from source JSON and news digest: `https://thehackernews.com/2026/03/ai-is-everywhere-but-cisos-are-still.html`. Corrected.

*Note: Additional articles — LeakNet Ransomware, Konni/EndRAT, CISA Wing FTP (CVE-2025-47813), South Korean Police cryptocurrency wallet, IP KVM vulnerabilities, Warlock Ransomware — also appear to carry truncated or domain-only URLs but could not be verified against source JSON because the source file (latest.json) was overwritten by a subsequent pipeline run before cross-checking was complete. These are flagged for manual review.*

---

### Overall Summary
Two factual errors were found and corrected in the news digest: a consistent substitution of "AGI" for "superintelligence" in the Microsoft restructuring story (two occurrences), and a fabricated composite title in the Europe section that conflated two separate Mistral articles under a single URL. The paper summaries are clean. The security digest is factually sound in its article descriptions but suffers from a systematic generation artifact where at least four non-ArXiv articles received truncated domain-only hyperlinks; all four confirmed cases were corrected using the full URLs verified from source data. Additional truncated URLs in the security digest remain flagged but unverifiable due to source file overwrite.
