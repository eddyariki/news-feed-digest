## Fact-Check Report — 2026-04-03

### Part 1: News Digest
**Verdict:** FAIL

#### Issues Found

**[Claude Code Leak Used to Push Infostealer Malware on GitHub]** (AI Security section) — Digest says "Attackers leveraged leaked Claude Code access to inject infostealer malware into GitHub projects." Source (BleepingComputer) says "exploiting the recent Claude Code **source code** leak by using **fake GitHub repositories** to deliver **Vidar** information-stealing malware." Two errors: (1) the incident is a source code leak, not a credentials/access leak; (2) malware is delivered via fake repositories, not injected into existing projects. Correction applied.

**[Apple Expands iOS 18.7.7 Update to More Devices to Block DarkSword Exploit]** (AI Security section) — Digest adds "after the DarkSword exploit was observed in the wild targeting state-affiliated actors." Source (The Hacker News) summary makes no mention of state-affiliated actors; it says the update is "to protect users from the risk posed by a recently disclosed exploit kit known as DarkSword." Detail removed. Correction applied.

**[OpenAI Acquires TBPN, the Buzzy Founder-Led Business Talk Show]** (USA section) — Digest describes TBPN as "a popular founder-focused **video network**." Source (TechCrunch) title calls it a "founder-led **business talk show**" and the summary calls it "Silicon Valley's cult-favorite **tech podcast**." "Video network" is not supported by the source. Correction applied.

**[Microsoft's New 'Superintelligence' Game Plan Is All About Business]** (USA section) — Digest spells the name as "Mustafa **Suleiman**." Source (The Verge) summary and URL slug both use "Mustafa **Suleyman**." Correction applied.

**[It's Not Easy to Get Depression-Detecting AI Through the FDA]** (USA section) — Digest says Kintsugi shut down "after failing to navigate the FDA's **De Novo pathway**." Source (The Verge) summary says "after failing to secure **FDA clearance** in time" with no mention of a specific pathway. Added specificity not present in source. Correction applied.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All paper titles and ArXiv URLs in papers-2026-04-03.md match the source data. Abstract-level claims in the summaries are plausible and consistent with the truncated abstracts available; no obviously fabricated findings were detected.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Possible US Government iPhone Hacking Tool Leaked]** (Vulnerabilities & Exploits) — Security digest states the toolkit uses "**23 vulnerabilities** across five exploit chains." Source (Schneier on Security) summary says "five complete hacking techniques" but does not enumerate 23 vulnerabilities. The five-chain count is consistent with the source; the "23 vulnerabilities" figure is not verifiable from the source JSON summary. No correction applied (claim may appear in full article body, and the five-chain figure is confirmed); flagged for awareness.

---

### Overall Summary
The news digest contained five factual errors requiring correction: a mischaracterization of the Claude Code incident as a credentials/access leak rather than a source code leak (and a related misdescription of the delivery mechanism), an unsourced claim that the DarkSword exploit targeted state-affiliated actors, a mislabeling of TBPN as a "video network" when sources call it a talk show or podcast, a misspelling of Mustafa Suleyman's surname, and an unverified reference to the FDA's De Novo pathway that should simply read "FDA clearance." Paper summaries are clean. The security digest is largely accurate; one claim (23 vulnerabilities in the Coruna toolkit) is unverifiable from source data but consistent in the more verifiable five-chain count.
