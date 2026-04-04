## Fact-Check Report — 2026-04-04

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[LinkedIn Secretly Scans for 6,000+ Chrome Extensions, Collects Data]** — The digest summary claims LinkedIn is "sending data to third-party security firms." The source summary (BleepingComputer) says only that LinkedIn "collect[s] device data" without disclosure; no third-party security firms are mentioned. The phrase was not supported by the source. **Correction:** Removed the unsupported "third-party security firms" claim from the summary.

**[Microsoft Commits $10 Billion to Japan's AI Infrastructure (2026–2029)]** (Japan section, Japan Times URL) — The Japan Times source title reads "Microsoft *drafts* $10 billion investment plan in AI-hungry Japan," and the source summary describes Microsoft as "battling" rivals for dominance, not formally committing. The digest's use of "Commits" overstates the Japan Times framing. Note: the separate Highlights entry uses The Decoder URL (which does describe a confirmed investment/commitment) and is correct. The Japan-section entry, citing the Japan Times, should reflect the "plans/drafts" framing. **Correction:** Title changed from "Commits" to "Plans."

**[Disentangling Prompt Risk Factors for Hallucinations in Mental Health LLM Responses]** (Research Papers section) — Source title is "Disentangling Prompt Element Level Risk Factors for Hallucinations **and Omissions** in Mental Health LLM Responses." The digest title omits "and Omissions," which is a key finding of the paper (omissions rate 13.2% vs. hallucinations 6.5%). **Correction:** Added "and Omissions" to the digest paper title.

---

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Safety, Security, and Cognitive Risks in World Models]** — papers-2026-04-04.md lists `Tags: cs.CR`; source (latest.json) shows `ArXiv cs.LG`. **Correction:** Tag updated to `cs.LG`.

**[De Jure: Iterative LLM Self-Refinement for Structured Extraction of Regulatory Rules]** — papers-2026-04-04.md lists `Tags: cs.AI`; source shows `ArXiv cs.LG`. **Correction:** Tag updated to `cs.LG`.

**[LiveMathematicianBench: A Live Benchmark for Mathematician-Level Reasoning with Proof Sketches]** — (a) papers-2026-04-04.md lists `Tags: cs.CL`; source shows `ArXiv cs.LG`. **Correction:** Tag updated to `cs.LG`. (b) Key Takeaway 1 reads "Top frontier models score below 20% random baseline when evaluated with substitution-resistant probes" — the summary's own data contradicts this: Gemini-3.1-pro-preview drops to 17.6% (below 20% baseline) but GPT-5.4 achieves 30.6% (above baseline) in the same mode. The plural "models" overgeneralizes. **Correction:** Key takeaway revised to name Gemini specifically.

---

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None. All article titles and ArXiv paper titles exactly match their source entries in latest.json. Source attributions and URLs are correct throughout. Summaries stay within the facts present in the source summaries.

---

### Overall Summary
The three artifacts are largely accurate. The most significant factual issue is in the news digest's LinkedIn summary, which adds an unsupported "third-party security firms" detail absent from the source. A second issue is the Japan-section Microsoft entry using "Commits" against a Japan Times source that explicitly says "drafts." A paper-title truncation in the digest omits the significant finding of "omissions" from the mental-health LLM paper title. In the paper summaries file, three ArXiv primary-category tags are wrong (World Models, De Jure, and LiveMathematicianBench should all be cs.LG), and one Key Takeaway overgeneralizes a finding that applies specifically to Gemini. The security digest is clean.
