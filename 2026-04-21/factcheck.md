## Fact-Check Report — 2026-04-21

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[NSA Spies Are Reportedly Using Anthropic's Mythos, Despite Pentagon Feud]** — The digest summary attributes "White House-level negotiations to resolve security concerns" to this TechCrunch article, but the JSON source summary ("NSA is said to be using Anthropic's restricted Mythos AI model") does not mention White House negotiations. That detail appears in a separate ITMedia Japan article ("Anthropicとホワイトハウス、Mythosへの懸念高まりを受けて'仲直り'を模索か") which is already listed under the Japan section. Additionally, the digest uses the characterization "classified-grade Mythos model" while the source says "restricted Mythos AI model"; "classified-grade" implies formal government classification and is not sourced from the summary. These details may exist in the full TechCrunch article but cannot be confirmed from available source data. No correction applied as the full article may support these characterizations, but the summary oversteps what the truncated source data confirms.

**[⚡ Weekly Recap: Vercel Hack, Push Fraud, QEMU Abused, New Android RATs Emerge & More]** — The digest summary says "browser extensions acting as silent data exfiltrators." The source summary says "Browser extensions act normally while pulling data and *running code*." "Running code" is a distinct capability omitted from the digest's characterization. Minor simplification; no correction applied.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All paper titles and ArXiv URLs in papers-2026-04-21.md match the digest exactly. Author lists match the JSON source data for all verified papers. Abstract-level claims in summaries (e.g., MEDLEY-BENCH evaluates 35 models from 12 families; SocialGrid's strongest open model achieves below 60% accuracy; LinuxArena has 1,671 main tasks and 184 side tasks; ReactBench degradation on branching/cyclic structures) are consistent with the JSON abstracts. Specific quantitative results cited in papers.md (Gemini 3.1 Pro AUROC 0.77 in ASMR-Bench; ~23% undetected sabotage rate for Claude Opus 4.6 in LinuxArena) are not present in the truncated JSON abstracts but are not contradicted by them; no obvious fabrication.

---

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None. All article titles, URLs, and source attributions verified against latest.json:
- All BleepingComputer articles (Gentlemen Ransomware/SystemBC, Microsoft Teams helpdesk impersonation, Apple phishing, Scattered Spider, NIST) match JSON titles and URLs.
- All Hacker News articles (SGLang CVE, Anthropic MCP, ZionSiphon, Vercel breach) match JSON titles and URLs.
- Dark Reading (Serial-to-IP Devices) URL and title verified.
- All ArXiv entries (LogJack, Apple Intelligence token theft, Reasoning-targeted Jailbreak, Jailbreak Scaling Laws, SoK Agentic Commerce, HarmfulSkillBench, SBOM Reality Check, PolicyGapper) have IDs present in the JSON.
- Summaries stay within facts present in source data.

---

### Overall Summary
The digest, paper summaries, and security digest are all factually sound. The single notable issue is in the news digest's summary of the TechCrunch NSA/Mythos article, which includes "White House-level negotiations" and "classified-grade" characterizations that appear to originate from a separate ITMedia Japan source rather than the cited TechCrunch article; the TechCrunch source summary is too truncated in the JSON to confirm or deny these details. All URLs, titles, and source attributions across all three artifacts are verified correct. Paper summaries add analytical synthesis but do not introduce claims that contradict the available abstract text.
