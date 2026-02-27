## Fact-Check Report — 2026-02-27

### Part 1: News Digest

**Verdict:** FAIL

#### Issues Found

**[China used ChatGPT to target Japan's PM]** — The digest characterises the influence operation as "portraying PM Sanae Takaichi as illegitimate and **ultranationalist**." The Gigazine source (the only cited source with narrative detail on the content of the messaging) reads: "高市首相を正当性に欠く**軍国主義的**であるかのように吹聴していました" — i.e., "**militaristic**," not "ultranationalist." The two terms describe meaningfully different political characterisations. **Correction:** replace "ultranationalist" with "militaristic."

**[900+ FreePBX instances still compromised]** — The digest says "significant clusters in Germany and France." The source (The Hacker News) explicitly reports the geographic breakdown as: US 401, Brazil 51, Canada 43, Germany 40, France 36. The United States hosts the single largest cluster by a wide margin (roughly ten times Germany's or France's share) yet goes unmentioned. Singling out Germany and France without noting the dominant US concentration creates a misleading impression of where the exposure is concentrated. **Correction:** add that the US hosts the largest cluster (401 instances), with Germany (40) and France (36) among the smaller European concentrations.

---

### Part 2: Paper Summaries

**Verdict:** PASS WITH NOTES

#### Issues Found

**[General Agent Evaluation — backbone model name]** — The summary states "three backbone models (Claude Opus 4.5, **Gemini 3**, GPT 5.2)." The PDF (p. 5) specifies "GPT 5.2, Claude Opus 4.5, and **Gemini 3 Pro**." The model name is truncated. **Correction:** replace "Gemini 3" with "Gemini 3 Pro" in both the Summary and Key Takeaways sections.

**[A Decision-Theoretic Formalisation of Steganography — institutional affiliations]** — The summary states "This paper from Cambridge, MIT, UK AI Safety Institute, and Oxford." The PDF lists five affiliations: ¹University of Cambridge, ²Massachusetts Institute of Technology, ³UK AI Safety Institute, ⁴**AstraZeneca**, ⁵University of Oxford. Jim Weatherall (affiliation 4) is from AstraZeneca, which is omitted. **Correction:** add AstraZeneca to the institution list: "Cambridge, MIT, UK AI Safety Institute, AstraZeneca, and Oxford."

**[Mirroring the Mind — answer-inclusive error rate]** — The Key Takeaways state "A substantial fraction of LRM failures **(10–24%)** are answer-inclusive errors." Figure 2 in the PDF shows percentages of *all predictions*: MuSiQue 23.75 %, HotpotQA ~5.87 %, 2WikiMultiHopQA ~9.42 %. As fractions of *failures* specifically, those figures correspond to roughly 50–66 % (e.g., 23.75 / 36.12 ≈ 66 % for MuSiQue). The "10–24 %" range approximates the proportion of *all predictions* that are answer-inclusive, not the proportion of failures. Using "of failures" instead of "of all predictions" understates the finding by a factor of ~3–5×. **Correction:** change "A substantial fraction of LRM failures (10–24%) are answer-inclusive errors" to "Answer-inclusive errors account for roughly 6–24% of all predictions (representing ~50–66% of failures) across MuSiQue, HotpotQA, and 2WikiMultiHopQA."

---

### Overall Summary

The news digest is largely accurate in titles, source attributions, and URLs. Two factual errors were found: a mistranslation/mischaracterisation in the China/Takaichi influence-operation entry ("ultranationalist" for "militaristic") and a misleading geographic framing in the FreePBX item that omits the dominant US cluster. The paper summaries are generally faithful to the source PDFs in titles, authors, and key results. Three issues were identified: a truncated backbone-model name (Gemini 3 Pro rendered as Gemini 3), an omitted institutional affiliation (AstraZeneca) in the steganography paper, and a meaningful denominator error in the Mirroring the Mind summary where "10–24% of failures" should read "~6–24% of all predictions" (equivalently, ~50–66% of failures). All four corrections are applied below.
