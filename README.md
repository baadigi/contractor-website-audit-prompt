# Contractor Website Audit Prompt

A three-part prompt you paste into Claude, ChatGPT, or Gemini to audit a contractor website the way an SEO agency would. Built and maintained by [BaaDigi](https://baadigi.com), a marketing agency for home-service contractors in Huntington Beach, CA.

It runs in three passes. Each pass is its own prompt file so you can run one at a time and read the results without getting buried.

| Pass | File | What it checks |
|---|---|---|
| 1. Foundation | [prompts/1-foundation.md](prompts/1-foundation.md) | Can Google and AI crawlers reach, read, and trust the site? Indexing, redirects, speed, security, sitemap, robots. |
| 2. Pages | [prompts/2-pages.md](prompts/2-pages.md) | Do the pages deserve to rank? Titles, meta, headings, service page depth, internal links, images, schema, duplicate city pages. |
| 3. Visibility | [prompts/3-visibility.md](prompts/3-visibility.md) | Does the business show up where homeowners look? Local signals, reviews, backlinks, brand searches, and AI search (ChatGPT, Perplexity, Google AI Overviews). |

Each pass returns a pass / warn / fail table, a plain-English explanation of what each failure costs you, and a fix list ordered by impact.

## How to use it

1. Open Claude, ChatGPT, or Gemini. Use a model that can browse the web.
2. Copy the full contents of `prompts/1-foundation.md`.
3. Replace `{{SITE_URL}}` with your homepage and `{{TRADE}}` with your trade (roofing, HVAC, plumbing, painting, and so on).
4. Paste and run. Read the fix list.
5. Repeat with pass 2, then pass 3.

Run it on a competitor's site too. The gap tells you what to fix first.

## What the AI can and cannot see

The prompt instructs the model to only report what it actually fetched. It cannot see your Google Search Console, Google Analytics, or Google Business Profile insights. Where a check needs that data, the prompt tells the model to say so and tell you where to look yourself. If the model reports a number it could not have seen, treat the whole answer with suspicion.

## Credits

This started as the `seo-audit` skill from Corey Haines' open-source [marketingskills](https://github.com/coreyhaines31/marketingskills) collection, which we installed in 2026 and ran for a few months. What is here now is a rewrite: the checks are reorganized into three passes, written in plain English for contractors instead of SaaS marketers, and extended with local SEO, review, brand, competitor, and AI-search checks that the original did not cover. The scoring rubric and live-data steps we use internally are not included. Thanks to Corey for publishing the starting point.

The full version we run for clients pulls live Search Console, Analytics, and Ahrefs data and produces a 30/60/90 day plan. If you want that run on your site, [request a free audit](https://baadigi.com/audit).

## License

MIT. Copy it, change it, ship it. A link back is appreciated but not required.
