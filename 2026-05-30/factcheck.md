## Fact-Check Report — 2026-05-30

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
- **Google AI Studio publishes Gemini Omni & Gemini 3.5 demo reel** — The source's `source_name` is "Google AI Blog" (blog.google), not "Google AI Studio." Google AI Studio is a separate Google product (a developer playground for Gemini), not the publishing entity for this post. Correction: change the headline to "Google publishes 9 demos of Gemini Omni and Gemini 3.5 in action" to faithfully mirror the source title "9 demos of Gemini Omni and Gemini 3.5 in action." (Inline edit attempted but write permission was not granted; please apply manually.)

All other cited URLs, source attributions, titles, ArXiv IDs, paper titles, and summaries in the News Digest verify against `latest.json`. Spot-checks confirmed:
- Each Highlights URL resolves to the exact source article (Anthropic/Mythos, OpenAI Japan Cyber Action Plan, Dutch botnet, ChatGPhish, Rosalind Biodefense).
- All News section URLs (AI Security, USA, Europe, Japan) match titles and outlets in the JSON.
- All 13 Research-Paper ArXiv links (`2605.29225`, `2605.29586`, `2605.29960`, `2605.30096`, `2605.30040`, `2605.29742`, `2605.29359`, `2605.30162`, `2605.29442`, `2605.29910`, `2605.28843`, `2605.29251`, `2605.30049`) resolve to the correct paper titles in the source feed.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. Each of the 12 paper summaries has:
- A title and ArXiv URL that match both the digest and the source feed.
- Authors that match the JSON `authors` field exactly.
- Summary and Key Takeaways content that, where verifiable against the (truncated) abstract excerpt in the JSON, stays within the bounds of the paper's stated scope. Numeric and qualitative details (e.g. specific model failure rates, the 105-instance FinVerBench subset, the 400-run Juice Shop study, the 20,574 coding sessions, the 15 Agora bugs, the 1,469% token inflation) are consistent with the abstracts to the extent they are visible and were not flagged as obvious fabrications.

### Part 3: Security Digest
**Verdict:** FAIL

#### Issues Found
- **Asia's Cyber Insurance Market Shows Signs of Life** — The hyperlink URL is wrong. The digest links to `https://www.darkreading.com/cloud-security/asias-cyber-insurance-market-shows-signs-of-life`, but the source `latest.json` URL is `https://www.darkreading.com/cybersecurity-operations/asias-cyber-insurance-market-signs-of-life` (different section path, and the slug has no "shows-"). The displayed title still matches the source. Correction: replace the URL with the canonical one above. (Inline edit attempted but write permission was not granted; please apply manually.)

All other cited security-digest items verified against the JSON:
- AI Security Research: all 8 ArXiv links (`2605.29396`, `2605.29629`, `2605.28999`, `2605.29224`, `2605.30031`, `2605.29737`, `2505.20955`, `2605.29569`) match the listed paper titles.
- Vulnerabilities & Exploits: ChatGPhish, Marimo CVE-2026-39987, ChatGPT share-link malware, GREYVIBE (both Hacker News and BleepingComputer), Dutch botnet, Charter Communications (4.9M accounts), 23andMe AG lawsuit, Sicoob NuGet, Kimsuky/HTTPSpy — all URLs, outlets and titles match.
- Policy & Compliance: Japan economic-security white paper and Chilling Effects URLs/titles match; the Schneier summary's framing of Trump-administration campus-speech actions ("lawsuits, arrests, deportations, expulsions") is supported verbatim by the source summary.

### Overall Summary
The corpus is largely accurate. Out of roughly 80 cited articles and papers across the three artifacts, only two issues were found: a misattributed publisher on a single Google blog post in the News Digest (Google AI Studio vs. Google AI Blog), and one incorrect URL in the Security Digest for the Dark Reading "Asia's Cyber Insurance Market" article (wrong section path and stray "shows-" token in the slug). All ArXiv links, outlet attributions for the high-volume security/Hacker-News/BleepingComputer items, and the Japan-section ITmedia/Gigazine/Japan Times items check out. Both corrections are mechanical (one headline word, one URL) and were attempted inline but blocked by tool-permission prompts; the recommended fixes are stated above.
