## Fact-Check Report — 2026-05-26

### Part 1: News Digest
**Verdict:** PASS

#### Issues Found
None.

All articles cited in the Highlights and News sections (AI Security, USA, Europe, Japan) were matched against `latest.json` by URL. Every cited URL resolves to a real source article. Titles faithfully paraphrase the source titles, outlet attributions are correct (The Verge AI, ITmedia AI+, The Decoder, TechCrunch AI, Gigazine, BleepingComputer, The Hacker News, Krebs on Security, Ars Technica, OpenAI Blog, The Japan Times), and summaries stay within the facts present in the source title/summary. Spot examples verified: the Pope Leo encyclical *Magnifica Humanitas* framing, the ~50-partner-firms / 10,000+ flaws figure (ITmedia), AlphaProof Nexus's nine Erdős problems with two open for 56 years, the 52%→63% memory-cost shift across NVIDIA/AMD/Google/Amazon, the ~70% compute cut via AutoTTS, the ¥20–30bn ($125M–$190M) Sakura Internet figure, and the 93%/91% Amazon/Yelp fake-review accuracy all match their sources. The 13 research papers listed (titles + ArXiv URLs) all resolve correctly, including GT-HarmBench at the unusual arXiv:2602.12316 id.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None.

All 12 summarized papers have titles, authors, tags, and ArXiv URLs that exactly match the source data, and each matches its corresponding digest entry. The stored abstracts in `latest.json` are truncated to ~500 characters, so the finer numeric claims in the summaries (e.g., 38% socially-harmful failures, 52,272 harm ratings, 70%→0% / 83.3%→0% MemAudit reductions, Qwen3-32B 54%→7%, 0.904 precision) come from the full abstracts the pipeline fetched and could not be independently re-verified against the truncated source; however, none of them contradict the available abstract text, and all overlapping facts (scenario counts, model lists, dataset sizes, method descriptions) align. The closing note that "HalluScan" (arXiv:2605.02443) is the one paper omitted to meet the 12-paper cap is consistent with the digest's 13-paper list.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None.

All 24 ArXiv research entries resolve by URL, with titles and `ArXiv cs.*` source labels matching `source_name` in the JSON, and descriptions consistent with the (truncated) abstracts. All eight news items (Ghost CMS / The Hacker News, Ghost CMS / BleepingComputer, TrapDoor / The Hacker News, Lazarus RemotePE / The Hacker News, FBI Kali365 / BleepingComputer, Weekly Recap / The Hacker News, Netherlands / Krebs on Security, chatbot personalities / The Verge AI) match source title, outlet, URL, and summary facts — including specifics such as CVE-2026-26980 (CVSS 9.4) and QiAnXin XLab's 700+ hijacked sites, TrapDoor's 34+ packages / 384+ versions starting May 22 2026, and Fox-IT's attribution of RemotePE to Lazarus via DPAPILoader/RemotePELoader.

### Overall Summary
All three artifacts pass fact-checking with no factual errors found. Every cited news and security URL resolves to a genuine source article in `latest.json`, outlet attributions are accurate, and titles and summaries faithfully paraphrase the source data without introducing invented details. All paper titles, authors, and ArXiv identifiers match across the digest, paper summaries, and source data. The only limitation is that `latest.json` stores abstracts truncated to ~500 characters, so the most granular statistics in the Part 2 summaries could not be re-verified against source text — but nothing in those summaries contradicts the available abstracts, and the digest/paper-summary cross-references are fully consistent. No inline corrections were required.
