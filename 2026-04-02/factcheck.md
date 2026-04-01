## Fact-Check Report — 2026-04-02

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Gradient Labs gives every bank customer an AI account manager]** — Digest says "Built on GPT-4.1 and GPT-5.4"; source JSON says "GPT-4.1 and GPT-5.4 mini and nano." The digest implies a model named "GPT-5.4" when the actual models used are GPT-5.4 mini and GPT-5.4 nano. **Correction:** "Built on GPT-4.1 and GPT-5.4 mini and nano".

**[OpenAI Confirms $122B Round and ChatGPT Super App]** (USA News section summary) — Digest says "signals a pivot away from API-first toward an integrated consumer super app"; source JSON summary says "signals a hard pivot toward enterprise." The "consumer" framing and "away from API-first" language are not supported by the source summary. **Correction:** Remove "away from API-first" and "consumer"; replace with "toward an integrated ChatGPT super app and enterprise" or simply match source: "signals a hard pivot toward enterprise."

**[Trojan-Speak: Bypassing Constitutional Classifiers via Adversarial Finetuning]** (Research Papers section) — Missing "with No Jailbreak Tax" from the paper title. Source title: "Trojan-Speak: Bypassing Constitutional Classifiers **with No Jailbreak Tax** via Adversarial Finetuning." The omitted phrase is a key finding of the paper. **Correction:** Add "with No Jailbreak Tax".

**[Extending MONA: Reward-Hacking Mitigation via Myopic Optimization with Non-Myopic Approval]** (Research Papers section) — Title substantially reworded. Source title: "Extending MONA in Camera Dropbox: Reproduction, Learned Approval, and Design Implications for Reward-Hacking Mitigation." The digest subtitle describes MONA itself rather than what this paper actually contributes (reproduction + learned approval extensions). **Correction:** Use source title.

*Note on ITmedia source attribution:* Several articles from ITmedia Enterprise (`/enterprise/` URL path) and ITmedia Business (`/business/` URL path) are correctly attributed in the digest as "ITmedia Enterprise" and "ITmedia Business" respectively, even though the JSON source_name field reads "ITmedia AI+" for all of them (an RSS feed aggregation artefact). The digest attributions are more accurate than the raw JSON field and are not errors.

---

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Trojan-Speak]** — Section heading "## 4. Trojan-Speak: Bypassing Constitutional Classifiers via Adversarial Finetuning" is missing "with No Jailbreak Tax." The link text within the same entry correctly includes the full title. **Correction:** Update section heading to match the link text.

**[Extending MONA]** — Section heading "## 9. Extending MONA: Reward-Hacking Mitigation via Myopic Optimization with Non-Myopic Approval" does not match the source title "Extending MONA in Camera Dropbox: Reproduction, Learned Approval, and Design Implications for Reward-Hacking Mitigation." The link text within the same entry correctly uses the source title. **Correction:** Update section heading to match the link text.

Summary content and key-takeaway claims for all 12 papers are consistent with the abstract content visible in the source JSON. No fabricated claims were identified.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Design Principles for a Benchmark Evaluating Security Operation Capabilities of Multi-agent AI Systems]** — Title omits "for the Construction of." Source title: "Design Principles for **the Construction of a** Benchmark Evaluating Security Operation Capabilities of Multi-agent AI Systems." **Correction:** Insert "for the Construction of a" after "Design Principles".

All other articles — titles, URLs, source attributions, and summaries — match or faithfully paraphrase the source JSON data.

---

### Overall Summary
The three artifacts are largely accurate. The most consequential error is the mischaracterization of the OpenAI USA News entry, which frames the company's strategic pivot as aimed at a "consumer super app" while the source summary says "hard pivot toward enterprise" — a meaningful difference in framing. The Gradient Labs model-name shortening ("GPT-5.4" for "GPT-5.4 mini and nano") is a factual inaccuracy that should be corrected. Two research paper titles — Trojan-Speak and Extending MONA — are truncated or reworded in both the digest and the paper summaries section headings, losing meaningful descriptive content; link texts within papers.md are correct. The security digest has one minor title truncation. No invented facts, incorrect URLs, or wrong source attributions were found beyond those noted above.
