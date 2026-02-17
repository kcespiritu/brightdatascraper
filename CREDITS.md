Credits and attribution

This repository contains a derived n8n workflow and custom Brightdata scrapers based on the "Social Story Scraper" project by sirlifehacker: https://github.com/sirlifehacker/social-story-scraper

Original author: sirlifehacker (https://github.com/sirlifehacker)
Original project: https://github.com/sirlifehacker/social-story-scraper

What was derived or inspired:
- The overall workflow design (topic analysis, Perplexity research, content brainstorming, report generation)
- Prompts and structured output parsers used for analysis and content generation

Modifications made in this repository:
- Replaced the original Apify X/Twitter scraper with a custom Brightdata-based scraper located under `brightdata/interaction-scraper`.
- Adjusted parsing prompts and output mappings to accept Brightdata output formats.
- Updated the workflow file `workflows/brightdata_socialstoryscraper.json` to include derived metadata and notes.

License and permissions

As of 2025-11-12 the upstream repository did not contain a LICENSE file. The absence of an explicit license means the original code is not licensed for reuse by default ("All rights reserved"). Before publishing a public fork or distribution that includes derived code, you should either:

1) Contact the upstream author to request permission or a license grant; or
2) Clearly state the license you are applying to the files you own and only publish files you have the right to redistribute.

Suggested next steps before publishing

- Replace placeholder values in the workflow sticky note (`REPLACE_WITH_YOUR_GITHUB_USERNAME`, `REPLACE_WITH_YOUR_REPO_URL`) with your actual GitHub account and repo URL.
- Add a LICENSE file for the code you control (e.g., MIT) and document which parts are your original work vs. derived.
- Optionally open an issue or PR on the upstream repo to ask for an explicit license or permission note.

Contact

If you'd like, I can craft the exact PR description and commit messages you'll use when publishing this fork.
