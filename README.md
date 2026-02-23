# AI News Digest

Daily curated digest of AI research papers, news, and security articles. Generated automatically each morning by an automated pipeline.

## Structure

```
YYYY-MM-DD/
  digest.md    — Curated news digest with highlights, research papers, news, and security articles
  papers.md    — In-depth summaries of 15 selected research papers (with full PDF analysis)
```

## How it works

A [news-curator](https://github.com/eddyariki/news-curator) pipeline runs daily at 8 AM via macOS LaunchAgent:

1. **Fetch** — Pulls from 11 RSS feeds (ArXiv cs.AI/cs.LG/cs.CL/cs.CR, MIT Tech Review, The Verge, Ars Technica, TechCrunch, OpenAI Blog, Google AI Blog, Schneier on Security, The Hacker News)
2. **Curate** — Filters to last 24 hours, deduplicates, and categorizes into research papers, news, and security
3. **Digest** — Claude reads the curated JSON and generates `digest.md` with ~30 notable research papers grouped by theme, all news/security articles, highlights, and key themes
4. **Paper deep-dives** — Claude selects the 15 most significant ArXiv papers, downloads their PDFs, reads them, and writes `papers.md` with detailed summaries and key takeaways
5. **Publish** — Commits and pushes to this repo

## Weekend gaps

ArXiv does not publish new papers on weekends (Saturday/Sunday), so digests on those days will have few or no research papers. The pipeline still runs but may produce minimal output. Full digests resume on Monday.
