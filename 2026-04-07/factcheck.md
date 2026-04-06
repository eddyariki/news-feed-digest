## Fact-Check Report — 2026-04-07

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Iran Threatens Stargate AI Data Centers]** — The Highlights summary attributes details to the TechCrunch URL that actually come from two other articles. The TechCrunch source (`iran-threatens-stargate-ai-data-centers/`) only states "Iran said it will target U.S.-linked data centers with new missile strikes, as the war between the U.S. and Iran escalates." The IRGC-published-video detail and "OpenAI's planned Abu Dhabi Stargate data center" specifics both originate from *The Verge* article (`theverge.com/…/907427`). The "Iranian strikes already taking AWS Dubai and Bahrain regions fully offline" claim originates from the Gigazine article (`gigazine.net/news/20260406-iran-strike-aws/`), which is correctly cited separately in the Japan section. Correction: revise the Highlights summary to reflect only what the TechCrunch article reports; the IRGC-video and AWS-offline details should not be attributed to TechCrunch.

**[Axios Attack Shows Social Engineering Is Industrialized]** — Source title in the JSON is "Axios Attack Shows Social Complex Engineering Is Industrialized"; the URL slug confirms "complex-social-engineering". The word "Complex" is dropped in the digest title. Correction: title should read "Axios Attack Shows Complex Social Engineering Is Industrialized".

**[OpenAI Reveals 600,000 Weekly Health Queries from Hospital Deserts]** — Minor: the digest says "with the majority coming from medically underserved areas." The source title says "600,000 weekly health queries from hospital deserts" while the summary separately states ChatGPT gets "millions of health queries per week." If the total is millions, 600K from hospital deserts is not a majority; the source summary uses "especially from," not "majority." This is a low-severity overstatement, noted for awareness.

---

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

All 12 paper titles and ArXiv URLs match the digest and source data exactly. Author names match the JSON. Abstracts in the JSON are truncated, so specific numeric claims in the summaries (e.g., "16 state-of-the-art LLMs" in the fraud cover-up paper; "73.63% attack success rate" in AgentHazard; "56.3% / 23.0%" in Agentic-MME; specific accuracy figures in DeltaLogic) cannot be verified from the available data. No obviously fabricated or contradicted claims were identified; the summaries are substantively consistent with the available abstract text. These statistics are noted as unverifiable from truncated JSON abstracts alone.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[AgenticRed: Evolving Agentic Systems for Red-Teaming]** — **URL is wrong.** The digest links to `https://arxiv.org/abs/2604.03201`, which resolves to a completely unrelated paper: "Coupled Control, Structured Memory, and Verifiable Action in Agentic AI (SCRAT — Stochastic Control with Retrieval and Auditable Trajectories)." The correct ArXiv URL for AgenticRed is `https://arxiv.org/abs/2601.13518`. Correction: fix the URL.

**[AI Offensive Cyber Capabilities Are Doubling Every Six Months, Safety Researcher Says]** — Source title is "AI offensive cyber capabilities are doubling every six months, safety researchers find" (plural "researchers"). The digest renders this as "Safety Researcher Says" (singular). Correction: title should use plural "Researchers" and "find."

**[Axios Attack Shows Social Engineering Is Industrialized]** — Same title-truncation issue as in Part 1: "Complex" is dropped. Correction: "Axios Attack Shows Complex Social Engineering Is Industrialized."

---

### Overall Summary

Both digests and the paper summaries are largely accurate. The most significant error is a wrong ArXiv URL for AgenticRed in the security digest, which points to an entirely different paper. The Iran Highlights summary in the main digest blends details from three separate sources (TechCrunch, The Verge, Gigazine) under a single TechCrunch attribution, which misrepresents the TechCrunch article. Several article titles drop the word "Complex" from the Axios story. All paper titles and URLs checked out; specific numeric statistics in paper summaries could not be confirmed from truncated abstracts but no clear contradictions were found. Three inline corrections are applied below.
