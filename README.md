# BrightData Social Story Scraper

A ready-to-import n8n workflow that pulls trending stories from X (Twitter) lists using Brightdata, enriches with Perplexity research, generates content ideas with LLMs, and optionally emails a daily HTML digest.

## Quick start

1) Install n8n (cloud or self-hosted) — see https://docs.n8n.io

2) Import the workflow
- In n8n: Workflows → Import → select `workflows/brightdata_socialstoryscraper.json`.

## Configure credentials (in n8n)
Do NOT paste raw keys into the workflow JSON. Use n8n's credential manager.

- Brightdata → HTTP Request nodes Authorization Bearer (placeholder: `<BRIGHTDATA_API_KEY>`)
- Perplexity → `Perplexity Researcher` node (placeholder: `<PERPLEXITY_CREDENTIAL_ID>`)
- OpenRouter/OpenAI → LLM nodes (placeholder: `<OPENAI_CREDENTIAL_ID>`)
- Notion → Notion nodes (placeholder: `<NOTION_CREDENTIAL_ID>`)
- Gmail (optional) → Gmail node (placeholder: `<GMAIL_CREDENTIAL_ID>`)

## Brightdata custom scraper and input schema (required)

- Place your Brightdata scraper code under `brightdata/interaction-scraper`.
- In your Brightdata collector's Input Schema, add a string input named `url_in` so the dataset receives values like:


```json
[{ "url_in": "https://nitter.net/<path>" }]
```

## Run a test
- Use the manual trigger node to execute once.
- Watch: `Scrape Tweet URLs` → `Trigger Scraping` → `Retrieve Output` → `Code in JavaScript` → `Twitter Analysis` → `Report Generator` → `Send a message`.
- Ensure `Code in JavaScript` returns: `[{ input: [{ url: "https://nitter.net/..." }, ...] }]`.

## Troubleshooting
- Empty Brightdata output: confirm collector accepts `url_in`, check dataset/collector ids and account limits.
- Code node returns []: log raw Brightdata JSON; ensure it includes a `urls` array.
- LLM errors: check credentials, model names, timeouts, and rate limits.

## Attribution
Derived from "Social Story Scraper" by sirlifehacker: https://github.com/sirlifehacker/social-story-scraper. See `CREDITS.md` for details.

