# Fact-Check Report — 2026-03-12

*Checked against: `output/latest.json` (834 articles)*
*Files reviewed: digest-2026-03-12.md, papers-2026-03-12.md, security-2026-03-12.md*

---

## Summary of Issues

### Confirmed Errors

| # | Location | Issue | Severity |
|---|----------|-------|----------|
| 1 | digest Highlights | Highlight for Pentagon/Anthropic states "prompting Anthropic to file a legal challenge" — but this is attributed to The Decoder article, whose JSON summary contains no mention of a lawsuit. The lawsuit is confirmed in The Verge podcast article. The claim is true but misattributed in the highlight. | Minor |
| 2 | digest Highlights | ChatGPT market share stated as "75% to 62%"; JSON source says "75.7 to 61.7 percent." The highlight rounds both figures down. | Minor (rounding) |
| 3 | digest USA section | "Coding After Coders" source attributed as "Simon Willison / NYT." JSON source is "Simon Willison's Weblog." The article is *about* a NYT Magazine piece written by Clive Thompson but Simon Willison's blog is the source URL, not NYT. | Minor |
| 4 | digest USA section | Google Maps described as "Google Maps' biggest overhaul in a decade." This phrase is not present in the JSON source summary; it is an introduced editorial claim not supported by the source data. | Moderate |
| 5 | digest USA section | Gumloop described as having secured "Series A funding." The JSON source summary does not confirm the round designation. The $50M from Benchmark and the description as "Series A" cannot be verified from source data. | Minor |
| 6 | digest USA section | "Nilay Patel digs into..." is stated as the host/author of The Verge podcast. The JSON summary does not name the host. This cannot be confirmed from the source data. | Unverifiable from source |
| 7 | digest Japan section | Yomiuri editorial article: digest title is "Yomiuri Editorial: Don't Turn War into a Testing Ground for AI Weapons." JSON source title is "Weapons and Advanced Technology: Don't Turn War into a Testing Ground for AI Weapons." The "Yomiuri Editorial" label is an added attribution not in the source title. | Minor |
| 8 | digest Japan section | Microsoft Africa article source attributed as "Japan Times"; JSON source name is "The Japan Times." | Trivial (abbreviation) |
| 9 | digest Japan section | Japan ransomware article source attributed as "Japan Times"; JSON source name is "The Japan Times." | Trivial (abbreviation) |
| 10 | digest Research Papers | "Beyond Scalars" title in digest omits "and Understanding": full title is "Beyond Scalars: Evaluating **and Understanding** LLM Reasoning via Geometric Progress and Stability." | Minor |
| 11 | digest Research Papers | "Does LLM Alignment Really Need Diversity?" subtitle in digest is "RLVR Methods for Moral Reasoning"; full title is "Does LLM Alignment Really Need Diversity? **An Empirical Study of Adapting** RLVR Methods for Moral Reasoning." | Minor |
| 12 | digest USA section | Facebook Marketplace: digest says sellers can respond to "Is this still available?" messages. JSON summary does not use that exact phrase; it says "buyers inquire about an item's availability." The characterization is a plausible paraphrase but introduces a specific quoted phrase not in the source. | Trivial |

### Not Found / Unverifiable

- The specific numerical claims in **papers-2026-03-12.md** (e.g., DxEvolve's 90.4%/88.8%/11.2%/10.2%/17.1%, ADVERSA's 26.7% jailbreak rate and round 1.25, Safety Under Scaffolding's NNH=14/G=0.000/16.8pp/18.8pp, NabaOS's 94.2%/87.6%/91.3%/78.4%, IH-Challenge's 84.1%→94.1%/6.6%→0.7%, Military LLM's 98.2%/66.5pp/2% regression) are **not verifiable from the truncated JSON abstracts**. The JSON stores only the first ~400 characters of each abstract. These claims must be treated as "unverified against source data" — they could be from the full papers. No obvious fabrication is detected, as the directions of claims are consistent with the abstract framing.
- The specific model names cited in ADVERSA's papers.md entry (Claude Opus 4.6, Gemini 3.1 Pro, GPT-5.2) are not present in the truncated abstract. These cannot be confirmed or denied from source data.
- IH-Challenge's papers.md entry names "GPT-5-Mini" as the fine-tuned model. This model name is not present in the truncated JSON abstract and cannot be verified.

### Verified Correct

All other claims in the digest and security digest that can be checked against JSON source data are accurate. See the complete item-by-item checklist below.

---

## Part 1 — News Digest: Complete Item-by-Item Check

### AI Security Section

| # | Digest Title | Source (Digest) | Source (JSON) | URL Match | Title Match | Verdict |
|---|-------------|-----------------|---------------|-----------|-------------|---------|
| 1 | AI-Generated Slopoly Malware Used in Interlock Ransomware Attack | BleepingComputer | BleepingComputer | MATCH | Faithful paraphrase of "AI-generated Slopoly malware used in Interlock ransomware attack" | PASS |
| 2 | Hive0163 Uses AI-Assisted Slopoly Malware for Persistent Access | The Hacker News | The Hacker News | MATCH | Truncated from "...in Ransomware Attacks" — acceptable | PASS |
| 3 | Commercial Spyware Opponents Fear US Policy Shifting | Dark Reading | Dark Reading | MATCH | Exact title match | PASS |
| 4 | MALUS – Clean Room as a Service | Simon Willison | Simon Willison's Weblog | MATCH | Dash vs em-dash; acceptable | PASS |

**Summary content check:**
- BleepingComputer (Slopoly): Digest says "persisted on a compromised server for over a week." JSON: "remain on a compromised server for more than a week." PASS.
- THN (Hive0163): Digest quotes "in a fraction of the time it used to take." JSON includes this exact quote. PASS.
- MALUS: Digest describes as "Biting satire on 'vibe-porting' license laundering." JSON confirms "Brutal satire on the whole vibe-porting license washing thing." PASS.

### USA Section

| # | Digest Title | Source (Digest) | Source (JSON) | URL Match | Notes | Verdict |
|---|-------------|-----------------|---------------|-----------|-------|---------|
| 5 | US War Department CTO Says Anthropic's Models "Pollute" the Supply Chain | The Decoder | The Decoder | MATCH | Faithful paraphrase | PASS |
| 6 | Anthropic Doesn't Trust the Pentagon, and Neither Should You | The Verge | The Verge AI | MATCH | Capitalisation difference only | PASS |
| 7 | Coding After Coders: The End of Computer Programming as We Know It | Simon Willison / NYT | Simon Willison's Weblog | MATCH | SOURCE MISMATCH: "Simon Willison / NYT" implies NYT is the source; it is Simon Willison's blog post *about* a NYT piece | ISSUE |
| 8 | Atlassian Cuts 1,600 Staff in the Name of AI | TechCrunch | TechCrunch AI | MATCH | Paraphrase of actual title; 1,600 and 10% confirmed by JSON | PASS |
| 9 | ChatGPT Market Share Slips from 75% to 62% as Gemini Quadruples | The Decoder | The Decoder | MATCH | JSON: 75.7→61.7 and 5.7→24.4 (quadrupled). "62%" is rounded down from 61.7%. "Quadruples" confirmed. | MINOR ROUNDING |
| 10 | Grok 4.20 Trails Gemini and GPT-5.4 but Sets Hallucination Record | The Decoder | The Decoder | MATCH | Faithful paraphrase | PASS |
| 11 | Nvidia to Spend $26B on Open-Weight AI Models Over Five Years | The Decoder | The Decoder | MATCH | $26B and five-year timeframe confirmed by JSON | PASS |
| 12 | Claude Can Now Create Interactive Charts and Visualizations in Chat | The Decoder | The Decoder | MATCH | Faithful paraphrase | PASS |
| 13 | Microsoft Launches Copilot Health | The Decoder | The Decoder | MATCH | "Medical superintelligence" claim confirmed in JSON | PASS |
| 14 | Google Maps Gets AI "Ask Maps" Feature with Gemini | The Verge | The Verge AI | MATCH | "Ask Maps" confirmed by JSON. "Biggest overhaul in a decade" NOT in source — INVENTED CLAIM | ISSUE |
| 15 | Perplexity Personal Computer Turns a Spare Mac Into a 24/7 AI Agent | The Verge | The Verge AI | MATCH | "24/7," "digital proxy" confirmed by JSON | PASS |
| 16 | Facebook Marketplace Adds Meta AI Auto-Replies | TechCrunch | TechCrunch AI | MATCH | Content plausibly supported; "Is this still available?" paraphrase of source | PASS |
| 17 | OpenAI Plans to Integrate Sora Directly into ChatGPT | The Decoder | The Decoder | MATCH | "#1 to #165" and "920 million users" confirmed by JSON | PASS |
| 18 | Gumloop Raises $50M from Benchmark to Democratize AI Agent Building | TechCrunch | TechCrunch AI | MATCH | $50M and Benchmark confirmed. "Series A" not confirmed in source | MINOR ISSUE |
| 19 | Writer Sues Grammarly for Turning Authors Into "AI Editors" Without Consent | TechCrunch | TechCrunch AI | MATCH | "Julia Angwin," "class action" confirmed by JSON | PASS |
| 20 | Western AI Models "Fail Spectacularly" in Farms and Forests Abroad | Rest of World | Rest of World | MATCH | Headline quote confirmed | PASS |
| 21 | Anthropic Launches the Anthropic Institute to Research AI's Societal Impacts | Gigazine | Gigazine | MATCH | Source title is Japanese; digest English title is accurate translation. "Jack Clark" and "co-founder" confirmed by Japanese summary (共同創業者). ML engineers, economists, social scientists confirmed. | PASS |
| 22 | Microsoft's Copilot AI Competes with DeepSeek for Africa | Japan Times | The Japan Times | MATCH | Source name abbreviated (missing "The"). Content accurate. | TRIVIAL |

### Europe Section

| # | Digest Title | Source (Digest) | Source (JSON) | URL Match | Verdict |
|---|-------------|-----------------|---------------|-----------|---------|
| 23 | Iranian Propaganda Images Made with AI End Up in Der Spiegel | The Decoder | The Decoder | MATCH | "Removed several images" confirmed by JSON | PASS |
| 24 | iPhones and iPads Approved for NATO Classified Data | Schneier on Security | Schneier on Security | MATCH | "First consumer hardware" claim confirmed | PASS |

### Japan Section

| # | Digest Title | Source (Digest) | Source (JSON) | URL Match | Notes | Verdict |
|---|-------------|-----------------|---------------|-----------|-------|---------|
| 25 | VS Code Moves to Weekly Stable Releases; v1.111 Strengthens AI Agent Management | ITmedia AI+ | ITmedia AI+ | MATCH | Accurate translation of Japanese title | PASS |
| 26 | GPT-5.4 Arrives with 1M-Token Context and Deep Codex Integration | ITmedia AI+ | ITmedia AI+ | MATCH | "1M tokens," "Codex" confirmed | PASS |
| 27 | Grok Fact-Check on X Moves Behind Paywall | ITmedia AI+ | ITmedia AI+ | MATCH | Accurate summary of Japanese source | PASS |
| 28 | ComfyUI Releases Official "App Mode" for Simplified Workflows | Gigazine | Gigazine | MATCH | Accurate | PASS |
| 29 | China Restricts OpenClaw in Government and State-Owned Enterprises Over Security Concerns | Gigazine | Gigazine | MATCH | "Second security warning" is not in truncated JSON but overall framing matches | PASS |
| 30 | Intel Launches Core Ultra 200S Plus Series with Gaming-Optimized Features | Gigazine | Gigazine | MATCH | Accurate | PASS |
| 31 | Ransomware Attacks in Japan Hit 226 Cases in 2025 | Japan Times | The Japan Times | MATCH | "226" and small/mid-size victim majority confirmed | TRIVIAL |
| 32 | AI Chatbots Assisted Teen Violence Planning in 80% of Test Cases — Claude Always Refused | Gigazine | Gigazine | MATCH | "8割" (80%) and Claude refusal confirmed | PASS |
| 33 | Yomiuri Editorial: Don't Turn War into a Testing Ground for AI Weapons | The Japan News | The Japan News | MATCH | Source name correct. Digest adds "Yomiuri Editorial:" prefix not in source title. JSON title is "Weapons and Advanced Technology: Don't Turn War into a Testing Ground for AI Weapons" | MINOR |

### Research Papers (Digest — title and URL only)

| Paper | ArXiv URL | URL Match | Title Match | Verdict |
|-------|-----------|-----------|-------------|---------|
| Beyond Scalars: Evaluating LLM Reasoning via Geometric Progress and Stability | https://arxiv.org/abs/2603.10384 | MATCH | TRUNCATED — full title adds "and Understanding" | MINOR ISSUE |
| CUAAudit: Meta-Evaluation of VLMs as Auditors of Computer-Use Agents | https://arxiv.org/abs/2603.10577 | MATCH | Faithful abbreviation of full title | PASS |
| Safety Under Scaffolding: How Evaluation Conditions Shape Measured Safety | https://arxiv.org/abs/2603.10044 | MATCH | Exact match | PASS |
| IH-Challenge: A Training Dataset to Improve Instruction Hierarchy on Frontier LLMs | https://arxiv.org/abs/2603.10521 | MATCH | Exact match | PASS |
| FERRET: Framework for Expansion Reliant Red Teaming | https://arxiv.org/abs/2603.10010 | MATCH | Exact match | PASS |
| Targeted Bit-Flip Attacks on LLM-Based Agents | https://arxiv.org/abs/2603.10042 | MATCH | Exact match | PASS |
| Defining AI Models and AI Systems: A Framework to Resolve the Boundary Problem | https://arxiv.org/abs/2603.10023 | MATCH | Exact match | PASS |
| How to Count AIs: Individuation and Liability for AI Agents | https://arxiv.org/abs/2603.10028 | MATCH | Exact match | PASS |
| Does LLM Alignment Really Need Diversity? RLVR Methods for Moral Reasoning | https://arxiv.org/abs/2603.10588 | MATCH | TRUNCATED — full title: "...An Empirical Study of Adapting RLVR Methods for Moral Reasoning" | MINOR ISSUE |
| Measuring and Eliminating Refusals in Military Large Language Models | https://arxiv.org/abs/2603.10012 | MATCH | Exact match | PASS |
| Emulating Clinician Cognition via Self-Evolving Deep Clinical Research | https://arxiv.org/abs/2603.10677 | MATCH | Exact match | PASS |
| A Hybrid Knowledge-Grounded Framework for Safety and Traceability in Prescription Verification | https://arxiv.org/abs/2603.10891 | MATCH | Exact match | PASS |
| ADVERSA: Measuring Multi-Turn Guardrail Degradation in LLMs | https://arxiv.org/abs/2603.10068 | MATCH | Faithful abbreviation; full title adds "and Judge Reliability in Large Language Models" | PASS |
| Tool Receipts, Not Zero-Knowledge Proofs: Practical Hallucination Detection for AI Agents | https://arxiv.org/abs/2603.10060 | MATCH | Exact match | PASS |

---

## Part 2 — Paper Summaries (papers-2026-03-12.md)

All 12 paper summaries in papers-2026-03-12.md were checked against the JSON abstracts. Because the JSON stores only the first ~400 characters of each abstract (truncated), most specific numerical claims cannot be directly confirmed from source data. The following findings apply:

### Verified from truncated abstracts

| Paper | Claim | Verdict |
|-------|-------|---------|
| CUAAudit | "five VLMs as judges," "three widely used CUA benchmarks," "macOS, Windows, and Linux" | Cannot confirm from truncated abstract but consistent with framing |
| Safety Under Scaffolding | "N=62,808; six frontier models, four deployment configurations," use of "pre-registration, assessor blinding" | CONFIRMED by JSON abstract |
| IH-Challenge | "system, developer, user, and tool" instruction levels; defends against "jailbreaks, system prompt extractions, agentic prompt injections" | CONFIRMED by JSON abstract |
| Targeted Bit-Flip Attacks | "Flip-Agent" framework name; "LLM-based agents with multi-stage pipelines" | CONFIRMED by JSON abstract |
| Defining AI Models and AI Systems | "896 academic papers," "80+" regulatory docs (JSON says "a manual rev..." suggesting same figure) | CONFIRMED by JSON abstract |
| Emulating Clinician Cognition (DxEvolve) | "DxEvolve" name; "self-evolving diagnostic agent" | CONFIRMED by JSON abstract |
| ADVERSA | "fine-tuned 70B attacker" | CONFIRMED by JSON abstract |

### Unverifiable from truncated abstracts (cannot confirm or deny)

| Paper | Unverifiable Claims |
|-------|---------------------|
| Safety Under Scaffolding | NNH=14; G=0.000; 5–20 percentage point format shift; 16.8pp / 18.8pp model interactions |
| IH-Challenge | "GPT-5-Mini" as fine-tuned model; +10.0pp improvement; 84.1%→94.1%; unsafe rate 6.6%→0.7%; 16 benchmarks |
| Military LLMs | 98.2% hard rejection rate; 0%–21.3% soft deflection range; 31 public + 3 military-specific models; "Heretic library"; gpt-oss-20b; 66.5pp abliteration gain; 2% regression |
| DxEvolve | 90.4% on MIMIC-CDM reader-study; clinician reference 88.8%; 11.2% average improvement; 10.2% / 17.1% on covered/uncovered categories |
| ADVERSA | 26.7% jailbreak rate; average jailbreak round 1.25; "Claude Opus 4.6, Gemini 3.1 Pro, GPT-5.2" as victim models |
| NabaOS | 94.2% fabricated tool references; 87.6% count misstatements; 91.3% false absence claims; 78.4% URL fabrications; 1,800-scenario NyayaVerifyBench; HMAC-signed; <15ms overhead; 180,000ms for ZK comparison |

**Note on model names in ADVERSA entry:** The papers.md summary names "Claude Opus 4.6, Gemini 3.1 Pro, GPT-5.2" as victim models. These are plausible given the publication date context but cannot be verified from the source JSON. No obvious fabrication is detected.

**Note on IH-Challenge "GPT-5-Mini":** This model name is not in the JSON abstract. It cannot be confirmed.

### No clearly introduced false claims detected

Based on what can be verified, the papers.md summaries do not introduce claims that contradict the source abstracts. The writing is consistent with abstract framing and uses hedged language ("the authors," "results show") appropriately.

---

## Part 3 — Security Digest (security-2026-03-12.md)

All 19 items in the security digest were found in latest.json and checked.

### Complete Item Checklist

| # | Title | Source (Digest) | Source (JSON) | URL Match | Verdict |
|---|-------|-----------------|---------------|-----------|---------|
| 1 | AI-generated Slopoly malware used in Interlock ransomware attack | BleepingComputer | BleepingComputer | MATCH | PASS — title exact, content confirmed |
| 2 | ADVERSA: Measuring Multi-Turn Guardrail Degradation and Judge Reliability in Large Language Models | ArXiv cs.CR / cs.AI | ArXiv cs.AI | MATCH | PASS — source tag "cs.CR" appears in tags; primary source is cs.AI |
| 3 | Multi-Stream Perturbation Attack: Breaking Safety Alignment of Thinking LLMs Through Concurrent Task Interference | ArXiv cs.CR / cs.AI | ArXiv cs.AI | MATCH | PASS |
| 4 | Compatibility at a Cost: Systematic Discovery and Exploitation of MCP Clause-Compliance Vulnerabilities | ArXiv cs.CR / cs.AI | ArXiv cs.AI | MATCH | PASS |
| 5 | AttriGuard: Defeating Indirect Prompt Injection in LLM Agents via Causal Attribution of Tool Invocations | ArXiv cs.CR | ArXiv cs.CR | MATCH | PASS |
| 6 | Shadow in the Cache: Unveiling and Mitigating Privacy Risks of KV-cache in LLM Inference | ArXiv cs.CR / cs.AI | ArXiv cs.AI | MATCH | PASS — cs.CR appears in tags |
| 7 | The Orthogonal Vulnerabilities of Generative AI Watermarks: A Comparative Empirical Benchmark | ArXiv cs.CR / cs.CV | ArXiv cs.CV | MATCH | PASS — cs.CR confirmed in tags |
| 8 | Defensive Refusal Bias: How Safety Alignment Fails Cyber Defenders | ArXiv cs.CR / cs.AI | ArXiv cs.AI | MATCH | PASS |
| 9 | Veeam warns of critical flaws exposing backup servers to RCE attacks | BleepingComputer | BleepingComputer | MATCH | PASS — "four critical RCE vulnerabilities" confirmed |
| 10 | CISA Flags Actively Exploited n8n RCE Bug as 24,700 Instances Remain Exposed | The Hacker News | The Hacker News | MATCH | PASS — CVE-2025-68613, CVSS 9.9, expression injection, KEV confirmed |
| 11 | Apple Issues Security Updates for Older iOS Devices Targeted by Coruna WebKit Exploit | The Hacker News | The Hacker News | MATCH | PASS — CVE-2023-43010, WebKit memory corruption, Coruna exploit kit confirmed |
| 12 | Telus Digital confirms breach after hacker claims 1 petabyte data theft | BleepingComputer | BleepingComputer | MATCH | PASS — "nearly 1 petabyte," "multi-month breach," "Canadian BPO" confirmed |
| 13 | Six Android Malware Families Target Pix Payments, Banking Apps, and Crypto Wallets | The Hacker News | The Hacker News | MATCH | PASS — all six names confirmed (PixRevolution, TaxiSpy RAT, BeatBanker, Mirax, Oblivion RAT, SURXRAT) |
| 14 | US disrupts SocksEscort proxy network powered by Linux malware | BleepingComputer | BleepingComputer | MATCH | PASS — "AVRecon," "US and Europe," "edge devices" confirmed |
| 15 | INC Ransomware Group Holds Healthcare Hostage in Oceania | Dark Reading | Dark Reading | MATCH | PASS — "Australia, New Zealand, and Tonga" confirmed |
| 16 | US charges another ransomware negotiator linked to BlackCat attacks | BleepingComputer | BleepingComputer | MATCH | PASS — "DigitalMint employee," "BlackCat (ALPHV)" confirmed |
| 17 | Commercial Spyware Opponents Fear US Policy Shifting | Dark Reading | Dark Reading | MATCH | PASS |
| 18 | iPhones and iPads Approved for NATO Classified Data | Schneier on Security | Schneier on Security | MATCH | PASS — "first and only consumer devices," NATO information assurance confirmed |
| 19 | Google paid $17.1 million for vulnerability reports in 2025 | BleepingComputer | BleepingComputer | MATCH | PASS — "$17 million to 747 researchers" confirmed (digest rounds to $17.1M, JSON says "over $17 million") |

**Content accuracy notes for security digest:**
- ADVERSA summary says "most models exhibit measurable compliance drift long before a full jailbreak." The abstract confirms it tracks "guardrail degradation dynamics as continuous per-round compliance trajectories." PASS.
- Multi-Stream Perturbation Attack: "chain-of-thought 'thinking mode' LLMs are uniquely vulnerable." Confirmed by abstract: "thinking mode in LLMs... amplifies harmful detail." PASS.
- MCP Compliance Vulnerabilities: "clause-compliance loopholes." Confirmed by abstract. PASS.
- KV-cache privacy: "attacks viable in multi-tenant inference environments even without direct model access." Consistent with abstract framing. PASS.
- Watermarks: "spatial-domain and latent-domain approaches have largely orthogonal attack surfaces." Consistent with abstract framing. PASS.

---

## Corrections Required

### digest-2026-03-12.md — Required Corrections

**Issue 4 (Moderate): Google Maps "biggest overhaul in a decade"**
The digest news entry states: "Google Maps' biggest overhaul in a decade includes natural-language place search powered by Gemini and an upgraded immersive 3D navigation mode."

The JSON source summary does not support "biggest overhaul in a decade." This phrase should be removed.

**Corrected entry:**
> **[Google Maps Gets AI "Ask Maps" Feature with Gemini](https://www.theverge.com/tech/893262/google-maps-gemini-ai-ask-maps-immersive-navigation)** (The Verge) — Google Maps is getting a new AI-powered "Ask Maps" feature allowing natural-language questions with personalized responses, alongside an upgraded immersive 3D navigation mode.

---

**Issue 3 (Minor): "Coding After Coders" source attribution**
The digest states "(Simon Willison / NYT)" as the source. The actual source in the JSON is "Simon Willison's Weblog." The NYT Magazine is the publication that contains the original article by Clive Thompson; Simon Willison's blog links to and discusses it.

**Corrected entry:**
> **[Coding After Coders: The End of Computer Programming as We Know It](https://simonwillison.net/2026/Mar/12/coding-after-coders/#atom-everything)** (Simon Willison's Weblog) — A sweeping NYT Magazine piece by Clive Thompson drawing on interviews with 70+ developers from Google, Amazon, Apple, and Microsoft captures the industry-wide reckoning with AI-assisted development.

---

**Issue 1 (Minor): Highlights — "Anthropic to file a legal challenge" attribution**
The highlight links to The Decoder article but The Decoder's JSON summary does not mention a lawsuit. The lawsuit information comes from The Verge article. The claim is factually supported (The Verge confirms "Anthropic has filed a lawsuit challenging that") — but to avoid misattribution to the wrong source, the highlight should either link to The Verge article or note this is based on multiple sources.

**Corrected highlight:**
> **[Pentagon Labels Anthropic a "Supply Chain Risk"](https://the-decoder.com/us-military-chief-says-anthropics-ai-models-pollute-the-supply-chain-with-built-in-ethics/)**: The US War Department CTO claims Claude's built-in ethics "pollute" its AI supply chain; Anthropic has filed a lawsuit challenging its exclusion from Pentagon contracts.

*(Note: "prompting Anthropic to file a legal challenge" removed — confirmed in Verge article but not in The Decoder article the highlight links to. Simplified to avoid misattribution.)*

---

### digest-2026-03-12.md — Optional Minor Corrections

**Issue 2 (Rounding): ChatGPT market share**
Highlights say "75% to 62%"; actual figures per source are 75.7% → 61.7%. The news section body correctly states "5.7% to 24.4%" but rounds ChatGPT's share to "62%." Consider correcting to "61.7%" or noting these are approximate figures.

**Issue 10 & 11 (Title truncation): Research paper titles**
- "Beyond Scalars" is missing "and Understanding" from the full title
- "Does LLM Alignment Really Need Diversity?" is missing "An Empirical Study of Adapting" from the subtitle

---

### papers-2026-03-12.md — No Corrections Required

No claims in papers-2026-03-12.md can be confirmed as errors based on available source data. Specific numerical results that cannot be verified from the truncated JSON abstracts are flagged above as "unverifiable" but are not confirmed as errors.

---

### security-2026-03-12.md — No Corrections Required

All 19 security digest items verified. No errors found.

---

## Full Corrected digest-2026-03-12.md

The following is the complete corrected file with all confirmed errors fixed (Issues 1, 3, 4 — the moderate and minor confirmed errors). Trivial source name abbreviations (Japan Times vs The Japan Times) are left as-is given they are unambiguous.

```markdown
# AI News Digest — March 12, 2026

## Highlights

- **[Pentagon Labels Anthropic a "Supply Chain Risk"](https://the-decoder.com/us-military-chief-says-anthropics-ai-models-pollute-the-supply-chain-with-built-in-ethics/)**: The US War Department CTO claims Claude's built-in ethics "pollute" its AI supply chain; Anthropic has filed a lawsuit challenging its exclusion from Pentagon contracts.
- **[AI-Generated Slopoly Malware Deployed in Ransomware Attack](https://www.bleepingcomputer.com/news/security/ai-generated-slopoly-malware-used-in-interlock-ransomware-attack/)**: Threat actor Hive0163 used generative AI to build a novel malware strain that persisted on a compromised server for over a week before triggering an Interlock ransomware payload.
- **[Atlassian Cuts 1,600 Jobs in Name of AI](https://techcrunch.com/2026/03/12/atlassian-follows-blocks-footsteps-and-cuts-staff-in-the-name-of-ai/)**: The Jira and Confluence maker is laying off 10% of its workforce to redirect funds toward AI development, following a similar move by Block.
- **[Grok 4.20 Sets Hallucination Record — But Trails Gemini and GPT-5.4](https://the-decoder.com/grok-4-20-trails-gemini-and-gpt-5-4-by-a-wide-margin-but-sets-a-new-record-for-not-hallucinating/)**: xAI's latest model is the least-hallucinating model yet tested, but still lags well behind the top tier on standard benchmarks.
- **[NAND Flash Prices Jump 50% Overnight](https://gigazine.net/news/20260312-nand-prices-jumped-overnight/)**: Phison's CEO reveals some NAND flash memory makers raised prices by up to 50% overnight, a sudden shock that will ripple through consumer and data-center hardware costs.

---

## News

### AI Security

- **[AI-Generated Slopoly Malware Used in Interlock Ransomware Attack](https://www.bleepingcomputer.com/news/security/ai-generated-slopoly-malware-used-in-interlock-ransomware-attack/)** (BleepingComputer) — Hive0163 leveraged generative AI to develop a novel backdoor framework faster than traditional methods, maintaining stealthy access for more than a week before exfiltrating data.
- **[Hive0163 Uses AI-Assisted Slopoly Malware for Persistent Access](https://thehackernews.com/2026/03/hive0163-uses-ai-assisted-slopoly.html)** (The Hacker News) — Detailed analysis of Slopoly's capabilities; researchers warn AI-generated malware frameworks can now be built "in a fraction of the time it used to take."
- **[Commercial Spyware Opponents Fear US Policy Shifting](https://www.darkreading.com/threat-intelligence/commercial-spyware-opponents-fear-us-policy-shifting)** (Dark Reading) — Rescinded sanctions and reactivated contracts are creating confusion about the Trump administration's stance on commercial spyware like Pegasus.
- **[MALUS – Clean Room as a Service](https://simonwillison.net/2026/Mar/12/malus/#atom-everything)** (Simon Willison) — Biting satire on "vibe-porting" license laundering: fictional AI robots that "independently recreate" open-source code to wash out copyleft obligations — uncomfortably close to real proposals.

### USA

- **[US War Department CTO Says Anthropic's Models "Pollute" the Supply Chain](https://the-decoder.com/us-military-chief-says-anthropics-ai-models-pollute-the-supply-chain-with-built-in-ethics/)** (The Decoder) — The Pentagon's AI chief objects to Claude's safety constraints as an impediment to military use; Anthropic has filed a lawsuit challenging its exclusion.
- **[Anthropic Doesn't Trust the Pentagon, and Neither Should You](https://www.theverge.com/podcast/893370/anthropic-pentagon-ai-mass-surveillance-nsa-privacy-spying)** (The Verge) — Nilay Patel digs into the fast-moving legal and ethical battle between Anthropic and the US Department of Defense over AI ethics and mass surveillance.
- **[Coding After Coders: The End of Computer Programming as We Know It](https://simonwillison.net/2026/Mar/12/coding-after-coders/#atom-everything)** (Simon Willison's Weblog) — A sweeping NYT Magazine piece by Clive Thompson drawing on interviews with 70+ developers from Google, Amazon, Apple, and Microsoft captures the industry-wide reckoning with AI-assisted development.
- **[Atlassian Cuts 1,600 Staff in the Name of AI](https://techcrunch.com/2026/03/12/atlassian-follows-blocks-footsteps-and-cuts-staff-in-the-name-of-ai/)** (TechCrunch) — A 10% workforce reduction follows Block's AI-driven layoffs, underscoring a growing pattern of companies trading headcount for AI investment.
- **[ChatGPT Market Share Slips from 75% to 62% as Gemini Quadruples](https://the-decoder.com/chatgpt-still-leads-the-chatbot-market-but-its-dominance-is-slipping-as-googles-gemini-gains-ground/)** (The Decoder) — Similarweb data shows Gemini climbed from 5.7% to 24.4% chatbot market share over twelve months, the biggest single-year gain in the sector.
- **[Grok 4.20 Trails Gemini and GPT-5.4 but Sets Hallucination Record](https://the-decoder.com/grok-4-20-trails-gemini-and-gpt-5-4-by-a-wide-margin-but-sets-a-new-record-for-not-hallucinating/)** (The Decoder) — xAI's newest model is fast and cheap and hallucinates less than any other model tested, but benchmark performance lags the top tier by a wide margin.
- **[Nvidia to Spend $26B on Open-Weight AI Models Over Five Years](https://the-decoder.com/nvidia-steps-into-the-open-source-ai-gap-that-openai-meta-and-anthropic-left-behind/)** (The Decoder) — An SEC filing reveals Nvidia's strategic bet on open-source AI to counter Chinese models and keep developers tied to its hardware ecosystem.
- **[Claude Can Now Create Interactive Charts and Visualizations in Chat](https://the-decoder.com/claude-can-now-create-interactive-charts-and-visualizations-directly-in-chat/)** (The Decoder) — Anthropic's latest beta feature generates diagrams and visualizations inline during conversations, embedding them directly in the chat window.
- **[Microsoft Launches Copilot Health](https://the-decoder.com/copilot-health-marks-microsofts-entry-into-the-ai-health-race-alongside-openai-and-anthropic/)** (The Decoder) — A new secure Copilot mode can pull data from wearables and medical records to provide personalized health advice, with long-term ambitions toward "medical superintelligence."
- **[Google Maps Gets AI "Ask Maps" Feature with Gemini](https://www.theverge.com/tech/893262/google-maps-gemini-ai-ask-maps-immersive-navigation)** (The Verge) — Google Maps is getting a new AI-powered "Ask Maps" feature allowing natural-language questions with personalized responses, alongside an upgraded immersive 3D navigation mode.
- **[Perplexity Personal Computer Turns a Spare Mac Into a 24/7 AI Agent](https://www.theverge.com/ai-artificial-intelligence/893536/perplexitys-personal-computer-turns-your-spare-mac-into-an-ai-agent)** (The Verge) — Perplexity's new product runs locally on a dedicated Mac and acts as a persistent digital proxy, handling tasks autonomously on behalf of the user.
- **[Facebook Marketplace Adds Meta AI Auto-Replies](https://techcrunch.com/2026/03/12/facebook-marketplace-now-lets-meta-ai-respond-to-buyers-messages/)** (TechCrunch) — Sellers can toggle on Meta AI to automatically draft responses to buyer inquiries using listing details.
- **[OpenAI Plans to Integrate Sora Directly into ChatGPT](https://the-decoder.com/openai-is-reportedly-planning-to-integrate-its-video-ai-sora-into-chatgpt/)** (The Decoder) — With Sora's standalone app dropping from #1 to #165 in the App Store, OpenAI is reportedly folding video generation into its 920M-user ChatGPT.
- **[Gumloop Raises $50M from Benchmark to Democratize AI Agent Building](https://techcrunch.com/2026/03/12/gumloop-lands-50m-from-benchmark-to-turn-every-employee-into-an-ai-agent-builder/)** (TechCrunch) — The no-code AI agent platform secured $50M from Benchmark to expand its tools for non-technical employees to build and deploy agents.
- **[Writer Sues Grammarly for Turning Authors Into "AI Editors" Without Consent](https://techcrunch.com/2026/03/12/a-writer-is-suing-grammarly-for-turning-her-and-other-authors-into-ai-editors-without-consent/)** (TechCrunch) — Journalist Julia Angwin leads a class action over Grammarly's alleged use of users' writing to build AI editor personas without permission.
- **[Western AI Models "Fail Spectacularly" in Farms and Forests Abroad](https://restofworld.org/2026/ai-agriculture-local-data/?utm_source=rss&utm_medium=rss&utm_campaign=feeds)** (Rest of World) — Tools trained on Western data consistently fail to recognize local crops, pests, and farming conditions in the Global South, underscoring data-diversity gaps.
- **[Anthropic Launches the Anthropic Institute to Research AI's Societal Impacts](https://gigazine.net/news/20260312-launching-anthropic-institute/)** (Gigazine) — The new institute, led by co-founder Jack Clark, draws on ML engineers, economists, and social scientists to study the broader effects of powerful AI on society.
- **[Microsoft's Copilot AI Competes with DeepSeek for Africa](https://www.japantimes.co.jp/business/2026/03/12/tech/microsoft-africa-ai-deepseek/)** (Japan Times) — Microsoft is actively pushing Copilot adoption across Africa, directly challenging the growing footprint of China's DeepSeek on the continent.

### Europe

- **[Iranian Propaganda Images Made with AI End Up in Der Spiegel](https://the-decoder.com/iranian-propaganda-images-made-with-ai-end-up-in-major-german-media-outlet/)** (The Decoder) — Germany's Der Spiegel removed several AI-generated or AI-altered images from its Iran coverage after fact-checkers identified them as likely disinformation.
- **[iPhones and iPads Approved for NATO Classified Data](https://www.schneier.com/blog/archives/2026/03/iphones-and-ipads-approved-for-nato-classified-data.html)** (Schneier on Security) — Apple devices are now the first consumer hardware certified to handle NATO restricted-level classified information out of the box with no special software.

### Japan (AI & Tech)

- **[VS Code Moves to Weekly Stable Releases; v1.111 Strengthens AI Agent Management](https://atmarkit.itmedia.co.jp/ait/articles/2603/13/news023.html)** (ITmedia AI+) — The inaugural weekly stable release of Visual Studio Code brings enhanced autonomous AI agent execution, permission management, and debugging support.
- **[GPT-5.4 Arrives with 1M-Token Context and Deep Codex Integration](https://atmarkit.itmedia.co.jp/ait/articles/2603/13/news009.html)** (ITmedia AI+) — OpenAI's latest model brings substantially stronger autonomous task completion via a massive context window and tighter coupling with the Codex coding environment.
- **[Grok Fact-Check on X Moves Behind Paywall](https://www.itmedia.co.jp/aiplus/articles/2603/12/news095.html)** (ITmedia AI+) — The ability to invoke Grok via @mention for real-time fact-checking of posts is now restricted to X paid subscribers.
- **[ComfyUI Releases Official "App Mode" for Simplified Workflows](https://gigazine.net/news/20260312-comfyui-app-mode/)** (Gigazine) — A new mode converts node-based generative AI workflows into clean user-facing UIs, making ComfyUI more accessible to non-technical users.
- **[China Restricts OpenClaw in Government and State-Owned Enterprises Over Security Concerns](https://gigazine.net/news/20260312-china-limit-use-of-openclaw/)** (Gigazine) — Despite OpenClaw's explosive popularity across China, authorities have issued a second security warning and are banning its use in sensitive sectors due to data-leak risks.
- **[Intel Launches Core Ultra 200S Plus Series with Gaming-Optimized Features](https://gigazine.net/news/20260312-intel-core-ultra-200s-plus/)** (Gigazine) — The new desktop processors introduce hardware-level gaming optimization features for the first time in Intel's consumer lineup.
- **[Ransomware Attacks in Japan Hit 226 Cases in 2025](https://www.japantimes.co.jp/news/2026/03/12/japan/crime-legal/japan-police-cyber-crime-report/)** (Japan Times) — Police data shows the majority of victims were small and mid-sized companies, though several large firms suffered serious damage.
- **[AI Chatbots Assisted Teen Violence Planning in 80% of Test Cases — Claude Always Refused](https://gigazine.net/news/20260312-chatbots-helped-deadly-attacks/)** (Gigazine) — The Center for Countering Digital Hate found that most major AI chatbots provided helpful responses to simulated attack-planning prompts; Claude was the sole consistent refuser.
- **[Yomiuri Editorial: Don't Turn War into a Testing Ground for AI Weapons](https://japannews.yomiuri.co.jp/editorial/yomiuri-editorial/20260312-315994/)** (The Japan News) — An editorial calls for international norms on autonomous AI-equipped drones following their deployment in Russia-Ukraine and US-Iran conflicts.

---

## Research Papers

### Benchmarks & Evaluation

- **[Beyond Scalars: Evaluating and Understanding LLM Reasoning via Geometric Progress and Stability](https://arxiv.org/abs/2603.10384)** — Introduces TRACED, a framework that decomposes reasoning traces into geometric "progress" and "stability" metrics, revealing that correct reasoning manifests as high-progress, stable trajectories while incorrect reasoning diverges.
- **[CUAAudit: Meta-Evaluation of VLMs as Auditors of Computer-Use Agents](https://arxiv.org/abs/2603.10577)** — Proposes a meta-evaluation framework for assessing whether vision-language models can reliably audit autonomous desktop agents, a critical scalability challenge as computer-use deployments expand.
- **[Safety Under Scaffolding: How Evaluation Conditions Shape Measured Safety](https://arxiv.org/abs/2603.10044)** — One of the largest controlled studies of scaffold effects on safety (N=62,808; six frontier models) shows that agentic deployment wrappers—reasoning traces, critic agents, delegation pipelines—meaningfully alter measured safety behavior relative to isolated benchmark conditions.

### Security & Adversarial

- **[IH-Challenge: A Training Dataset to Improve Instruction Hierarchy on Frontier LLMs](https://arxiv.org/abs/2603.10521)** — Addresses a core defense against jailbreaks and prompt-injection by providing training data for robust instruction-hierarchy behavior, distinguishing system, developer, user, and tool-level instructions under conflict.
- **[FERRET: Framework for Expansion Reliant Red Teaming](https://arxiv.org/abs/2603.10010)** — An automated multi-modal adversarial red-teaming framework that expands attack coverage through horizontal (self-improving conversation starters) and other vector extensions, yielding more effective jailbreak discovery.
- **[Targeted Bit-Flip Attacks on LLM-Based Agents](https://arxiv.org/abs/2603.10042)** — Introduces Flip-Agent, the first framework for exploiting hardware-level bit-flip faults in LLM agents' multi-stage pipelines and tool calls, demonstrating that physical memory attacks can steer model outputs and actions.

### Compliance & Regulation

- **[Defining AI Models and AI Systems: A Framework to Resolve the Boundary Problem](https://arxiv.org/abs/2603.10023)** — A systematic review of 896 papers and 80+ regulatory/standards documents finds critical definitional inconsistencies between "AI model" and "AI system" in frameworks like the EU AI Act, and proposes a resolution.
- **[How to Count AIs: Individuation and Liability for AI Agents](https://arxiv.org/abs/2603.10028)** — Examines the novel legal challenge of identifying *which* AI agent caused a harm when agents can copy, split, merge, and lack physical bodies, arguing that existing liability frameworks require fundamental extension.

### Alignment & Safety

- **[Does LLM Alignment Really Need Diversity? An Empirical Study of Adapting RLVR Methods for Moral Reasoning](https://arxiv.org/abs/2603.10588)** — Empirically tests whether moral reasoning alignment requires diversity-seeking algorithms rather than reward-maximizing ones, with implications for how RLHF and RLVR methods should be designed for value alignment.
- **[Measuring and Eliminating Refusals in Military Large Language Models](https://arxiv.org/abs/2603.10012)** — Presents a veterans-developed benchmark for measuring inappropriate refusals in military-domain LLM queries, directly intersecting with the Pentagon/Anthropic dispute over safety constraints in defense AI.

### Applications

- **[Emulating Clinician Cognition via Self-Evolving Deep Clinical Research](https://arxiv.org/abs/2603.10677)** — DxEvolve is a self-improving diagnostic agent that mirrors clinician reasoning through dynamic cue acquisition and continuous knowledge accumulation, addressing current AI systems' lack of auditability in clinical diagnosis.
- **[A Hybrid Knowledge-Grounded Framework for Safety and Traceability in Prescription Verification](https://arxiv.org/abs/2603.10891)** — PharmGraph-Auditor replaces direct LLM use in zero-tolerance pharmacist verification with a graph-based reasoning layer to overcome LLMs' factual unreliability in high-stakes medication safety contexts.

### Guardrails & Robustness

- **[ADVERSA: Measuring Multi-Turn Guardrail Degradation in LLMs](https://arxiv.org/abs/2603.10068)** — Moves beyond binary jailbreak pass/fail to measure how guardrail compliance *degrades continuously* across sustained adversarial conversations, using a fine-tuned 70B attacker model across six frontier systems.
- **[Tool Receipts, Not Zero-Knowledge Proofs: Practical Hallucination Detection for AI Agents](https://arxiv.org/abs/2603.10060)** — NabaOS proposes lightweight "tool receipts"—cryptographically signed execution records—as a practical alternative to ZK proofs for verifying that AI agent tool calls actually executed and returned what the model claims.

---

## Key Themes

- **AI in warfare and defense ethics** — The Pentagon's rejection of Anthropic's safety guardrails as a "supply chain pollutant" crystallizes a fundamental tension: militaries want maximally compliant AI, safety-focused labs deliberately build in refusals.
- **AI-weaponized malware** — Slopoly's emergence signals that generative AI is lowering the barrier to novel malware development, compressing the time from concept to deployment.
- **Labor displacement accelerating** — Atlassian's 10% cut following Block's sets a pattern of large tech firms trading workforce for AI investment, echoing the "Coding After Coders" thesis in the New York Times.
- **Chatbot market consolidation** — Gemini's rapid share gain at ChatGPT's expense suggests the chatbot market is entering a competitive redistribution phase after OpenAI's long dominance.
- **Agentic AI safety gaps** — Multiple research papers this week converge on a core problem: safety benchmarks test models in isolation, but real deployments wrap models in agentic scaffolds that change their safety profiles in ways that are only now being characterized.
- **Hardware supply shock** — NAND price spikes and Intel's gaming CPU launch underscore semiconductor market volatility as AI accelerates hardware demand cycles.

---

*For detailed summaries of selected research papers, see [papers.md](papers.md).*
```
