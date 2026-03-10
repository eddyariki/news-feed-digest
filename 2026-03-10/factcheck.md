## Fact-Check Report — 2026-03-10

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[APT28 Deploys BEARDSHELL and COVENANT Malware Against Ukrainian Military]** — URL in the digest is `https://thehackernews.com/2026/03/apt28-uses-beardshell-and-covenant-malware-to-spy-on-ukrainian-military.html`, which does not match the URL in latest.json: `https://thehackernews.com/2026/03/apt28-uses-beardshell-and-covenant.html`. The longer URL appears to be fabricated. Correction: use the JSON URL.

**[KadNap Botnet Hijacks 14,000+ ASUS Routers for Proxy Network]** — The digest title meaningfully differs from the source (The Hacker News): "KadNap Malware Infects 14,000+ Edge Devices to Power Stealth Proxy Botnet." The digest substitutes "Malware" with "Botnet" in the lead noun, and narrows "Edge Devices" to "ASUS Routers" only (the source summary says KadNap targets ASUS routers primarily but is called "14,000+ Edge Devices"). The URL in the digest (`https://thehackernews.com/2026/03/kadnap-malware-infects-14000-edge.html`) matches the JSON. Correction: update the display title to match the source.

**[Lessons from 16 Open-Source RL Libraries]** (Hugging Face) — The source title in latest.json is "Keep the Tokens Flowing: Lessons from 16 Open-Source RL Libraries." The digest omits the primary title entirely. Correction: use the full source title, or at minimum add the main title.

**[Overly Permissive Salesforce Cloud Configs Under Active Attack]** (Dark Reading) — The source title is "'Overly Permissive' Salesforce Cloud Configs in the Crosshairs." The digest replaces "in the Crosshairs" with "Under Active Attack," which changes the meaning (editorial framing to active-exploitation claim). URL matches the JSON. Correction: use the source title.

**[AutoChecklist: Composable Pipelines for LLM-as-a-Judge Evaluation]** (Research Papers section) — The source title in latest.json is "AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge." The digest's subtitle differs substantially. Correction: update the subtitle to match the source.

**[Sednit Resurfaces with Sophisticated New Toolkit]** — Minor paraphrase of the source title "Russian Threat Actor Sednit Resurfaces With Sophisticated Toolkit." The word "New" is added and "Russian Threat Actor" is dropped. URL matches. This is acceptable paraphrasing; no correction required.

---

### Part 2: Paper Summaries
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Lying to Win: Assessing LLM Deception through Human-AI Games and Parallel-World Probing]** — The summary names specific models (GPT-4o, Gemini-2.5-Flash, Qwen-3-235B) and specific deception rates (42.00%, 26.72%, 0.00%) that are not present in the truncated abstract available in latest.json. These figures are plausible as paper-reported results, but cannot be verified from source data. No correction required; flagged as unverifiable from available data.

**[Invisible Safety Threat: Malicious Finetuning via Steganography]** — Summary states the attack was demonstrated against "GPT-4.1 using OpenAI's fine-tuning API." The abstract in the JSON is truncated and does not confirm the model name. No other discrepancies found. Flagged as unverifiable from available source data; not corrected.

All other paper summaries are well-grounded in their source abstracts and do not introduce clearly absent claims.

---

### Part 3: Security Digest
**Verdict:** PASS

#### Issues Found

None. All security digest article titles faithfully paraphrase their sources, source attributions (outlet names) are correct, and URLs match the JSON. The APT28 entry in the security digest correctly uses the URL `https://thehackernews.com/2026/03/apt28-uses-beardshell-and-covenant.html`, which matches the JSON (the error was in the news digest, not here).

---

### Overall Summary

The digest is largely accurate and well-sourced. Four factual corrections are needed in the news digest: (1) the APT28 article has a fabricated long-form URL that does not match the source; (2) the KadNap display title substitutes "Malware" with "Botnet" and narrows scope to "ASUS Routers" when the source says "Edge Devices"; (3) the Hugging Face RL blog entry drops the primary title "Keep the Tokens Flowing" entirely; and (4) the Salesforce Dark Reading title substitutes an editorial phrase with an active-exploitation claim not present in the source headline. One paper title in the research section (AutoChecklist) has a subtitle that diverges from the source. The security digest is clean. Paper summaries are well-constructed and accurate relative to available abstracts, with two items containing specific figures that are plausible but unverifiable from the truncated source data.
