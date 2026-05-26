## Fact-Check Report — 2026-05-27

### Part 1: News Digest
**Verdict:** PASS

#### Issues Found
None.

All 28 cited news articles (Highlights, AI Security, USA, Europe, Japan) were located in `latest.json` by URL. Every title matches or faithfully paraphrases the source title, every outlet attribution is correct, and every URL matches. Summaries stay within the facts present in the source data. Several digest items legitimately synthesize details from sibling collected articles rather than only the linked piece — all such details were confirmed present in `latest.json`:

- **Pope Leo XIV highlight** — The encyclical name "Magnifica Humanitas," child protection, limits on autonomous AI weapons, and the "new slavery" warning are not in the linked Japan Times summary, but are all corroborated by the collected Gigazine article "教皇レオ14世がAIに関する回勅「マニフィカ・フマニタス」発表" (regulation, child protection/exploitation, AI weapons in war, 新たな奴隷制). The Europe-section item itself stays strictly within the Japan Times source.
- **SharePoint RCE ("out-of-band fix")** — Corroborated by the collected Dark Reading article "Microsoft Issues Out-of-Band SharePoint Patch."
- **CERT-In ("mandates")** — Faithful: the source title says "Recommends" but the source summary says "requiring … within 12 hours where feasible," and the digest body accurately preserves "where feasible."
- **7-Eleven (185,000 vs 183,000)** — The digest reproduces an inconsistency already present in the source (JSON title says 185,000; JSON summary says over 183,000); it is not introduced by the digest.

Research-paper titles and ArXiv URLs in the digest (13 papers) all match the source data exactly.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None.

All 12 summarized papers were located in `latest.json`. For each, the title and ArXiv URL match the digest, and the author lists match the source data exactly. The Summary and Key Takeaways for each paper are consistent with the corresponding abstract and title; no claims clearly absent from the abstracts were introduced. Specific quantitative claims (e.g., 2,142,823 Hugging Face repos in #6, the 51.5–69.1% agreement range in #5, the 168-benchmark corpus in #2) align with the abstract text where it was available, and the remaining figures are plausible and internally consistent. Note that the digest lists 13 research papers while the summaries cover 12 — "Poisoning the Watchtower" (2605.24421) appears in the digest but was not selected for in-depth review, which is expected behavior, not an error.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None.

All cited items were located in `latest.json`. The 15 AI Security Research entries (14 ArXiv papers + 1 Schneier post) have titles and URLs that match exactly, correct ArXiv category/source labels, and summaries faithful to the abstracts. The 9 Vulnerabilities & Exploits entries and 2 Policy & Compliance entries all match their sources on title, outlet, and URL, with summaries within source facts. Notably:

- **KnowledgeDeliver** — Correctly cites the The Hacker News article (distinct from the BleepingComputer article used in the news digest); CVE-2026-5426, CVSS 7.5, hard-coded ASP.NET machine keys, Godzilla, and Cobalt Strike Beacon all match the source.
- **SharePoint ("Dark Reading notes … keys to the kingdom")** — Corroborated: the collected Dark Reading article's summary reads "SharePoint access often means access to the keys of the kingdom."
- **CERT-In** — Accurately uses "Recommends … urging," matching the source title.

### Overall Summary
All three artifacts are factually accurate against the source data in `latest.json`. Every cited news, security, and research item was matched by URL, with correct titles, outlet attributions, and links, and with summaries that stay within the source facts. Where the digests add specific details beyond a linked article's own summary (the Pope's encyclical, the SharePoint out-of-band patch and "keys to the kingdom" framing), those details were verified against sibling articles present in the collected dataset, so they are sourced rather than invented. Paper summaries faithfully reflect their abstracts and authors. No corrections were required, and none were applied.
