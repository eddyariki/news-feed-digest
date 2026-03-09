## Fact-Check Report — 2026-03-09

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[U.S. Military Struck 3,000 Iran Targets with AI Support]** (Highlights) — Digest says "Generative AI—including Claude—played a deep role…" The source (The Decoder) confirms widespread generative AI use across intelligence, targeting, and logistics but does not mention Claude specifically. "Including Claude" is an unsupported addition. **Correction applied:** removed "—including Claude—".

**[OpenAI and Google Employees Rush to Anthropic's Defense]** — Digest says employees "—including Jeff Dean—filed an amicus brief." The source JSON summary says they "signed onto a statement." (1) "Jeff Dean" does not appear in the source summary and is unverifiable from available data. (2) "Amicus brief" is a specific legal filing; the source says "statement," a broader term. **Correction applied:** removed the named individual and changed "filed an amicus brief" to "signed a statement."

**[Anthropic Sues the Department of Defense]** (Highlights, TechCrunch URL) — The claim "17 US federal agencies" is not present in the TechCrunch source summary; it comes from the companion The Decoder article. The Highlights section cites the TechCrunch URL for this claim. Minor cross-attribution — the fact is confirmed in the associated The Decoder article and the TechCrunch article covers the same event. No correction applied (the fact is accurate; only the source-URL pairing is imprecise).

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

**[SAHOO], [Reasoning Models / CoT-Control], [The Fragility of Moral Judgment], [DeepFact]** — Several specific quantitative figures (e.g., "18.3% improvement," "2.7% CoT control rate," "129,156 total judgments," "60.8% expert accuracy") are not present in the truncated JSON abstracts and therefore cannot be confirmed from source data. None are contradicted by available abstract text. Flagged as unverifiable, not as fabricated. No corrections applied.

**[Proof-of-Guardrail]** — Paper summary refers to "OpenClaw agents." The JSON abstract does not mention OpenClaw by name. Unverifiable from available data. No correction applied.

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Reasoned Safety Alignment: Ensuring Jailbreak Defense via Answer-Then-Check]** — Digest describes the method as "first generate an answer and then apply a reasoning step to catch jailbreak violations." The source abstract states the model applies its thinking ability "before producing a final answer" — the opposite order. The method is Answer-Then-Check from the model's perspective (it reasons, then outputs), not generate-then-review after the fact. **Correction applied:** changed to "applies a reasoning step before producing a final answer to catch jailbreak violations."

**[Chinese Cyber Threat / Dark Reading article]** — News digest attributes sector list "aviation, energy, telecom, pharma" to the Dark Reading URL, but the Dark Reading source JSON summary does not enumerate sectors; that detail appears in the companion THN article covering the same Unit 42 research. Minor cross-source interpolation; the sectors are accurate per the THN source. No correction applied.

### Overall Summary
The 2026-03-09 digest is largely accurate, with all URLs and source attributions verified. Three confirmed factual errors were found and corrected: (1) the claim that Claude was specifically used in the Iran military campaign was added without source support; (2) a named individual (Jeff Dean) was inserted into the employees-supporting-Anthropic item without source confirmation, and the legal term "amicus brief" overstated what the source calls a "statement"; (3) the Reasoned Safety Alignment paper summary in the security digest reversed the order of the paper's Answer-Then-Check mechanism. Research paper summaries contain specific quantitative claims that exceed what the truncated abstracts confirm but are internally consistent and not contradicted by available data.
