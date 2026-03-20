## Fact-Check Report — 2026-03-20

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[DarkSword iOS Exploit Kit — Highlights title]** — The Highlights section renders the title as "DarkSword iOS Exploit Kit Uses 3 Zero-Days for Full Device Takeover," omitting "6 Flaws." The corresponding News section entry reads "DarkSword iOS Exploit Kit Uses 6 Flaws, 3 Zero-Days for Full Device Takeover" and the source URL slug is `darksword-ios-exploit-kit-uses-6-flaws.html`. The Highlights title is missing the "6 Flaws" clause. **Correction applied:** Highlights title updated to include "6 Flaws."

**[Coverage gap vs. latest.json]** — `latest.json` (generated 2026-03-19T23:09:12Z) contains only 3 articles: a Gigazine dog-behavior piece, the TechCrunch AI Jeff Bezos/$100B manufacturing article, and the Dark Reading "AI Conundrum: Why MCP Security Can't Be Patched Away" (https://www.darkreading.com/application-security/mcp-security-patched). None of the ~25 articles cited in the digest appear in this file, and the Dark Reading article that does appear is absent from the digest. This indicates the digest was built from a separate, fuller data pull that is no longer present in `latest.json`. Cross-verification against source URLs is not possible for most entries. No correction possible; noted as a data-provenance limitation.

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Contrastive Reasoning Alignment (CRAFT)]** — The digest (line 80) titles this paper "Contrastive Reasoning Alignment (CRAFT): Reinforcement Learning Against Jailbreaks," while `papers-2026-03-20.md` consistently renders it as "Contrastive Reasoning Alignment (CRAFT): Reinforcement Learning from Hidden Representations" — matching the anchor text of the ArXiv link provided. The subtitle diverges: "Against Jailbreaks" (digest) vs. "from Hidden Representations" (papers.md). "From Hidden Representations" describes the paper's core method and appears to be the actual title. **Correction applied:** Digest subtitle updated to "Reinforcement Learning from Hidden Representations."

### Part 3: Security Digest
**Verdict:** SKIPPED

File `/Users/ariki/ai-everything/ai-news/news-curator/output/security-2026-03-20.md` does not exist.

#### Issues Found
N/A

---

### Overall Summary
The digest is substantially clean. Two factual issues were identified: (1) the DarkSword article title in the Highlights section omits "6 Flaws" from a title that includes both "6 Flaws" and "3 Zero-Days" in the body News section and in the source URL slug; (2) the CRAFT paper subtitle in the digest ("Against Jailbreaks") conflicts with the more precise subtitle used consistently in `papers-2026-03-20.md` ("from Hidden Representations"). Both corrections have been applied inline. A data-provenance note was added: `latest.json` covers only 3 articles and does not include the articles cited in the digest, so most entries could not be independently cross-checked against source URLs. The paper summaries are well-grounded, with no claims that appear fabricated or clearly inconsistent with the methods described. The security digest was absent and skipped.
