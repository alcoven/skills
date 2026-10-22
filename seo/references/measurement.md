# Measurement, testing and sources

What to measure, what Search Console can and cannot say, baselines and tests, reading a drop, a worked example, and the sources for the whole skill.

## What to measure

| Measure | What it tells you | Read it with care because |
|---|---|---|
| **Clicks** (Search Console) | Visits from Google Search | Google only; Bing Webmaster Tools has its own |
| **Impressions** | How often a page was shown | Moves with demand and with reporting changes (below) |
| **Click-through rate** | Clicks divided by impressions | Compute it from the counts; compare similar positions only |
| **Average position** | The site's topmost link, averaged across queries | A new query at position 40 lowers it while clicks rise; read it per query or page |
| **Indexed pages** | Whether each important page's canonical is indexed (Google's stated goal) | Google does not expect every URL indexed |
| **What search brings** | Sign-ups, enquiries or sales from organic search, in analytics | The goal; the rest explains it |
| **Brand and other queries, apart** | Brand follows fame; the rest follows the content | Mixed, a PR week looks like an SEO win |

## Search Console's caveats

- **Lag:** data arrives in two to three days, and the newest days are preliminary (a dotted line). Days follow Pacific Time.
- **History:** the Performance report keeps 16 months. Export it, or pull it through the API, to keep more.
- **Rows:** the interface shows 1,000 rows, and rare queries are left out for privacy, so query rows add up to less than the total. Totals by property and by page are counted differently and differ.
- **AI features:** an AI Overview takes one position, shared by all its links; AI Mode counts like a normal results page. Since June 2026 a Generative AI report shows impressions in both, as a subset of the main report (see the ai-visibility skill).
- **Known breaks:** the data anomalies page lists them. A logging error affected impressions from 13 May 2025 to 27 April 2026 (clicks were not affected), and impressions may look lower since the fix. In mid-September 2025 Google stopped honouring the `num=100` parameter rank trackers used; many sites saw impressions fall and average position improve while clicks held (industry reports; Google gave no explanation). Never compare impressions across such a date as if nothing happened.
- **Annotations:** since November 2025 you can add a dated note to the Performance chart (120 characters). Use it for each change you ship.

## Baseline, notes and like periods

1. **Before the change,** export clicks and impressions by day for the pages it touches and for the whole site: several full weeks, and the same weeks a year earlier if the data reaches back. Note anything else planned in the window (a launch, a campaign, a holiday).
2. **Write the decision rule and the reading date** before shipping: "If clicks to the changed pages from [date] to [date] are at least [x] above the same weeks before, measured against the unchanged pages, we keep it; below [y], we revert; in between, we read again on [date]." The lean-experiments skill has the test card.
3. **Ship one change per group of pages** and note the day, on the project and in Search Console.
4. **Compare like with like:** the same number of days and weekdays, the same season, the unchanged pages beside the changed ones, and year on year where the business is seasonal.
5. **Check Google's Search Status Dashboard** for core and spam updates in the window. After a core update, Google suggests waiting at least a full week after it finishes, then comparing the week after with the week before it began.

## How long changes take

Google's SEO Starter Guide says some changes show in hours and others take several months, and suggests waiting a few weeks before judging. A new title can take days to weeks to be noticed; most pages of a small or medium site move within a few weeks; after a core update, recognising lasting improvement can take several months. Set the reading date from the kind of change, and write in the rule that the date is the team's choice. Reading early is the commonest way to learn the wrong thing.

## Tests

| Design | When it fits | What it can tell |
|---|---|---|
| Before and after, with a dated note | Any site | The weakest: anything else in the window looks like your effect |
| Before and after against unchanged pages | Several pages of one kind | Better: updates, seasons and demand hit both groups |
| Split test by pages | Many pages on one template, steady traffic | The strongest: pages that behaved alike are split, and the effect is the gap from a forecast built on the unchanged group |

SEO tests split pages, because the crawler is one visitor. SearchPilot, which sells such tests, says they are more often inconclusive than tests on people. On a small site, say what a test cannot show and settle for a dated before and after.

## Reading a drop

Check in this order, writing down what each check found:

1. **The data:** Search Console's data anomalies page, a tracking change in analytics, preliminary days.
2. **The site:** a jump in excluded pages in Page indexing; `robots.txt`; `noindex`; redirects; outages; a release on that day (`git log`).
3. **Manual actions and Security issues.**
4. **Google's updates:** the Search Status Dashboard's dates against the drop.
5. **Demand:** Google Trends for the main queries; the same weeks last year.
6. **The results page:** a new feature above you (an AI Overview, videos, a map), a new competitor, a changed intent. Impressions steady with clicks down points here or at your title; both down points to rankings, indexing or demand.
7. **The page itself:** what changed on it, and when.

Write the reading in the shape the metrics skill uses: what moved, against what, the checks run, the likely cause and how sure, what it cannot show, and what would settle it.

## AI answers and clicks

AI answers above the results go with fewer clicks below them. Pew Research Center tracked 900 US adults in March 2025: visits to a Google results page with an AI summary ended in a click on a traditional result 8% of the time, against 15% without one; 1% clicked a link inside the summary. Ahrefs (February 2026) found an AI Overview correlated with a 58% lower click-through rate for the top result, December 2025 against an estimated baseline from December 2023. Seer Interactive (September 2025) saw click-through fall on queries without AI Overviews too. Each is one study with its own method. So judge search by clicks and what they bring, expect fewer clicks on questions with short answers, and use the ai-visibility skill for being cited in the answers.

## The routine

| When | What |
|---|---|
| Each release | Fetch the live `robots.txt`, a page's head and headers, the sitemap; note the day |
| Weekly | Add the week's rows; note why anything moved |
| Monthly | Queries and pages up, down and new; Page indexing; Core Web Vitals |
| Quarterly | The audit; comparison pages refreshed; pages nobody visits merged or removed |

## Worked example (invented)

Studio Wren sells booking software to small yoga and pilates studios. Maya runs marketing; Tomás builds the site: about 130 pages, with 70 blog posts and 40 "studio software in [city]" pages from one template. On 27 July 2026 Maya asks: "Our Google traffic has dropped since June. Why don't we rank?"

**The audit** (`seo/audits/2026-07-27.md`), the fix list:

| # | Issue | Evidence | Pages | Impact | Effort | How sure |
|---|---|---|---|---|---|---|
| 1 | Blog posts carry `noindex` | In every post's server HTML; 64 posts "Excluded by 'noindex' tag" from 12 June; template changed in the 10 June release | 70 | High | S | Seen |
| 2 | City pages share one text | Only the city's name differs; 31 "Crawled, currently not indexed" | 40 | Medium | M | Official, Seen |
| 3 | Prices drawn in the browser | Server HTML has the heading, no prices | 1 | Medium | M | Seen |
| 4 | www redirects with a 302 | The redirect commands | All | Low | S | Official |
| 5 | FAQ markup | No longer shown; harmless | 12 | Low | None | Official |

Tasks: Tomás removes the tag and fixes the redirect by 29 July, with a release check that fetches a post's head; prices by 10 August. The AI said once that 40 near-identical pages read as doorways and suggested keeping six cities with customers, each with its studio's story; Maya agrees to do it after the blog fix, so the two changes do not overlap.

**The plan:** support tickets keep mentioning double bookings; autocomplete offers "how to stop double booking yoga classes", whose results are guides and forum threads, so the page is a guide with screenshots, drafted from Maya's interview notes. "BigStudio Suite alternatives" (an invented rival) shows comparison pages, so that brief is a fair comparison: a table, dated prices with links, and who should choose BigStudio (studios with several locations).

**The measure:** blog clicks were 380 to 420 a week from 13 April to 10 May, and about 110 a week by mid-July. The fix shipped on 29 July, with a note on the widget that day and an annotation in Search Console. The rule, written on 27 July: "By 19 August, blog clicks within a fifth of the April and May weeks and at least 60 of 64 posts indexed: close it; otherwise inspect the posts still excluded." On 19 August: 330 and 350 clicks in the weeks of 3 and 10 August, 59 posts indexed, and no Google update in either window. The reading: the drop came from the tag and mostly returned once the posts were indexed; season cannot be ruled out, since the blog has no year of history. Of the five posts still out, one duplicates another and is merged. The city pages go next, read in November against the six kept pages' own baseline.

## Sources

All read on 2026-10-22. Google's pages carry their own "last updated" date, given where it matters.

**Google Search Central** (developers.google.com/search)
- Spam policies for Google web search (updated 2026-08-28): scaled content, site reputation and expired domain abuse, link spam, doorways, cloaking; trying to manipulate generative AI responses counts as spam.
- Creating helpful, reliable, people-first content (2026-10-05); using generative AI content (2026-10-01); the generative AI features guide in Search Central's Fundamentals (2026-07-10: AI features need SEO fundamentals, no llms.txt, special markup or chunking); AI features and your website.
- SEO Starter Guide; how Google Search works; Search Essentials; ranking systems guide; core updates; the Search Status Dashboard (status.search.google.com).
- Page experience (2026-09-22); Core Web Vitals; "Introducing INP to Core Web Vitals" (May 2023, updated 12 March 2024).
- JavaScript SEO basics; robots.txt; canonical URLs (2026-07-10); redirects; sitemaps (2026-07-08); faceted navigation; localized versions; site moves (2026-08-20); title links; snippets; link best practices; high quality reviews.
- Structured data introduction; search gallery (2026-10-16); the FAQ notice (not shown from 7 May 2026).
- Blog: HowTo and FAQ changes (August 2023); sitemaps ping retired (June 2023); March 2024 core update and spam policies; site reputation abuse update (November 2024); simplifying the results page (June 2025); custom annotations (November 2025); Generative AI performance reports (June 2026).
- blog.google, "New ways we're tackling spammy, low-quality content on Search", 5 March 2024, updated 26 April 2024 (45% less low-quality, unoriginal content, by Google's count).
- Search Console Help: Performance metrics; about the data; Page indexing; data anomalies; disavow links. Google Business Profile Help: local ranking.
- Search Quality Rater Guidelines, January 2025 version (the section on intent; low-effort AI content).

**Bing and IndexNow**
- Bing Webmaster Guidelines (bing.com/webmasters), with prompt injection added in 2024 (Search Engine Land); Bing Webmaster Blog, "Keeping Content Discoverable with Sitemaps in AI Powered Search", July 2025; IndexNow FAQ (indexnow.org).

**Studies and reporting**
- Pew Research Center, "Google users are less likely to click on links when an AI summary appears in the results", 22 July 2025.
- Ryan Law and Xibeijia Guan, "Update: AI Overviews Reduce Clicks by 58%", Ahrefs, 4 February 2026.
- Seer Interactive, "AIO impact on Google CTR: September 2025 update".
- Giacomo Zecchini, Alice Alexandra Moore, Malte Ubl and Ryan Siddle, "The rise of the AI crawler", Vercel, 17 December 2024.
- Will Critchlow, "The math behind SearchPilot: how SEO A/B testing actually works", SearchPilot, 29 July 2026.
- The 2024 leaked Content Warehouse API documents: Rand Fishkin (SparkToro) and Mike King (iPullRank), 27 and 28 May 2024; Google's statement to The Verge warning against "out-of-context, outdated, or incomplete information". The documents list stored attributes, with no weights and no word on how each is used.
- Search Engine Journal: Gary Illyes on links (April 2024); John Mueller on Domain Authority (2019 to 2022); the `num=100` change (September 2025).
- HubSpot Knowledge Base, pillar pages and topic clusters; Screaming Frog, SEO Spider pricing (free up to 500 URLs).
- Directive 2006/114/EC on misleading and comparative advertising (EU).
