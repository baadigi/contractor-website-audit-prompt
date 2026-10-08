# Pass 3 of 3: Visibility

You are auditing a contractor website the way a senior SEO would before taking on the client. Passes 1 and 2 covered the site itself. This pass checks whether the business shows up where homeowners actually look: the Google map pack, review sites, other websites, and AI answers from ChatGPT, Perplexity, and Google AI Overviews.

Site: {{SITE_URL}}
Trade: {{TRADE}}
Business name: {{BUSINESS_NAME}}
Primary city: {{CITY}}

## Ground rules

- Search the web for every claim you make. Report what you found and where. Do not invent review counts, backlink numbers, or rankings.
- You cannot see Google Business Profile insights, Search Console, or paid SEO tools. Mark those checks "owner must check."
- Write for a business owner. What is wrong, what it costs, how to fix it.

## What to fetch and search

1. The site's homepage, contact page, and footer
2. `/llms.txt` on the site
3. Web search: `"{{BUSINESS_NAME}}"` (in quotes)
4. Web search: `"{{BUSINESS_NAME}}" {{CITY}}`
5. Web search: `{{TRADE}} {{CITY}}` and `{{TRADE}} near me {{CITY}}` and note who appears
6. Web search: `"{{BUSINESS_NAME}}" reviews`
7. Web search: `site:{{SITE_URL}}` and note the count and what kinds of pages appear
8. Ask yourself, as the AI, the question a homeowner would ask: "Who is a good {{TRADE}} in {{CITY}}?" Record whether this business comes up and which sources you would cite.

## Checks

### A. Name, address, phone consistency

- Business name, street address, and phone number on the website footer and contact page.
- Compare against what web search returns for the business on Google Business Profile, Yelp, BBB, Facebook, Angi, HomeAdvisor, Nextdoor, and trade directories you find. Flag any mismatch in name spelling, suite number, phone number, or an old address still listed somewhere.
- A Google Map embed on the contact page.
- `LocalBusiness` schema on the homepage matches the footer exactly.

### B. Reviews

- Review count and average rating on Google, from what search returns. Flag under 20 reviews or under 4.5 average for a {{TRADE}} business. State clearly these are counts you saw in search results, not live figures.
- Are reviews recent (within the last 90 days)? Stale reviews signal a stalled business.
- Are reviews shown on the website, and do they match what exists on Google?
- Does the owner respond to reviews, especially negative ones?

### C. Who else talks about them

- From the business name search: list every site that mentions the business. Separate directories, news or local media, supplier or manufacturer pages (certified installer listings), chamber of commerce, sponsorships, and social profiles.
- Which of those mention the business without linking to the website? Each one is a backlink you can ask for.
- Does the business appear on manufacturer "find a dealer" pages for the brands it sells (for example Owens Corning, Carrier, Sherwin-Williams)? Those pages carry real authority and are free.
- Owner must check: referring domain count and anchor text in Search Console's Links report, or in Ahrefs or Semrush.

### D. Brand search

- When you search the exact business name, is the website the first result, and does it show sitelinks? Flag if a directory or a competitor outranks the business for its own name.
- Does a Knowledge Panel appear for the business?
- Owner must check: in Search Console, how many clicks per month come from queries containing the business name. Rising brand searches predict revenue 60 to 90 days out. Fewer than 50 a month for an established business is a flag.

### E. Social and physical presence

- Active profiles on Facebook, Instagram, YouTube, LinkedIn, and Nextdoor. "Active" means a post in the last 60 days. Consistent logo, name, and phone number across all of them.
- Street View or photos of the actual office, trucks, or crew somewhere online.

### F. AI search readiness

- `/llms.txt` exists and summarizes what the business does and where. Absence is a warning, not a failure, but it is cheap to fix.
- Confirm from Pass 1 that AI crawlers are not blocked in `robots.txt`.
- Fetch the homepage and one service page with JavaScript disabled if your tool allows. If the content disappears, AI crawlers cannot read the site. Flag as a failure.
- Does each service page open with a direct one-to-three sentence answer to "what is this and who is it for" before any marketing copy? AI systems quote those sentences.
- Does the site have FAQ sections with real questions in the words a homeowner would use, and `FAQPage` schema behind them?
- Result of your own test question in step 8: did the business come up? Which sources would you have cited (Yelp, Google, a local news story, the site itself)? That list is the owner's roadmap.
- Owner must check: ask ChatGPT, Perplexity, and Google (with AI Overview) "best {{TRADE}} in {{CITY}}" once a month and record who is named. Track it.

### G. Competitors in the map pack

- From the `{{TRADE}} {{CITY}}` search: name the three businesses that appear in the map pack or top organic results.
- For each, note review count, rating, and whether their site has a dedicated page for {{CITY}}. One line each.
- State the biggest single gap between the audited business and the top competitor.

## Output format

Return exactly these four blocks.

**1. Scorecard**

| Check | Status | Evidence (URL or search) | What it costs you |
|---|---|---|---|
| A. Name, address, phone | pass / warn / fail | ... | one sentence |
| B. Reviews | ... | ... | ... |
| C. Who else talks about them | ... | ... | ... |
| D. Brand search | ... | ... | ... |
| E. Social and physical | ... | ... | ... |
| F. AI search readiness | ... | ... | ... |
| G. Competitors | ... | ... | ... |

**2. Where the business was found, and where it was missing**

Two lists. Found: site, what it says, whether it links. Missing: directories, manufacturer pages, and local sources where competitors appear and this business does not.

**3. Fix list, in order**

Numbered. Highest impact first. Each item is something the owner or office manager can do without a developer where possible: claim a listing, fix a phone number, ask a supplier for a link, request reviews from the last ten customers.

**4. Owner must check**

Every item that needs Google Business Profile, Search Console, or a paid tool, with the exact report name.

Cite the source for every claim. If you did not see it, say you did not see it.
