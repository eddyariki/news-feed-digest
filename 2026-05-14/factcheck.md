## Fact-Check Report — 2026-05-14

### Part 1: News Digest
**Verdict:** PASS

#### Issues Found
None.

All 87 article URLs cited in the News, Highlights, and Research Papers sections resolve to the corresponding source records in `latest.json`. Source-name attributions are correct in every case (the digest uses "Microsoft Research" where the JSON stores "Microsoft Research Blog" — treated as a benign abbreviation, not a factual error). Titles are either verbatim or faithful paraphrases / truncations of the source titles. Section summaries (Highlights bullets and News bullets) stay within the facts present in the source `summary` fields:

- Anthropic 34.4% vs OpenAI 32.3% on Ramp AI Index — confirmed.
- Microsoft MDASH multi-model agentic scanning harness, 16 surfaced Windows flaws, 138 May Patch Tuesday fixes (30 Critical, 104 Important) — confirmed.
- Foxconn / Nitrogen ransomware; 8TB / 11M+ files (Gigazine); ~600 manufacturing-sector incidents YTD (Dark Reading) — confirmed.
- Anthropic rejecting Chinese request for Claude Mythos Preview — confirmed; Gigazine's own headline frames it as a Chinese-government request, so the highlight phrasing is consistent with the source.
- SoftBank ¥5 trillion net profit (¥5.022T, +333.7% YoY), Q4 ¥1.83T vs ¥295.2B consensus, "largest ever for a Japanese company" — confirmed across The Japan Times and ITmedia.
- Mandiant M-Trends 2026 mean-time-to-exploit −7 days vs 32-day remediation — confirmed.
- Luma Uni-1.1 at $0.04/image, 2,048-px, web search / reasoning / 9 reference images — confirmed.
- Anthropic Claude for Small Business: 15 agent workflows, QuickBooks/PayPal/HubSpot, 10-city tour — confirmed.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None.

All 12 paper titles and arXiv URLs in `papers-2026-05-14.md` match the digest and `latest.json` exactly. Author rosters match (the IPI-proxy author list in the JSON contains a parenthetical "(Janet)" nickname after the first author's given name; the summary uses the canonical "Chia-Pei Chen" form, which is correct). Source abstracts in `latest.json` are truncated to ~500 characters, so detailed numeric claims in the summaries (e.g., ExploitGym's 898 instances, AgentShield's 176 cross-lingual prompts, GRIEF's 15 vulnerabilities / 2 CVEs, FATE's 33.5% / 82.6% improvements, the 1,002-participant alignment study, etc.) cannot be cross-checked against this source data, but all claims that *are* visible in the truncated abstracts (problem framing, methodology themes, regulatory anchors, agent-failure typologies) are consistent with the summaries. Nothing in the summaries contradicts the truncated abstracts or appears implausible.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None.

All 23 articles cited in `security-2026-05-14.md` resolve in `latest.json`. Source attributions match (BleepingComputer, The Hacker News, Dark Reading, Krebs on Security, Schneier on Security, arXiv cs.AI/cs.CL/cs.CR). Titles are either exact or faithful paraphrases. Per-article framing is grounded in the source `summary` fields:

- Schneier / UK AI Security Institute, GPT-5.5 ≈ Mythos, "requires more scaffolding" — confirmed.
- MDASH "multi-model agentic scanning harness," 16 surfaced flaws, limited private preview — confirmed.
- Microsoft 138 fixes (30 Critical / 104 Important), 61 privilege-escalation, none publicly known or under active attack — confirmed.
- BitLocker "YellowKey" / "GreenPlasma" PoCs — confirmed.
- Exim unauthenticated RCE in certain configurations — confirmed.
- FamousSparrow attribution by Bitdefender, Azerbaijani oil-and-gas target, late-Dec-2025 through Feb-2026 window — confirmed.
- GemStuffer / 150+ RubyGems, Socket attribution, exfiltration channel (not developer compromise) — confirmed.
- Android Intrusion Logging within Advanced Protection Mode — confirmed.
- Mandiant M-Trends 2026 figures — confirmed.
- arXiv security papers (Few-Shot DPO Attack, Context-Aware Spear Phishing, FlowSteer, x402 five attacks) — abstracts in `latest.json` align with the summaries.

### Overall Summary

All three artifacts pass fact-checking against `latest.json`. URL, source attribution, title, and summary content are faithful to the source data in every case. Title differences between digest and source are limited to acceptable digest-style trimming (long Japanese titles condensed to their lede, headline-case normalization, ASCII vs. smart-quote substitution); no article was attributed to the wrong outlet, and no summary introduced facts absent from the source. Paper summaries are consistent with the truncated abstracts available in `latest.json`; the report does not flag detailed numeric claims that cannot be checked against the truncated source, per the "do not fabricate checks" instruction. No corrections were applied.
