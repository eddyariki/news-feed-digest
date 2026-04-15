## Fact-Check Report — 2026-04-16

### Part 1: News Digest
**Verdict:** FAIL

#### Issues Found

**[Audit: Big Tech Often Ignores CA Privacy Law Opt-Out Requests]** — URL is wrong in the news digest. The digest links to `https://www.darkreading.com/application-security/audit-big-tech-often-ignores-ca-privacy-law-opt-out-requests` but the source JSON records the correct URL as `https://www.darkreading.com/cyber-risk/audit-big-tech-ignores-data-collection-requests` (wrong path segment `/application-security/` instead of `/cyber-risk/`, and wrong slug). The security digest has the correct URL.

**[Patch Tuesday, April 2026 Edition]** (Krebs on Security) — The digest summary says "Detailed breakdown of the 167 CVEs, including two zero-days among the elevation-of-privilege bugs." This mischaracterises the Krebs article. The source JSON shows the Krebs article focuses on a SharePoint Server zero-day and a publicly disclosed Windows Defender weakness codenamed "BlueHammer," plus a Google Chrome zero-day and an Adobe Reader emergency fix — none of which are described as EoP zero-days. The "elevation-of-privilege bugs with two zero-days" framing belongs to the separate Dark Reading article "Privilege Elevation Dominates Massive Microsoft Patch Update," which is already listed correctly.

**[Highlights — Microsoft 169 Flaws]** (note, not a definitive error) — The highlights blurb says "over 90 privilege-escalation bugs." The JSON for The Hacker News article indicates 93 vulnerabilities allow remote code execution (not privilege escalation). The Dark Reading article states EoP bugs account for "more than half" of the ~165–169 patches, which implies ~83+, not necessarily "over 90." This language likely conflates the 93-RCE count with the EoP count and should be "more than half" or "more than 80."

---

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Can We Watermark Low-Entropy LLM Outputs?]** — Minor inconsistency between the news digest and the security digest characterisations. The news digest says the paper finds "provably undetectable watermarking is infeasible in these regimes." The security digest says "The proposed construction maintains output quality while enabling reliable attribution." These framings may be compatible (the paper could find undetectable watermarking infeasible yet propose a detectable construction), but they pull in opposite directions. The truncated abstract confirms the paper studies provably undetectable watermarking; the exact conclusion is not verifiable from the available abstract. Flagged for awareness; not a confirmed factual error.

All other paper titles, ArXiv URLs, and author lists match the source data. Summaries and key takeaways are consistent with the available abstracts and do not introduce claims clearly absent from the source material.

---

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found

None. All article titles, outlet names, URLs, and summaries were checked against the source JSON and are accurate. The "Audit: Big Tech" article, while URL-wrong in the news digest, has the correct URL (`https://www.darkreading.com/cyber-risk/audit-big-tech-ignores-data-collection-requests`) in the security digest.

---

### Overall Summary

The digest is largely accurate. Two definitive errors were found in the news digest: (1) a wrong URL path/slug for the Dark Reading Big Tech privacy audit article, and (2) a misleading summary for the Krebs on Security Patch Tuesday article that attributes Dark Reading's "EoP with two zero-days" framing to the Krebs piece, which actually focuses on the SharePoint zero-day and the Windows Defender "BlueHammer" disclosure. The security digest is clean. The paper summaries are accurate to the source abstracts, with one minor internal inconsistency in how the watermarking paper is characterised across the two outputs. Corrections have been applied inline below.
