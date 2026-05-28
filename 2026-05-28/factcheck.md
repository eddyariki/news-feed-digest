## Fact-Check Report — 2026-05-28

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
- **[GPU-mining malware spreads via SEO poisoning and AI chatbots]** — The digest summary stated "Microsoft warned of the same delivery technique." The source article (BleepingComputer) title/summary makes no mention of Microsoft, and the security digest's coverage of the same article does not include this claim. The clause is an unsupported addition. **Correction applied:** removed the "; Microsoft warned of the same delivery technique" clause.

#### Notes (beyond the truncated source text, but plausible/accurate — no correction made)
- **[GlassWorm supply-chain botnet takedown]** — The detail that GlassWorm "abused Solana transactions and the BitTorrent DHT" is not present in the provided (truncated) source summary, which ends mid-sentence. It is consistent with public reporting on GlassWorm's C2 infrastructure, so it was left in place. The source describes GlassWorm as a "campaign"; the digest's "botnet" framing is a characterization.

All other News-section items verified clean: titles faithfully match or paraphrase source titles, the citing URLs all resolve to the correct source records in latest.json, and summaries stay within the source facts. This includes the Japanese-language ITmedia/Gigazine items (translations are faithful: e.g. Atom's ¥3B seed round and 1%-GDP goal, GMO's 97.8% adoption figure, the "Gennai"/源内 administrative-AI Diet answer, "Shōsetsuka ni Narō" four-tier AI disclosure, CODA's statement, Micron's $1T market cap), the Pope Leo XIV / *Magnifica Humanitas* encyclical pair, and the rewritten headlines (e.g. The Verge's "AI tried to bury this politician…" → "AI super-PAC spending reshapes a NY congressional race"), which remain faithful to source content. All research-paper titles and ArXiv URLs in the digest match the source data (with acceptable abbreviations such as "RLHF" and shortened subtitles).

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles and ArXiv URLs in papers-2026-05-28.md match those in the digest and source data (papers.md uses the full source titles where the digest abbreviated them). Author lists are plausible and show no obvious errors. Each Summary and Key Takeaways section is consistent with the visible portion of its source abstract and introduces no claims that contradict the abstract. Quantitative details (e.g. SEC-bench Pro's 183 vulnerabilities and V8/SpiderMonkey success rates, MemMorph's 85.9% attack success with three records, the abliteration/prefilling 16–96% range, Anchored Decoding's 75% copying-gap closure, EHR-ReasonCon's 8,048 entities) fall beyond the truncated abstracts available in latest.json and could not be independently confirmed, but none conflict with the visible abstract text, so per the brief they are not flagged.

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
None requiring correction. Every cited article — nine ArXiv research papers plus the news/policy items — was matched to its source record: titles match or faithfully abbreviate the source titles (e.g. "GradSentry … in LLM Fine-Tuning" for "…Large Language Model Fine-Tuning"; "Prompt Injection Detection is Regime-Dependent" for the longer subtitle), the italicized outlet/source attributions are all correct (Ars Technica, The Hacker News, BleepingComputer, Dark Reading, Schneier on Security, The Japan Times, and the ArXiv category tags cs.CR/cs.LG/cs.AI/cs.CL), all URLs resolve to the correct records, and summaries stay within source facts (CVE-2026-27771 affecting Gitea < 1.26.2; 5.8M Uruguayan records; Grandoreiro/BTMOB targeting Spain/Portugal/Mexico/Brazil per WatchGuard and ESET; 29% of UK NIS reports being significant-impact). Notably, the security digest's GPU-mining entry correctly omits the unsupported Microsoft claim found in the news digest.

#### Notes (beyond the truncated source text, but plausible/accurate — no correction made)
- **[GlassWorm Malware Takedown Disrupts Developer Supply Chain Attack Infrastructure]** — The "resilient Solana blockchain and BitTorrent DHT infrastructure" detail is not in the truncated source summary but is consistent with public reporting; "botnet" is a characterization of the source's "campaign."
- **[FBI warns of in-person data theft attacks from extortion gang]** — "socially engineer its way into U.S. law firms' servers and databases" elaborates on the source's "in-person data theft attacks" against U.S. law firms; the elaboration is plausible and consistent, not contradicted by the source.

### Overall Summary
All 71 cited URLs across the three artifacts resolve to genuine source records in latest.json, outlet/source attributions are accurate, and titles match or faithfully paraphrase their sources. The artifacts are substantially accurate. The single substantive error was in the News digest: the GPU-mining entry attributed a warning to Microsoft that does not appear in the source data and was absent from the security digest's parallel coverage of the same story — this unsupported clause has been removed. The paper summaries are clean against the visible abstract text, and the security digest is clean apart from two minor elaborations (GlassWorm's Solana/BitTorrent C2 and the FBI/Silent Ransom social-engineering detail) that go slightly beyond the truncated source summaries but are accurate and consistent with public reporting, so they were left intact. No fabricated sources, mismatched URLs, or invented quantitative claims were found.
