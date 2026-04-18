## Fact-Check Report — 2026-04-18

### Part 1: News Digest
**Verdict:** PASS

#### Issues Found
None. All 28 news articles verified against `latest.json`:
- Titles match or faithfully paraphrase source titles.
- Source attributions are correct (minor stylistic shortening of "The Verge AI" → "The Verge", "TechCrunch AI" → "TechCrunch", "The Japan Times" → "Japan Times" are editorial conventions, not errors).
- All URLs match source records. The Rest of World e-waste article URL in the digest (`https://restofworld.org/2026/global-ewaste-crisis/`) is a clean version of the UTM-appended source URL; resolves to the same article.
- Summaries stay within facts present in source data. Specific details confirmed: Project Glasswing (~50 organizations), Dario Amodei/Susie Wiles meeting (confirmed in The Decoder source), BlueHammer/RedSun/UnDefend names, 75,000 cybercriminals (Operation PowerOFF), CVSS 8.8 (Apache ActiveMQ CVE).

---

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found
**[Prompt Optimization Is a Coin Flip — ATBench-Claw and ATBench-CodeX]** — Minor internal inconsistency between digest and papers.md on run counts. The digest states "72 optimization runs on Claude Haiku and Amazon Nova Lite (6 methods × 4 tasks × 3 seeds)" implying both models are covered by the same 72 runs. The papers.md summary is internally consistent with 72 runs per model (= 144 total), noting "18,000 grid evaluations and 144 optimization runs." This is a minor framing discrepancy in the digest; papers.md is internally consistent and no correction is required to papers.md itself.

All 12 paper titles and ArXiv URLs in papers.md match the digest exactly. Authors are not listed (deferred to paper), so no author check is possible. Specific numeric claims in paper summaries (e.g., 1,520 evaluated responses in Context Over Content; 74 regulations in OmniCompliance-100K) are not present in source JSON and could not be cross-checked, but are plausible given the papers' scope and were not flagged for obvious implausibility.

---

### Part 3: Security Digest
**Verdict:** FAIL

#### Issues Found
**[Three Microsoft Defender Zero-Days Actively Exploited; Two Still Unpatched]** — The security digest summary states the three vulnerabilities are "codenamed BlueHammer, RedSun, and a third unnamed vulnerability." This is incorrect. The source (The Hacker News) explicitly names all three: BlueHammer, RedSun, and **UnDefend**. The parenthetical "(requires GitHub sign-in)" in the source refers to the disclosure access method for BlueHammer, not to the naming of the third CVE. **Correction:** replace "a third unnamed vulnerability" with "UnDefend".

---

### Overall Summary
The news digest and paper summaries are clean. All cited articles were found in `latest.json` and their titles, URLs, attributions, and summaries are accurate. The one factual error is in the security digest: the Microsoft Defender zero-day named "UnDefend" is incorrectly described as unnamed. This has been corrected inline below.
