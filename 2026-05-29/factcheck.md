## Fact-Check Report — 2026-05-29

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found
- **[Taiwan arrests three in alleged Nvidia GPU smuggling ring routed via Japan]** (Highlights #5) — The cited URL points to The Japan Times article, whose JSON title and summary are "Taiwan suspects Nvidia chips smuggled to China via Japan" and focus on Chinese companies renting foreign-owned hardware in overseas data centers. The digest highlight's title ("arrests three") and summary specifics ("Keelung prosecutors," "Supermicro AI servers") are content from the separate Gigazine article (`https://gigazine.net/news/20260528-nvidia-smuggling-transshipment-japan/`), which is correctly cited in the Japan section. The two articles cover the same broader case, but the cited URL's JSON summary does not support "arrests three," "Keelung prosecutors," or "Supermicro" specifically. Correction: rephrase the highlight to match what the Japan Times article actually says (suspicion / data-center rentals framing), or change the URL to the Gigazine article that supports the specifics. Inline edit was attempted but blocked by file-write permissions; the recommended replacement bullet is:

  ```
  - **[Taiwan suspects Nvidia chips smuggled to China via Japan](https://www.japantimes.co.jp/business/2026/05/28/taiwan-china-nvidia-smuggle/)**: Japan emerges as one of many Asian locations where Chinese companies access American AI chips by renting foreign-owned hardware installed in overseas data centers, exposing a new export-control gap.
  ```

All other 52 cited URLs resolve in `latest.json`, all titles are accurate or faithful paraphrases of the source titles, all outlet attributions are correct, and all summaries stay within the facts present in the JSON summaries (with normal stylistic compression). The 14 research-paper ArXiv URLs and titles all match `latest.json` exactly.

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper summaries (Code as a Weapon, Models That Know How Evaluations Are Designed Score Safer, MIRAGE, SilentRetrieval, Emerging Threats of the Agent Skill Ecosystem, Operational AI Deployment Assurance, Informing AI Policy Assessment, Behavioural Analysis of Alignment Faking, When Context Flips Safety Breaks, SafeMed-R1, GuardReasoner-Omni, AgentGuard) match the digest titles and ArXiv URLs, list authors consistent with the JSON `authors` field, and confine claims to what the abstracts (as excerpted in `latest.json`) plausibly support. Numerical specifics in the summaries (e.g. 3,984 skills / 76 malicious / 13.4% critical for Emerging Threats; 1,111-sample benchmark and 23–30% ASR for MIRAGE; 181k training samples for GuardReasoner-Omni; PacifAIst + 12 models / 17.4 pp safety-vs-commonsense gap for When Context Flips Safety Breaks; ~10-line client integration for AgentGuard) are consistent with the abstract excerpts seen in the JSON.

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found
None. All 19 cited URLs (including the inline "see also" links) resolve in `latest.json`. Titles match the source titles either exactly or as faithful paraphrases (e.g. "Power users" wording, BTMOB/RAT framing). Outlet attributions and author bylines (Dan Goodin / Sergiu Gatlan / Bill Toulas / Nate Nelson / Jai Vijayan / Fahmida Y. Rashid & Kristina Beek / Elizabeth Montalbano) match the JSON `authors` field. Specific factual claims — CVE-2026-35616 for FortiClient EMS, the "EKZ" credential-stealer name, the Rapid7 CVSS-9.4 rating with no CVE for Gogs, "Chaotic Eclipse" researcher handle, 800 servers / two operators in the Dutch raid on THE.Hosting, ShinyHunters claim from April 2026 for the Carnival breach, and the 56-month sentence for the Romanian hacker — all match `latest.json`.

### Overall Summary
The 2026-05-29 artifacts are highly faithful to their source data. Every cited URL across the news digest, research-paper list, paper summaries, and security digest resolves to a real article in `latest.json`, and outlet attributions, author bylines, and factual specifics are accurate throughout. The only issue identified is a single conflation in the Highlights section, where one bullet points to The Japan Times article but describes details (three arrests, Keelung prosecutors, Supermicro servers) that come from a separate Gigazine article on the same case; a recommended replacement is provided above (inline edit was blocked by file-write permissions). The paper summaries stay within the bounds of the published abstracts, the security digest is clean, and no fabricated claims or invented numbers were found.
