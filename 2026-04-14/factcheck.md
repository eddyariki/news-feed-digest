## Fact-Check Report — 2026-04-14

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[AI-Induced Human Responsibility in AI-Human Teams]** — The brief digest description says people "consistently under-attribute moral responsibility to themselves when AI is involved." The source paper (arXiv:2604.08866) is titled *AI-Induced Human Responsibility (AIHR)*, and the detailed paper summaries file (papers-2026-04-14.md) — drawn from the same abstract — states the opposite: participants attributed *more* responsibility to human decision-makers when paired with AI than when paired with another human (a finding the paper explicitly frames as counter to "responsibility diffusion" intuitions). The direction of the effect is inverted in the digest brief description.

*Note: Per task scope, brief descriptions of research papers in the digest are not formally required to be checked (only titles and ArXiv URLs are). All 21 research paper titles and URLs were verified against the JSON and are correct. All 33 news article titles, source attributions, URLs, and summaries were verified and are accurate.*

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles and ArXiv URLs match their entries in the digest. Author lists match the JSON. Summaries and Key Takeaways are consistent with the abstracts visible in the source data. Specific quantitative claims (76.1%/81.8% ASR for Re-Mask; 10-point AIHR effect; 41 models in PilotBench; 11–14× precision gap) cannot be verified from truncated abstracts but are plausible and internally coherent.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Your MTTD Looks Great. Your Post-Alert Gap Doesn't]** — The security digest summary states: "Palo Alto's Wendi Whitmore warns similar capabilities are weeks away from broad proliferation." The source JSON reads: "Palo Alto Networks' Wendi Whitmore warned that similar capabilities are weeks *or months* from proliferation." The omission of "or months" makes the timeline sound more imminent than the source states.

*All other articles in the security digest — including all news items and all arXiv paper entries — were verified against the JSON for title, URL, source attribution, and summary fidelity. No further issues found.*

---

### Overall Summary
Both the news digest and security digest are largely accurate: titles, URLs, source attributions, and summaries are faithful to their source data across more than 50 individual articles and papers. Two corrections are required. First, the news digest's one-line description of arXiv:2604.08866 inverts the paper's central finding: the paper demonstrates that AI involvement *increases* perceived human moral responsibility (counter to responsibility-diffusion expectations), but the digest says people "under-attribute" responsibility when AI is involved. Second, the security digest's summary of the MTTD article (The Hacker News) truncates Wendi Whitmore's quoted timeline from "weeks or months" to "weeks," overstating imminence. Both corrections have been applied inline to the respective files.
