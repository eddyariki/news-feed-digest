## Fact-Check Report — 2026-03-02

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Apple Might Use Google Servers to Store Data for Its Upgraded AI Siri]** — URL mismatch. The digest links to `https://www.theverge.com/tech/887802/apple-ai-siri-google-servers-data` (with trailing `-data`), but the source JSON records the canonical URL as `https://www.theverge.com/tech/887802/apple-ai-siri-google-servers`. The extra `-data` segment is not present in the source and produces a different (potentially broken) link. **Correction:** remove `-data` from the URL.

All other articles checked:
- Titles match or faithfully paraphrase source titles (minor title-casing differences are acceptable).
- Source attributions (The Hacker News, The Verge, The Decoder, TechCrunch, MIT Technology Review, Schneier on Security, Rest of World, The Japan Times, The Japan News, ITmedia AI+, Gigazine) are correct.
- All other URLs match the JSON source (tracking parameters stripped from Rest of World URL — acceptable).
- Summaries stay within facts present in the source title/summary without adding invented details.
- ArXiv paper titles and URLs in the Research Papers section match the source JSON.

---

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Memory Caching: RNNs with Growing Memory]** — Title formatting error in the section header. The papers file renders the title as "**MemoryCaching: RNNs with Growing Memory**" (no space between "Memory" and "Caching"), but the PDF metadata gives the correct title as "**Memory Caching: RNNs with Growing Memory**" (with a space). The body text of the summary and the digest both use the correct form. **Correction:** add the missing space in the section heading.

All other papers checked (15 total):
- Titles match PDF metadata exactly (minor case variants, e.g. "LLM-based" vs "LLM-Based", are not factual errors).
- Authors verified against PDF metadata — all match.
- ArXiv URLs verified against source JSON — all match.
- Summaries and Key Takeaways checked against source abstracts; no invented claims identified.
- "UK AI Security Institute, London, UK" affiliation for the Ask Don't Tell paper confirmed directly from PDF body text.
- CUDA Agent model comparisons (Claude Opus 4.5, Gemini 3 Pro) confirmed via PDF citation keys and URL links to respective model cards.

---

### Overall Summary
Both artifacts are largely accurate and well-sourced. Two minor issues were found: a URL in the news digest for The Verge's Apple/Siri article has a spurious `-data` suffix not present in the source feed, and the Memory Caching paper's section heading in the papers file is missing a space in the title. Neither issue affects the factual substance of the coverage. Both corrections have been applied inline.
