## Fact-Check Report — 2026-04-09

### Part 1: News Digest
**Verdict:** PASS WITH NOTES

#### Issues Found

**[Python Supply-Chain Compromise: litellm 1.82.8]** — The source title is "Python Supply-Chain Compromise" (no subtitle). The ": litellm 1.82.8" suffix is drawn from the article body rather than the title itself. The addition is factually accurate per the source text, so this is a minor note rather than an error; no correction applied.

All other articles checked: titles are faithful paraphrases of source titles, outlet attributions are correct, URLs match the JSON source records, and summaries stay within the facts present in the source text.

---

### Part 2: Paper Summaries
**Verdict:** PASS

#### Issues Found
None. All 12 paper entries have titles and ArXiv URLs that match the digest. Author lists are consistent with what is present in the source data. Summaries and Key Takeaways are supported by the abstracts and do not introduce claims clearly absent from the source material.

---

### Part 3: Security Digest
**Verdict:** FAIL

#### Issues Found

**[Python Supply-Chain Compromise]** — Two factual errors in the security digest description:

1. The digest says the `.pth` file executes "automatically **on import**". This directly contradicts the source, which states it "is automatically executed by the Python interpreter **on every startup, without requiring any explicit import** of the litellm module." The absence of a required import is the critical security detail — the malicious code runs even if the package is never imported.

2. The digest says the file executes "**to exfiltrate environment variables and credentials**." This specific payload description does not appear in the source. The source describes only that the `.pth` file is malicious and executes automatically; it does not characterise what the code does to the host system. This is an invented detail.

**[New Chaos Variant Targets Misconfigured Cloud Deployments, Adds SOCKS Proxy]** — The security digest specifies "**SOCKS5** proxy capability." The source (both the JSON article and the news digest entry) says only "SOCKS proxy module" with no version specified. "SOCKS5" is an unsourced addition.

---

### Overall Summary
Parts 1 and 2 are clean. The news digest's article attributions, URLs, and summaries are accurate throughout, and the paper summaries stay faithfully within their abstracts. Part 3 (security digest) contains two articles with verifiable errors: the litellm entry mischaracterises the execution trigger ("on import" instead of "on every Python startup without import") and adds an unsourced payload claim ("exfiltrate environment variables and credentials"), while the Chaos botnet entry promotes an unspecified "SOCKS proxy" to a specific "SOCKS5" version not mentioned in any source. Corrections have been applied to security-2026-04-09.md below.
