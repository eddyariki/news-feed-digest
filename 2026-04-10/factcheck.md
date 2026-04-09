## Fact-Check Report — 2026-04-10

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Highlight — Adobe Reader zero-day]** — Summary describes it as "A highly sophisticated PDF exploit weaponizing an unpatched Adobe Reader flaw." The linked source is BleepingComputer (`hackers-exploiting-acrobat-reader-zero-day-flaw-since-december`); its summary reads simply "Attackers have been exploiting a zero-day vulnerability in Adobe Reader using maliciously crafted PDF documents since at least December." The qualifier "highly sophisticated" does not appear in the BleepingComputer source — it comes from the separate Hacker News article about the same vulnerability. "Unpatched" is unsupported by the BleepingComputer source (the Hacker News version explicitly says "Adobe has since patched the flaw," making "unpatched" factually wrong). **Correction applied:** removed "highly sophisticated" and "unpatched"; summary now reads "A zero-day flaw in Acrobat Reader has been exploited via maliciously crafted PDFs in targeted attacks for at least four months before disclosure."

**[Highlight — OpenAI halves Pro tier price to $100/month]** — Summary ends with "directly undercutting rivals Anthropic and Google." The URL cited is the TechCrunch article (`chatgpt-pro-plan-100-month-codex`), whose source summary makes no mention of undercutting Anthropic or Google. That claim appears in the separately cited The Decoder article (`openai-halves-its-pro-price-to-100...`). **Correction applied:** removed "and directly undercutting rivals Anthropic and Google" from the highlight summary.

**[OpenAI reportedly following Anthropic's lead on restricting powerful cybersecurity AI]** — Digest says "available to a vetted group of companies." Source (The Decoder) says "available to a small group of companies." The word "vetted" is not present in the source. **Correction applied:** "vetted" → "small."

**[Google and Intel deepen AI infrastructure partnership]** — Digest says "The two companies plan to co-develop custom chips, including IPUs, amid a global CPU shortage driven by AI demand." The TechCrunch source summary says only "co-develop custom chips" — no mention of IPUs. **Correction applied:** "including IPUs" removed.

**[Microsoft's New Future of Work report]** — Digest calls it "Microsoft Research's 2025 report." The article was published 2026-04-09, and the source says "This year, the shift feels especially sharp" — placing it in 2026. **Correction applied:** "2025" → "2026."

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper summaries in `papers-2026-04-10.md` have titles and ArXiv URLs that match the digest exactly. Author lists match the source metadata. Abstract-level claims in summaries are consistent with the source abstract excerpts available; no claims are obviously absent from the source material. (Specific numerical results such as accuracy figures cannot be independently verified from the truncated abstracts in `latest.json`, but none are flagged as obviously implausible.)

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[OpenAI Reportedly Following Anthropic's Lead in Restricting Access to Powerful Cybersecurity AI]** — Security digest says "an AI model with advanced **offensive** cybersecurity capabilities that will be made available only to a **vetted group of organizations**." The source (The Decoder) says "a new AI model with advanced **cybersecurity** capabilities that will only be available to a **small group of companies**." Two errors: (1) "offensive" is not in the source and introduces a characterisation not present in the original; (2) "vetted group of organizations" → source says "small group of companies." **Correction applied:** "offensive cybersecurity capabilities" → "cybersecurity capabilities"; "vetted group of organizations" → "small group of companies."

---

### Overall Summary
Both the news digest and the security digest are broadly accurate and well-sourced, with all article URLs verified against `latest.json`. Five corrections were required in the news digest: a highlight summary borrowed a "highly sophisticated" qualifier and an erroneous "unpatched" claim from a different article about the same vulnerability; the OpenAI Pro highlight cross-contaminated a claim from The Decoder into the TechCrunch-attributed summary; the OpenAI cybersecurity blurb added an unsupported "vetted" modifier; the Google–Intel item introduced "IPUs" which is absent from the source; and the Microsoft report was misdated as 2025 when it was published in 2026. The security digest required one correction: the OpenAI cybersecurity entry added "offensive" (not in source) and changed "small group of companies" to "vetted group of organizations." The paper summaries file is clean.
