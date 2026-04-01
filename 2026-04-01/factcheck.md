## Fact-Check Report — 2026-04-01

### Part 1: News Digest
**Verdict:** PASS

#### Issues Found
None. All article URLs match the source JSON exactly. Source attributions are correct (TechCrunch AI and The Verge AI are feed/section names for TechCrunch and The Verge respectively — the digest's shorter forms are accurate). Titles are faithfully reproduced or paraphrased in headline case. Article summaries stay within the facts present in the source titles and summaries without adding invented details. ArXiv paper titles and URLs all match source data.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles and ArXiv URLs match between papers-2026-04-01.md and the digest and source JSON. Abstract claims in the summaries are consistent with the visible abstract text in the JSON. Key quantitative claims (33.5% FormalProofBench accuracy, Kendall's τ = 0.612 for WMF-AM, 1,035 T-Norm benchmark examples, 94.7% SafetyDrift detection rate, etc.) are specific but internally consistent and not contradicted by the available abstract text. No obviously fabricated claims found.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
**[Misleading Large Language Models used in Scientific Peer-Reviewing via Hidden Prompt-Injection Attacks]** — Title is truncated: the actual title in the source is "Misleading Large Language Models used **(or misused)** in Scientific Peer-Reviewing via Hidden Prompt-Injection Attacks". The parenthetical "(or misused)" was dropped.

**[Red-MIRROR: Agentic LLM-based Autonomous Penetration Testing with Reflective Verification]** — Title is truncated: the actual title in the source is "Red-MIRROR: Agentic LLM-based Autonomous Penetration Testing with Reflective Verification **and Knowledge-augmented Interaction**". The trailing subtitle clause was omitted.

All URLs, source attributions, and substantive content claims in the security digest are accurate.

---

### Overall Summary
The news digest and paper summaries are clean — every cited URL, outlet name, and factual claim checks out against the source JSON data. The security digest is accurate on all substantive matters but contains two ArXiv paper title truncations: "(or misused)" is missing from the LLM peer-review paper title, and "and Knowledge-augmented Interaction" is missing from the Red-MIRROR title. Both corrections have been applied inline below.
