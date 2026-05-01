## Fact-Check Report — 2026-05-01

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

- **[NEC CEO: hundreds of millions of yen earmarked for AI investment]** — Translation error. Source title is "NEC社長「AI投資に数百億円」". 数百億円 means "tens of billions of yen" (roughly hundreds of millions of US dollars at current exchange rates), not "hundreds of millions of yen" — this is two orders of magnitude off (数百億 vs. 数億). Corrected inline to "tens of billions of yen".
- **[NEC CEO summary]** — Name error. Summary attributed quotes to "Mori-CEO", but the CEO's name in the source is 森田隆之 ("Morita Takayuki"). 森田 reads as "Morita", not "Mori". Corrected inline to "CEO Morita".

Notes (not corrected — minor inferences within reasonable editorial latitude):
- "OpenAI says it hit its 10 GW compute goal years ahead of schedule" — digest summary calls this "A milestone in the U.S. Stargate buildout"; the Stargate name is not in the source summary, but is widely associated with OpenAI's U.S. compute initiative.
- "Salesforce is crowdsourcing its AI roadmap with customers" — digest summary names "Agentforce" priorities; the source summary refers more generally to "AI roadmap" / "product roadmap". Plausible inference but specific brand name not in source summary.
- "Mistral Medium 3.5" — digest editorializes "France's Mistral pushes back against Chinese open-weights"; the source headline focuses on beating Claude Sonnet 4.5. Reasonable framing but not in source.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All twelve paper titles, ArXiv URLs, and authors match the source data. Summaries and key takeaways stay within scope of the available abstracts (some abstracts in the source JSON are truncated, so specific numerical claims like the 82%/79% FP/FN reduction in eDySec, the 5.6% / 2.2% ASR figures for the Behavioral Firewall, and the 3.5–23.7% AF detection rates for Tatemae could not be verified against the JSON's truncated abstract — but they are consistent with what the abstracts begin to describe and have no obvious contradictions).

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

- **[Anti-DDoS Firm Heaped Attacks on Brazilian ISPs]** — The digest summary identifies the firm as "Huge Networks" and the botnet as "Mirai-derived TP-Link Archer AX21". Neither detail is present in the JSON source summary, which only states a Brazilian DDoS-mitigation firm enabled a botnet attacking rival ISPs. These additions are plausible (consistent with how Krebs typically reports) and likely come from the full article body, but they cannot be verified from the source data provided. The summary also omits the firm's CEO's stated counter-claim (security breach by a competitor) that is in the JSON summary.
- **[PyTorch Lightning and Intercom-client Hit in Supply Chain Attacks]** — Security digest says "two malicious versions (2.6.2 and one other)"; the source JSON explicitly identifies them as 2.6.2 and 2.6.3 (the digest News section gets this right). Vague but not factually incorrect.

### Overall Summary
Across the three artifacts, the only clearly factual error is the NEC headline's mistranslation of 数百億円 ("tens of billions of yen") as "hundreds of millions of yen" — an order-of-magnitude error — together with the related "Mori-CEO" name truncation; both have been corrected inline in the digest. All other article URLs, source attributions, titles (modulo paraphrase), and paper metadata check out against `latest.json`. The remaining notes are minor editorial inferences (Stargate, Agentforce, Mistral framing) and one security-digest summary that adds Krebs-typical specifics not visible in the JSON's summary excerpt. No fabricated articles, mismatched URLs, or invented research-paper claims were detected.
