# Content: demand, intent and pages

How to find what people search for, decide which pages to make, and write or review a page. Sources are in [measurement.md](measurement.md).

## Where demand comes from

Start with the customers' words, then check them against what people type. Every source has limits; write them down beside what you found.

| Source | What it gives | Its limits |
|---|---|---|
| **Customers' words:** interviews, support tickets, sales calls, reviews of you and of rivals, community threads | The problem as they say it, the alternatives they name, the questions they ask before buying | No counts. A phrase people say may not be what they type: check it below. |
| **Search Console queries** | Real queries that showed your pages, with impressions and clicks | Only queries you already appear for. Rare queries are left out for privacy; the interface shows 1,000 rows (the API and the bulk data export give more). |
| **Autocomplete, "People also ask", related searches** | Phrasings people type now | No counts; they change by country, language and time. |
| **Google Trends** | The direction and season of a term; two terms compared | Relative scores, never volumes. |
| **Keyword tools** (Google Keyword Planner and paid tools) | An order of size, related terms, who ranks | Estimates, each tool built its own way, so tools disagree. Small terms often show as zero and still bring the right people. |
| **What ranks now** | The intent and the kind of page that gets shown | Learn from it; a copy adds nothing. |
| **Your site search and sales questions** | What visitors could not find | Small samples. |

Search the customers' phrases yourself and keep the exact words that come back. When a customer's phrase and the typed phrase differ, the page title uses the typed words and the body uses both.

## Intent: what the person wants

Google's search quality rater guidelines sort queries into Know (with Know Simple for one-fact answers), Do, Website and Visit-in-person. Practitioners add a comparing intent between knowing and buying.

| Intent | Sounds like | The page that answers |
|---|---|---|
| Know | "how does…", "what is…", "why does…" | A guide or explainer with the answer first |
| Do | "book…", "convert…", "download…", "template" | A tool, a template, a sign-up, a product page |
| Compare and buy | "best … for …", "X vs Y", "X alternatives", "X pricing" | A fair comparison, a pricing page, a product page with evidence |
| Website | a brand name, "X login" | The page itself: make sure it is the one that shows |
| Visit in person | "near me", a town's name | A Google Business Profile and a page per real location |

**Read the results page** for each candidate, in a private window, set to the customers' country and language, on a phone as well. Note the kinds of page in the top results, who ranks (forums, large brands, sites your size), what features show (an AI Overview, videos, a map, shopping), and the questions under "People also ask". A first page of forum threads says people want lived experience; a first page of tools says they want to do the thing. Make the kind of page the results show, or choose another query.

For a business people visit, the Google Business Profile is what shows in local results and on maps: keep it complete and true. Google ranks local results on relevance, distance and prominence, and says there is no way to pay for a better local ranking.

## Choosing what to make

Score each candidate cluster low, medium or high on five things, and talk the scores through rather than adding them up:

1. **Demand:** people search for it (any source above, written with its date).
2. **Fit:** the product truly answers it, in a way you can show.
3. **Chance:** the pages ranking now are ones you can beat on usefulness (a first page of national brands and government sites is a long road for a new site).
4. **Path to the product:** a reader of this page is close to needing what you sell.
5. **Effort:** what the page needs (data, screenshots, an expert's time), and whether you have it.

High fit with low measured demand can still be worth a page when customers ask it often: tools miss small queries. Write one line per choice on why now.

## Clusters and internal links

Group queries that share an intent into one page. Group pages that share a topic into a cluster: a hub page that covers the topic and links to a page for each question, each linking back to the hub and to its neighbours where it helps the reader. HubSpot popularised this as pillar pages and topic clusters; Google's own rule is plainer: every page you care about should have a link from at least one other page, with anchor text that says what is there.

When two pages answer the same intent, merge them into the stronger, redirect the other to it, and update the internal links.

## Programmatic pages

Pages built from a template and a data set are legitimate when each page answers a distinct question with data that differs: a timetable per route, a price per item, an integration per pair of apps. They become scaled content abuse or doorway abuse when the pages exist mainly to catch searches: one text with the city or the keyword swapped, AI rewrites of the same page per phrasing, pages for every variation of a query.

Before building them, ask:

- Would you publish these pages if search engines did not exist?
- Would someone landing on page 37 be glad they found it, rather than its siblings?
- What on each page is true only of that page?

Then start with a small batch. Check in Search Console's Page indexing report that they get indexed, and in Performance that people click them, before making more. Many pages stuck in "Crawled, currently not indexed" is a sign Google sees little value in them.

## AI in the writing

Google allows AI help with research, structure and drafting. Its guidance asks for every fact to be checked by a person, titles, descriptions, structured data and alt text included, and suggests telling readers how content was made when they would reasonably wonder. Its spam policies treat many AI pages with no added value as scaled content abuse, whatever tool made them, and Google's generative AI guide adds two don'ts: mass pages for query variations, and rewriting content only for AI systems. Use AI to draft from your own material (interviews, data, screenshots, the expert's notes); never to fill a page you have nothing to put in.

## The page checklist

| Item | Good looks like |
|---|---|
| Query and intent | One main query and its intent, written at the top of the brief; the page type matches the results page |
| Title | Unique, says what the page is in the searcher's words, brand short at the end; no repeated keywords |
| Description | Unique, a summary of the page in a sentence or two, with a detail the title lacks (a price, a date, who it is for) |
| URL | Short, readable words; stable once published |
| Main heading | One, visible, saying what the title says |
| The answer early | The direct answer in the first lines, then the detail, steps and exceptions |
| Evidence | What only you can show: first-hand use, your data, screenshots, worked examples, named and linked sources, a date on every fact that changes |
| Who and how | The author's name and why they know; how it was made where readers would wonder; an About page reachable |
| Internal links | From the hub and related pages to this one, and from this one onward, with descriptive anchors |
| Images | Alt text that says what the image shows and why it is there |
| Structured data | Only types that match visible content and serve a feature still in use (Article, Breadcrumb, Product, Organization, Software app, Video, Event, Local business and others in Google's search gallery). FAQ rich results no longer show. |
| Date | An "updated" date that changes only when the content does |
| Mobile and speed | Readable on a phone; no layout jumps; no pop-up covering the answer |
| No stuffing | Read aloud, it sounds like a person talking to a person |
| One page per intent | No sibling page answers the same thing |

## Comparison and alternatives pages

People searching "X vs Y" or "X alternatives" are close to deciding, so these pages earn their keep and carry the most risk. The positioning skill decides what is truly different about you; this page shows it with evidence.

- **Credit the other product accurately,** in its own terms, from its own pages, each fact dated and linked. Say what it does well.
- **Say who each one suits,** including the people for whom the other product is the better choice.
- **Say where yours is weaker.** Readers trust a page that admits it, and Google's reviews guidance asks for drawbacks as well as benefits.
- **Put a verdict and a table near the top:** the decision factors that matter to the buyer, never a list padded in your favour.
- **No self-ranked "best" list** without first-hand evidence for every entry. Google's reviews guidance asks for evidence of use, measurements, and what sets each option apart.
- **Check the comparative advertising rules where you sell.** In the EU, Directive 2006/114/EC allows comparisons that are objective, verifiable and like for like, and forbids misleading or denigrating ones.
- **Re-check every quarter,** or when the other product changes its prices or plans, and update the date.

## Page brief template

```markdown
# Brief: [working title]

- Main query: [as typed], intent: [know | do | compare and buy | website | visit]
- Other queries this page answers: [same intent only]
- Evidence of demand: [source, number if any, date]
- The reader: [who, the moment they are in, what they fear]
- In their words: [quotes from interviews or tickets, with source]
- What ranks now: [kinds of page, who, features shown], checked [date]
- What we add that they lack: [first-hand use, data, examples]
- The answer, in two sentences: [...]
- Outline: [headings]
- Evidence to gather: [screenshots, data, an expert's input, sources]
- Links in: [pages that will link here]; links out: [pages this links to]
- Title: [...]; description: [...]; URL: [...]
- Structured data: [type, or none]
- Writer and reviewer: [member ids]; due: [date]
- Measure: [query, page], baseline [clicks and impressions by week, dates], reading date [date]
```

## Content plan template

| Cluster | Main query | Intent | Demand (source, date) | Fit | Chance | Path to product | Effort | Page (new or existing) | Owner | Due | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|

Status is planned, briefed, written, published (with the date) or measured (with the reading's address).
