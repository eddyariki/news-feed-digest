## Fact-Check Report — 2026-05-22

### Part 1: News Digest
**Verdict:** PASS

#### Issues Found
None. All cited article titles, URLs, source attributions, and summaries align with `latest.json`. Spot-checks of specific claims:
- "Apple M5 kernel memory corruption…Anthropic's Mythos" — matches Schneier source.
- "US Cyber Command…OpenAI, Google, and Anthropic models…6–24 months" — matches The Decoder source ("comparable tools could be widely available within six to 24 months").
- Erdős 1946 unit-distance conjecture, algebraic number theory, Tim Gowers "milestone in AI mathematics" — all verbatim from The Decoder source.
- SpaceX S-1 figures: $15B/year Anthropic compute, $6.36B xAI loss, $2.8B turbines, 85.1% voting power — match The Decoder, Verge, and TechCrunch sources.
- The Path 95 vs 65 Vera-MH score, Hark $700M Series A, $43B Nvidia startup holdings, Drupal CVE-2026-9082, Linux CVE-2026-46333, 3,800 GitHub repos — all verified against source summaries.
- All 15 ArXiv paper IDs in the Research Papers section resolve to matching titles in the source data.
- Japan-section Japanese-language titles and URLs match `latest.json` exactly.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles, ArXiv URLs, and author lists match `latest.json` records. The summaries and Key Takeaways stay consistent with the (truncated) abstracts available in the source data — claims like Mirage's four diagnostics (LPR/CKA/Feature Separability/Layer-Wise Recovery), VERA-MH's three-stage pipeline targeting suicidal-ideation risk, and the Apple DP audit's framework name and coverage scope (Safari domains, keyboard events, photo attributes, health reports) all correspond to the abstract text. Specific numerical claims (e.g., 106 0-day MCP vulnerabilities, 87%/68% macOS DP-violation coverage, 90×/0.71%/18k-verifications-per-sec for HBHC, 12.71%/33.49% AIR gains) are not contradicted by the abstracts and were not fabricated checks.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None.
- Microsoft Defender entry: CVE-2026-41091, CVSS 7.8 (privilege escalation) and the second DoS flaw are confirmed by The Hacker News companion article (`microsoft-warns-of-two-actively.html`), which the digest correctly cross-links.
- Showboat / JFMBackdoor naming and Linux/Windows split confirmed by BleepingComputer source; "modular post-exploitation framework" and "since at least mid-2022" timing confirmed by the linked Hacker News piece.
- GitHub / Nx Console / TanStack chain: 3,800 internal repositories number matches BleepingComputer source; URL and outlet attribution correct.
- "Underminr" CDN-fronting framing aligns with the Dark Reading title and summary.
- All 11 ArXiv papers in the AI Security Research section (including the additional ones not in the main digest — `2605.20734` egress monitor, `2605.20282` Mirage) resolve to matching titles in `latest.json`.

### Overall Summary
All three artifacts — the news digest, the paper summaries file, and the security digest — accurately reflect the source data in `latest.json`. Titles, URLs, outlet attributions, and headline numerical claims (financial figures, CVE IDs, CVSS scores, paper authors, ArXiv IDs) are all faithful to the source records. Paraphrases stay within the bounds of the source titles and summaries, and additional contextual claims (e.g., turbine spending, modular post-exploitation framework, 1946 conjecture date) are corroborated by other articles in the same source set or by the linked companion sources. No corrections needed.
