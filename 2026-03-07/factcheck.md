## Fact-Check Report — 2026-03-07

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Grammarly's 'expert review' is just missing the actual experts]** — The digest summary states the feature "relies on AI outputs rather than genuine expert input." The source JSON summary only says the feature "purports to improve users' writing with help from the world's great writers and thinkers — and some tech journalists, too." The specific claim that it substitutes AI-generated content for real experts is not stated in the source feed entry; it is an inference from the headline. The phrase "drawing scrutiny over misleading product framing" is also editorially added beyond the source. These additions are plausible given the article title but go beyond what the available source data supports.

All other articles: titles, URLs, source attributions (all correctly attributed to The Decoder or TechCrunch AI), and summaries check out against the JSON.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. The single paper cited ("Spilled Energy in Large Language Models," `https://arxiv.org/abs/2602.18671`) is consistent with the digest's reference to Sapienza University of Rome research surfaced via The Decoder article. Authors and abstract framing are plausible; no claims clearly absent from the described methodology are introduced. The ArXiv URL cannot be independently verified against the JSON (the feed only contains the news article URL), but no discrepancies are identifiable within the available data.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Anthropic Finds 22 Firefox Vulnerabilities Using Claude Opus 4.6 AI Model]** — The security digest (sourcing The Hacker News) reports 22 previously unknown Firefox vulnerabilities, 14 rated high severity, patched in Firefox 148. The corresponding article in `latest.json` (sourcing The Decoder) states Claude found "over 100 bugs in Firefox." These are two publications reporting on the same Anthropic/Mozilla research partnership with substantially different numbers. The discrepancy (22 vs. 100+) is unresolved — the 22 may refer to a confirmed exploitable subset while 100+ reflects total bugs identified, but neither source in the available data clarifies this. The security digest also specifies "Claude Opus 4.6" as the model used; this detail is absent from the `latest.json` source and cannot be verified against available data.

**[OpenAI Codex Security Scanned 1.2 Million Commits and Found 10,561 High-Severity Issues]**, **[Microsoft: Hackers Abusing AI at Every Stage of Cyberattacks]**, **[Termite Ransomware Breaches Linked to ClickFix CastleRAT Attacks]** — These three articles (sourced from The Hacker News and BleepingComputer) are not present in `latest.json`. They were drawn from external security publications outside the curated news feed and cannot be verified against available source data. No internal contradictions are apparent in the summaries themselves.

---

### Overall Summary
The news digest (Part 1) is largely accurate: all article titles, URLs, and source attributions match the JSON exactly, and summaries are faithful to source content. The one note is that the Grammarly summary introduces a specific characterization ("relies on AI outputs") not directly stated in the source feed entry — a plausible inference from the headline, but an addition beyond the available data. The paper summary (Part 2) is clean. The security digest (Part 3) has a material factual discrepancy: the Firefox vulnerability count differs significantly between the security digest source (22 bugs, via The Hacker News) and the news feed source (100+ bugs, via The Decoder), both reporting on the same event — this warrants caution. Three of the four security digest articles are sourced from publications outside the news feed and cannot be independently verified from `latest.json`; their content appears internally consistent but remains unconfirmed.
