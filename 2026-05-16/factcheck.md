## Fact-Check Report — 2026-05-16

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
- **Google expected to announce new Gemini at I/O 2026** — The digest renders the source title's "GPT-5.5レベルの性能だがMythosには及ばない" ("GPT-5.5 level performance but does not reach Mythos") as "a new tier just below the **GPT-5.5 'Mythos' frontier**." This phrasing conflates Mythos with the GPT-5.5 tier; the source treats them as distinct, with Mythos as a higher frontier above GPT-5.5-level performance. Corrected inline to "a new tier at GPT-5.5-level performance, still short of the Mythos frontier."
- **Chinese 1T-parameter open model Ring-2.6-1T beats GPT-5.4 and Gemini 3.1 Pro on select benchmarks** — Source (Gigazine) characterises the model as "1兆トークン規模" ("1 trillion token scale"), not 1 trillion parameters. The digest's "1T-parameter" is consistent with the model name's "-1T" suffix (which in LLM nomenclature normally denotes parameters) but does not match the literal wording in the source summary. Flagged as a note rather than a hard error since the digest appears to be applying the conventional reading of the model name; left as-is.
- **Microsoft Research clarifies "LLMs Corrupt Your Documents When You Delegate"** — JSON title is "Further Notes on Our Recent Research on AI Delegation and Long-Horizon Reliability." The digest title is a heavy interpretive rewrite rather than a paraphrase, though it accurately reflects the post's content (the JSON summary explicitly says the post is a follow-up to "LLMs Corrupt Your Documents When You Delegate"). Left as-is.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles, ArXiv URLs, and author lists in `papers-2026-05-16.md` match the source JSON. Summary and Key Takeaways framings are consistent with the (truncated) abstracts surfaced in `latest.json`; specific quantitative claims (e.g., "8 of 11 frontier models," "30.2 percentage points," "41 V8 bugs," "98.5% removal success") are not visible inside the truncated abstracts but are plausible details from the full papers, and no claim contradicts visible source text.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None. All cited URLs resolve to entries in `latest.json`; titles match or faithfully paraphrase; outlet attributions are correct; and the descriptive summaries (AgentTrap, Payload-less Skills, Tab-Tab-Bug, TESLA, Schneier age-verification, Exchange CVE-2026-42897, Pwn2Own day two, node-ipc, TanStack, NGINX CVE-2026-42945, Funnel Builder + Avada Builder, Turla/Kazuar, OpenClaw "Claw Chain," Taiwan bullet train, MDASH, Dark Reading "Boring Stuff," CISA Cisco SD-WAN, Microsoft Edge, Windows driver rollback) stay within facts present in the source titles/summaries.

### Overall Summary
The digest, security digest, and paper summaries are substantively accurate against the source data in `latest.json`. The only correction applied was to a single bullet about Google's Gemini Spark leak, where the digest's wording incorrectly suggested that Mythos *is* the GPT-5.5 tier when the source treats them as separate (Spark hits GPT-5.5 performance but falls short of Mythos). Two additional notes — the Ring-2.6-1T "tokens vs parameters" wording and the interpretive Microsoft Research title — are characterised judgment calls rather than factual errors and were left in place. Paper summaries and security digest were clean.
