## Fact-Check Report — 2026-05-20

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
- **[Mythos breaks Apple's MIE in 5 days]** (AI Security entry) — The digest reads "defeating Apple's five-year-old Memory Integrity Enforcement defense." The ITmedia source describes MIE as "5年がかりで開発した最先端のセキュリティ対策" — i.e., a cutting-edge measure that Apple **spent five years developing**, not one that is five years old. MIE is a new (2025-era) Apple feature. Correction applied: rephrased to "Apple's flagship Memory Integrity Enforcement defense, which Apple spent five years developing."
- **[SMBC, Fujitsu, and SoftBank form medical AI alliance]** (Japan entry) — The linked Japan Times article is titled "SMFG, Fujitsu and SoftBank forming medical alliance to help contain costs." The digest substitutes SMBC (Sumitomo Mitsui Banking Corp, the bank subsidiary) for SMFG (the parent financial holding group named in the source). Correction applied: title changed to "SMFG, Fujitsu, and SoftBank form medical AI alliance." (Note: the immediately following Japanese-language ITmedia entry legitimately uses SMBC, matching its own source.)

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles, ArXiv URLs, and author lists match the source JSON exactly. Summaries and key takeaways stay within plausible abstract claims (specific numbers like 0.878 mean AUC for the MDLM MIA paper, 28% / 3.8% for CHI-Bench, 93.8% ASR for ShadowMerge, 74.4% / 70.6% for Lying with Truths, 79.1% / 67.7% for the legal precedent paper, 0.00 → 0.69 F1 for VLM-AutoDrive, 84.2 / 56.9 GuardedJoint for Trust No Tool) are internally consistent and not flagged as obvious fabrications. Minor abbreviations in digest titles (LLM, RAG, VLMs) are faithful paraphrases of the longer source titles.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None. All 24 cited articles map cleanly to entries in latest.json: titles, outlet attributions, and URLs match (the Dark Reading "CISA Exposes Secrets, Credentials in 'Private' Repo" used here is a distinct source from the Ars Technica article cited in the news digest, but both exist in the JSON and cover the same incident). The seven ArXiv cs.CR papers verify against source titles and IDs. Summaries stay within facts present in the source titles/summaries.

### Overall Summary
The 2026-05-20 artifacts are largely accurate. Two factual issues were found in the news digest: a misstatement of Apple's MIE as "five-year-old" (it is the product of five years of development, per the Japanese source) and a substitution of "SMBC" for "SMFG" in a Japan Times headline. Both have been corrected inline. The research-paper digest entries, the standalone papers-2026-05-20.md summaries, and the security-2026-05-20.md digest all check out against the source JSON without further issue.
