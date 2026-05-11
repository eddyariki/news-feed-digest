## Fact-Check Report — 2026-05-12

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
- **EU regulators still locked out of Anthropic's Mythos model after five meetings (Highlights)** — Source summary says "after four to five meetings" on the Mythos model; the highlight headline rounded this up to "five meetings." Suggested correction: change "after five meetings" to "after four to five meetings." (Inline edit attempt was not authorized.)
- **"ChatGPT以後"に公開のWebサイト、35％がAI生成に？ (Japan section)** — Attributed as "(ITmedia)" in the digest, but the source `source_name` in latest.json is "ITmedia AI+" (the article is delivered via the aiplus RSS feed and is consistent with how every other entry from this feed is labeled in the digest). Suggested correction: change "(ITmedia)" to "(ITmedia AI+)." (Inline edit attempt was not authorized.)
- **Instructure confirms hackers used Canvas flaw to deface portals (AI Security)** — Cited URL is BleepingComputer, whose summary mentions only login-portal modification and an extortion message. The digest's added details ("ShinyHunters-linked," "thousands of schools mid-exam season") are not in the cited article's source summary but are documented in a separate Gigazine entry in the same source dataset. Not factually wrong, but the summary blends in details from a different cited URL — noted, not changed.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All paper titles, ArXiv URLs, and author lists in papers-2026-05-12.md match the corresponding records in latest.json exactly. The unusual ArXiv ID 2601.23143 for the THINKSAFE paper matches the URL recorded in latest.json (the source data carries the same identifier, so this is faithful reproduction, not a digest error). Summary content stays within the bounds of the recorded (truncated) abstracts, and the additional framing in each paper's narrative ("Cognitive Overload," "Structured Cognitive Offloading," etc.) is plausibly drawn from text beyond the truncated abstract excerpt available in latest.json — no obvious fabrications.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None. Every article cited in the security digest — including Ollama OOB-read, Hackers abuse Google ads / Claude.ai chats, Crimenetwork takedown, Cross-Modal Backdoors, Demystifying Agentic Workflow Injection, MIPIAD, Asymmetric Phase Coding, Cybersecurity Policy Compliance, and the Schneier steganography post — matches the title, URL, and source attribution in latest.json. Summaries faithfully paraphrase the source summaries without inventing details.

### Overall Summary
The 2026-05-12 artifacts are largely accurate. The news digest has two minor issues worth correcting: an over-precise "five meetings" claim in the Anthropic/EU highlight (source says "four to five"), and an inconsistent "(ITmedia)" outlet attribution that should read "(ITmedia AI+)" to match the JSON source_name. Inline edits to the digest file were not authorized in this session, so the corrections are recorded here for manual application. One borderline case in the Instructure/Canvas summary blends details from a related Gigazine record into the BleepingComputer-cited bullet; the underlying facts are present in the source dataset, so this was noted but not changed. The paper summaries and security digest are clean: all paper titles, ArXiv URLs, security-article titles, and outlet attributions match the source data exactly, and no summary introduces claims clearly absent from its corresponding source record.
