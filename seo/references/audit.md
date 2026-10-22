# The SEO audit checklist

Work in this order: technical health, then content and intent, then links and reputation. A technical blocker makes every other finding moot for the pages it touches. Each check says how to run it, why it matters, and where the rule comes from (full sources in [measurement.md](measurement.md)). Replace `example.com` with the site.

## Scale the pass

| Site | The pass |
|---|---|
| Small: a few templates, tens of pages | The fetch checks on the home page and one page per template, Search Console's Page indexing and Performance, a read of each key page. |
| Medium: hundreds to thousands of pages | Add a crawler (Screaming Frog's SEO Spider is free up to 500 URLs) and check each template, then a sample of its pages. |
| Large, faceted, several languages, or moving | Add server logs (what Googlebot actually fetches), faceted navigation, `hreflang` and the site-move rows. Stage changes with the developers. |

## Fetch it the way a crawler does

```sh
# Each variant of the home page: final status, number of hops, where it ends
for u in http://example.com http://www.example.com https://www.example.com https://example.com; do
  curl -s -o /dev/null -L -w "%{http_code} %{num_redirects} hops -> %{url_effective}\n" "$u"
done

# Each hop of one redirect (look for a single 301 or 308)
curl -sIL http://www.example.com/pricing | grep -iE "^HTTP|^location"

# robots.txt and the sitemap
curl -s https://example.com/robots.txt
curl -s https://example.com/sitemap.xml | head -40

# One page's server HTML, before any JavaScript runs
curl -s https://example.com/pricing -o page.html
grep -io '<title>[^<]*' page.html
grep -io '<meta[^>]*name="description"[^>]*>' page.html
grep -io '<link[^>]*rel="canonical"[^>]*>' page.html
grep -io '<meta[^>]*name="robots"[^>]*>' page.html
curl -sI https://example.com/pricing | grep -i x-robots-tag

# Is the main text there? Search the server HTML for a sentence you can see in the browser
grep -c "a sentence from the page" page.html
```

A fetch with a crawler's user agent string shows what the server sends to that name, and cannot show what Google received: URL Inspection gives Google's own fetch, rendered HTML and chosen canonical. Some firewalls challenge unknown bots, so check that the crawlers you want get through.

## Technical

| Check | How | Why it matters | Source |
|---|---|---|---|
| **Pages answer 200.** Gone pages answer 404 or 410; an error page never answers 200 (a soft 404). | The commands above; Page indexing: "Soft 404", "Not found (404)", "Server error (5xx)". | Google indexes only pages served with a 200. | Google Search Essentials, technical requirements |
| **One address per page.** http goes to https, one host (www or not), permanent redirects (301 or 308) in one hop, one trailing-slash style. | The redirect commands. | A permanent redirect tells Google the target should be canonical; a temporary one does not. Chains slow crawling, and Google's site-move guide says to avoid them. | Google, redirects; consolidate duplicate URLs; site moves |
| **robots.txt allows what should be crawled.** No stray `Disallow: /`, no blocked CSS or JavaScript the page needs, a `Sitemap:` line. | Fetch it; Search Console's robots.txt report. | Blocked pages cannot be crawled. robots.txt does not keep a page out of the index either: a blocked URL can still show, without a description. Use `noindex` for that. | Google, introduction to robots.txt |
| **`noindex` only where meant.** None on pages that should rank; present on staging, internal search results and empty tag pages. | `<meta name="robots">` and the `X-Robots-Tag` header; Page indexing: "Excluded by 'noindex' tag"; a crawler's indexability column. | A stray tag removes a page. A `noindex` page must stay crawlable, or Google never sees the tag. Google may skip rendering a page that arrives with `noindex`, so adding or removing it with JavaScript is unreliable. | Google, JavaScript SEO basics; robots.txt introduction |
| **The sitemap lists the pages that should rank.** Canonical, indexable, 200, absolute URLs; a `lastmod` that changes only when the content does; split at 50,000 URLs or 50 MB; submitted in Search Console and Bing Webmaster Tools. | Fetch it; compare with a crawl; Search Console's Sitemaps report. | Google uses `lastmod` when it is consistently accurate and ignores `priority` and `changefreq`; Bing uses `lastmod` to choose what to recrawl. Google retired its sitemap ping in 2023. | Google, build a sitemap; Bing Webmaster blog, July 2025 |
| **Canonicals agree.** Each indexable page names itself with an absolute URL; duplicates point to the main version; sitemap, canonical and internal links all use the same URL. | The page commands; URL Inspection ("Google-selected canonical"); Page indexing: "Duplicate, Google chose different canonical than user". | The canonical is a strong signal, and Google overrules it when signals conflict. Using `noindex` or robots.txt to pick a canonical is a known mistake. | Google, consolidate duplicate URLs |
| **The server HTML holds the page.** Main text, links, title, description and canonical are there before JavaScript runs; links are `<a href>`; no content behind `#` fragments. | Compare the curl output with the browser; URL Inspection, "View crawled page". | Google renders JavaScript in a later step and recommends server-side rendering or pre-rendering, since not all bots run it. GPTBot, ClaudeBot and PerplexityBot fetch JavaScript files without running them. | Google, JavaScript SEO basics; Vercel, December 2024 |
| **Internal links reach every page that matters,** with descriptive anchor text, and key pages are a few clicks from home. | A crawler (inlinks, crawl depth); pages in the sitemap that the crawl never reached are orphans. | Crawlers find pages and learn what they are about through links. | Google, link best practices |
| **Mobile and Core Web Vitals.** The mobile page holds the same content. Field data at the 75th percentile: LCP 2.5 s or less, INP under 200 ms, CLS under 0.1. | PageSpeed Insights (field data from the Chrome UX Report, a rolling 28 days) and Search Console's Core Web Vitals report. Use lab tools only to find causes. | Google crawls with a smartphone crawler. Core Web Vitals line up with what core ranking rewards, yet Google still shows the most relevant page when its experience is poor: fix poor pages, and stop at good. INP replaced FID on 12 March 2024. | Google, Core Web Vitals; page experience; Search Central blog on INP |
| **HTTPS and security.** A valid certificate, no mixed content, no hacked pages. | The browser; Search Console's Security issues report. | Hacked content is a spam policy; http links in sitemaps or `hreflang`, or a bad certificate, push Google toward the http version. | Google, spam policies; canonicals |
| **Structured data is valid, matches visible text, and serves a feature that still exists.** | Rich Results Test; Search Console's enhancement reports. | Markup makes a page eligible for a rich result and never guarantees one. FAQ rich results stopped showing for all sites on 7 May 2026, How-to went in 2023, and seven more types were phased out from June 2025. Google says AI features need no special markup. Old markup does no harm. | Google, structured data introduction; search gallery; FAQ notice; Search Central blog, June 2025; AI features |
| **Languages and regions** (only if there are several): `hreflang` on every version, listing every version, itself and an `x-default`, with valid language codes. | A crawler; the page source. | Without the return links, Google may ignore the annotations. Google detects a page's language itself, from the text. | Google, localized versions |
| **Manual actions.** | Search Console's Manual actions report; Bing Webmaster Tools. | A manual action outranks every other finding. | Google, spam policies |
| **Bing and IndexNow.** The site is verified in Bing Webmaster Tools; if the site uses IndexNow, the key file answers at the root. | Fetch `https://example.com/<key>.txt`. | IndexNow tells Bing, Yandex, Naver, Seznam, Yep and Amazon about changed URLs at once. Google does not take part. A submission makes a crawl more likely and guarantees nothing. | indexnow.org FAQ |
| **Large sites: faceted and parameter URLs.** | A crawler; server logs; Search Console's Crawl stats. | Filter combinations can swallow crawling. Block the ones that need no index in robots.txt, and answer 404 for empty combinations. | Google, faceted navigation |
| **Site moves.** | Map every old URL to its new one; 301s from each, kept at least a year; canonicals, internal links and `hreflang` updated; Change of Address for a new domain; the new sitemap submitted. | Rankings wobble while Google recrawls; most pages of a small or medium site move within a few weeks. Google advises against sending many old URLs to an unrelated page such as the home page. | Google, site moves with URL changes |

## Content and intent

| Check | How | Why it matters | Source |
|---|---|---|---|
| **Each important query has one page that answers its intent.** | Search Console: Queries, then Pages for each query. Read the results page for the query. | Google serves what it judges most relevant to the query; the right kind of page matters as much as the words. | Google, how Search works; rater guidelines, intent |
| **Titles and descriptions are unique, descriptive and in the searcher's words,** with the brand short. | A crawler (missing, duplicate); Performance by page. | Google builds title links mainly from the title element and rewrites half-empty, boilerplate or inaccurate ones. Snippets come mostly from the page text; a good description is used when it summarises better. | Google, title links; snippets |
| **No thin or near-duplicate pages:** templated pages with a word swapped, empty tag and category pages. | A crawler's near-duplicate report; many URLs in "Crawled, currently not indexed". | These read as scaled content or doorways, and low-value pages often stay unindexed. Google does not expect every URL to be indexed. | Google, spam policies; Page indexing report |
| **Two pages competing for one query.** | Performance: filter a query, open Pages. | Fine when they answer different intents. When they answer the same one, merge into the stronger page and redirect the other. | Practitioners' judgement |
| **Impressions with few clicks.** | Performance by page and query: compare click-through with pages at similar positions on the same site. | The title misses the intent, or the results page answers the question itself (an AI Overview, a feature). | Google, title links; Pew Research Center, 2025 |
| **Who, how and why are visible:** a named author with their background, how the page was made (including AI, when readers would wonder), linked sources, an About page. | Read the pages. | Google calls trust the most important part of E-E-A-T. E-E-A-T is what raters look for and is no ranking factor in itself; rater data is not used directly in ranking. | Google, helpful content |
| **Dates are honest:** changed only with the content; outdated facts fixed. | Read; compare page dates with the git log or CMS history. | Changing dates to look fresh is one of Google's warning signs. | Google, helpful content |
| **AI-written text is checked by a person,** titles, descriptions and alt text included. | Ask how pages are made; read a sample. | Google allows AI help. Many pages with no added value is scaled content abuse, and raters are told to give low-effort AI main content the lowest rating. | Google, generative AI content; rater guidelines, January 2025 |
| **Demand with no page.** | The content plan ([content.md](content.md)). | A question customers already ask is the cheapest new traffic. | |

## Links and reputation

| Check | How | Why it matters | Source |
|---|---|---|---|
| **Who links, and to which pages.** | Search Console's Links report (top linking sites, top linked pages, anchor text); Bing Webmaster Tools; third-party tools as estimates. | Links help Google find pages and learn what they are about; PageRank is still part of core ranking. Google's Gary Illyes said in 2024 that Google needs "very few links" to rank pages, then said he should not have put it that way. | Google, ranking systems guide; Search Engine Journal, April 2024 |
| **Patterns that look bought or swapped:** paid posts without `sponsored`, exchanges, networks, sitewide footer links, exact-match anchors in bulk. | Anchor text in the Links report; a third-party tool's list. | Link spam under Google's policies, and a reason for manual actions. | Google, spam policies |
| **Disavow only when needed.** | Manual actions report. | Google says most sites never need the disavow tool: use it for many spammy links that caused, or are likely to cause, a manual action. | Google, disavow help |
| **Mentions and listings people use:** partners, associations, directories and review sites with real visitors; the same name and description everywhere. | Search the brand; open each listing. | Real mentions send people, and show a real business behind the site. | |
| **Brand demand.** | Performance: queries containing the brand, by month. | It grows when people hear of you elsewhere, so it shows whether PR and word of mouth work. | |
| **Hosted third-party content and bought domains:** coupon sections, partner pages run by others, an expired domain repurposed. | Read site sections; the domain's history. | Site reputation abuse (which applies even with first-party oversight, since November 2024) and expired domain abuse. | Google, spam policies; Search Central blog, November 2024 |
| **Third-party scores** (Domain Authority, Domain Rating, Authority Score). | | Tools' estimates of a link profile. Google's John Mueller has said Google does not use Domain Authority. Use them to compare, never as a goal. | Search Engine Journal reporting, 2019 to 2022 |

## The prioritised fix list

| # | Issue | Evidence (what, where, date) | Pages | Impact | Effort | How sure | Owner | Due |
|---|---|---|---|---|---|---|---|---|

- **Impact:** High blocks indexing or ranking of pages that matter, or touches most pages. Medium touches a template or a cluster. Low touches single pages or is hygiene.
- **Effort:** S (hours), M (days), L (weeks, or several people).
- **How sure:** Official (Google's or Bing's documentation says so), Seen (you saw it in a fetch or in Search Console), Study (a published study with a method, usually a correlation), Opinion.
- **Order:** High impact with Official or Seen evidence first, small effort first within that. Opinion-only items wait for evidence.

## The audit document

```markdown
# SEO audit: example.com, YYYY-MM-DD

- Scope: [whole site | section], [n] URLs in the sitemap, [templates]
- Data: Search Console [property], [date range]; crawl of [n] URLs on [date]; [other]
- In short: [one or two sentences: the biggest blocker, the biggest chance]

## Fix first
[the prioritised table]

## Technical
[each check: pass, warn or fail, with what you saw and when]

## Content and intent
[findings, each with the query or page and its numbers and dates]

## Links and reputation
[findings]

## Could not check
[what, and why: no Search Console access, no server logs, a page behind a login]

## Next audit
[date, and who runs it]
```
