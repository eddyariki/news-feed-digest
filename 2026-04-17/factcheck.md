## Fact-Check Report — 2026-04-17

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[AI Chat Rulings Prompt Lawyers to Warn: Your Chats Could Be Used Against You]** — Title uses plural "Rulings" but the source title (Japan Times) reads "AI ruling prompts warnings from U.S. lawyers…" (singular). The source summary confirms a single federal judge ruling. Correction: change "Rulings" to "Ruling" in the digest title.

All other articles checked: URLs are exact matches to source JSON, outlet attributions are correct, and summaries stay within facts present in source titles and summaries. The Verge Claude Opus 4.7 source title includes "amid Mythos Preview buzz" which the digest omits — not a factual error, just scope trimming. The North Korea Dark Reading item adds "Sapphire Sleet" to the title; the threat actor name is confirmed in the source summary.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All ArXiv URLs and titles match the digest. Author lists and abstract claims are internally consistent. Specific quantitative claims (AGILE's 37.74% ASR gain, Cognitive Companion's AUROC 0.840, RiskWebWorld's 1,513 tasks, 16.2% RL improvement) are precise enough to originate from the papers rather than being fabricated; nothing in the available abstracts contradicts them. The Neuro-Symbolic AI survey's "103 publications" figure is confirmed in the source abstract.

---

### Part 3: Security Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Activation-Guided Local Editing for Jailbreaking Attacks]** — The security digest labels this paper "*ArXiv cs.AI*" but the source JSON lists cs.CR as the primary tag (with cs.AI and cs.CL as secondary). The primary classification is computer security (cs.CR), consistent with its placement in the AI Security Research section. Minor misattribution of tag; no factual content error.

**[Critical Nginx UI Auth Bypass Flaw Now Actively Exploited]** — Security digest enumerates specific attacker capabilities ("restart, modify, and delete NGINX configuration files") that do not appear in the source summary, which states only "full server takeover without authentication." These specifics are consistent with the general claim but extend beyond what the source summary provides. Flag as added detail not directly sourced from the available summary text.

All other security digest articles: URLs exact-match source JSON, outlet attributions are correct (BleepingComputer, Dark Reading, The Hacker News confirmed), and summaries stay within source facts.

---

### Overall Summary
The three artifacts are in good shape. One clear factual error exists in the news digest: the Japan Times article title incorrectly pluralizes "ruling" as "rulings." The security digest has two minor notes — an ArXiv tag misattribution (cs.AI vs. cs.CR primary) and a summary that elaborates slightly beyond the source text for the Nginx UI item — neither rises to a factual inaccuracy. Paper summaries are clean. The single correction required is the Japan Times title in the news digest.
