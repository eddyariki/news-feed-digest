## Fact-Check Report — 2026-03-25

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Popular AI proxy LiteLLM backdoored with Kubernetes-spreading malware]** — Title does not match source. Source title is "Popular AI proxy LiteLLM got hacked with malware that spreads through Kubernetes clusters" (The Decoder). "Backdoored" and "Kubernetes-spreading malware" are significant rewrites; corrected to source title.

**[TeamPCP Backdoors LiteLLM Versions 1.82.7–1.82.8]** — Title truncated. Source title is "TeamPCP Backdoors LiteLLM Versions 1.82.7–1.82.8 Likely via Trivy CI/CD Compromise". The second clause ("Likely via Trivy CI/CD Compromise") was dropped; corrected to full title.

**[Databricks buys two startups to underpin its new AI security product]** — Title tense mismatch. Source title reads "Databricks bought two startups…" (past tense). The digest used present tense "buys", likely derived from the URL slug rather than the article title; corrected.

**[Arm's first CPU ever will plug into Meta's AI datacenters later this year]** — Summary adds unsupported claim. The USA-section summary states "with Meta as its **first and exclusive** customer at launch." Source says only "the first customer." The word "exclusive" is not in the source and has been removed.

**[Are we ready to hand AI agents the keys?]** (MIT Technology Review) — Title drops "Exclusive eBook:" prefix from the source title "Exclusive eBook: Are we ready to hand AI agents the keys?" Minor cosmetic omission; no factual error in the summary; no correction applied.

**[From Chile to the Philippines, meet the people pushing back on AI]** (Rest of World) — Article URL (`restofworld.org/2026/ai-pushback-chile-mexico-kenya-philippines/`) is not present in `latest.json`; title, attribution, and summary cannot be verified against source data. No correction possible; flagged for manual review.

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

**[MARCUS: An agentic, multimodal vision-language model for cardiac diagnosis and management]** — Author name misspelled. The author list includes "Li Fe-Fei"; the correct name is "Li Fei-Fei" (Fei-Fei Li, Stanford). Corrected in `papers-2026-03-25.md`.

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[U.S. Sentences Russian Hacker to 6.75 Years for Role in $9M Ransomware Damage]** — URL error. The security digest links to `https://thehackernews.com/2026/03/us-sentences-russian-hacker-to-675-years` (missing `.html`, slug differs). The correct URL from `latest.json` is `https://thehackernews.com/2026/03/us-sentences-russian-hacker-to-675.html`; corrected.

### Overall Summary
All three artifacts are substantially accurate: outlet attributions, URLs, and summaries are correct across the vast majority of entries. Six issues were identified in total. The most consequential is the Arm/Meta summary adding the unsupported word "exclusive" (not in the source); two further issues are a significant title rewrite for The Decoder's LiteLLM article and a truncated THN title that drops meaningful attribution context. A Databricks tense mismatch and an author name misspelling (Fei-Fei Li in the MARCUS paper) are minor but factually wrong. The security digest contains one broken URL for the Russian hacker sentencing article. The Rest of World article was not present in `latest.json` and could not be verified. All verifiable errors have been corrected inline in the respective files.
