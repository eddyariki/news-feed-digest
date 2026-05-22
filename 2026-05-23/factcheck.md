## Fact-Check Report — 2026-05-23

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
- **Granta's Commonwealth Short Story Prize winner appears to be AI-written** — The digest sub-bullet states "Three of five regional winners flagged as likely AI-generated." The source RSS summary in `latest.json` only mentions "one of the selections... appears to have been written by AI" (specifically Jamir Nazir's "The Serpent in the Grove"). The "three of five" figure is not present in the source summary visible to this check; it may be drawn from the full Verge article body, which is not in the source data. Flagging as a note rather than a hard correction because the truncated RSS summary cannot rule it out.

Otherwise: all URLs match `latest.json` exactly; outlet attributions match; article titles are either verbatim or faithful paraphrases; figures and quotes that are checkable against source summaries (OpenAI -122% margin / $5.7B Q1 revenue, Cloudflare 20%+ layoffs, Cisco CVE-2026-20223 CVSS 10.0, Langflow CVE-2025-34291 CVSS 9.4, Megalodon 5,718 commits / 5,561 repos / 6-hour window, SpaceX 36-page risk section / $28T TAM, Cohere Command A+ minimum 2×H100 or 1×B200, Cursor Composer 2.5 #3 on Artificial Analysis at ~1/10 cost vs. Opus 4.7 / GPT-5.5, Spotify-UMG via URL slug, DeepSeek ~$10B raise at ~$45B valuation) all verify against source summaries. Research-paper section titles and ArXiv URLs all match source records.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper titles match the ArXiv records in `latest.json` exactly. All 12 ArXiv URLs match. Authors lists match the source records (Roland Pihlakas / Jan Llenzl Dagohoy in the Milgram paper appear with a "(the Three Laws collaboration)" affiliation suffix in the source that the summary file drops — a cosmetic, non-factual change). Summary and Key Takeaways paragraphs are plausible expansions of the truncated source abstracts; specific quantitative claims (Boiling the Frog 20.5%–92.9% ASR by model, M3 94%/93%/69% accuracy figures, Blind Spots in the Guard 93.8%→9.7% / χ² statistics, THREAT <1% vs ~50% refusal) are not visible in the truncated `latest.json` abstracts but are consistent with the paper framing and not contradicted by source data.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None. All 13 research-paper entries (Autonomous LLM Agents & CTFs, Measuring Security Without Fooling Ourselves, When Grammar Guides the Attack, Semantic Attacks on Tool-Augmented LLMs, A First Measurement Study on Authentication Security in Real-World Remote MCP Servers, Adversarial Reframing, RADAR, LeakyCLIP, Lost in Modality, PEMark, Provable Robustness against Backdoor Attacks, Frequency-Domain Regularized Adversarial Alignment, Chain Reactions on ECDSA, Charge It to My Neighbor) have ArXiv URLs and titles matching `latest.json` exactly. All vulnerabilities-and-exploits items (Apex One, Langflow+KEV, Cisco Secure Workload CVE-2026-20223, Drupal SQLi, Ubiquiti UniFi, Megalodon, BYOVD, CISA leak / Schneier, First VPN dismantling, Netherlands 800-server seizure, Kimwolf/Dort, Ghostwriter, Webworm) match their source URLs and outlet names. Policy items (Trump EO, Verizon DBIR, former US execs plead guilty) also verify. The Kimwolf piece says "nearly two million devices" while the source summary says "millions of devices" — the more specific figure is plausibly drawn from the article body and is not contradicted by the summary.

### Overall Summary
The 2026-05-23 digest, paper summaries, and security digest are all well-anchored to the underlying `latest.json` source data. URLs, outlet names, and titles match cleanly throughout, and key quantitative claims that can be checked against source summaries (financial figures, CVE IDs and CVSS scores, model-config minimums, layoff percentages) verify. The only soft note is the Granta sub-bullet's "three of five regional winners" figure, which is not present in the source RSS summary; it may come from the article body but cannot be independently confirmed from the cached data. No corrections applied because no claim has been positively contradicted by source material.
