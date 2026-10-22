# Crawler access and the site check

An engine can cite only what its crawler could fetch and read. This page lists the crawlers, how to let the right ones in, how to test what they see, and the site check to run each week. For crawling and indexing in general (sitemaps, canonicals, redirects, Search Console), use the seo skill if the project has it; this page covers what is specific to AI engines. Docs read 2026-10-22.

## Who reads your site

Three kinds of bot: **search** bots build the index an engine answers from, **user-fetch** bots open a page because a person's question needs it, and **training** bots collect pages that may train future models. For visibility in answers, the first two matter most.

| Token in robots.txt | Vendor | What it does | robots.txt | If you block it | Vendor's doc |
|---|---|---|---|---|---|
| OAI-SearchBot | OpenAI | Crawls for ChatGPT's search features | Honoured; about 24 hours to take effect | Your pages are not shown in ChatGPT search answers (they may still appear as plain links) | developers.openai.com/api/docs/bots |
| ChatGPT-User | OpenAI | Opens a page when a person's request in ChatGPT needs it; not automatic crawling | "may not apply", since a person started it | ChatGPT cannot open your page for that person | same |
| GPTBot | OpenAI | Crawls content that may train OpenAI's models | Honoured | Your content is kept out of training | same |
| Claude-SearchBot | Anthropic | Crawls to improve Claude's search results | Honoured; Crawl-delay supported | Your content is not indexed for Claude's search | support.claude.com, article 8896518 (updated 7 Apr 2026) |
| Claude-User | Anthropic | Fetches pages when a person's question to Claude needs them | Honoured | Claude cannot retrieve your page for a person's question | same |
| ClaudeBot | Anthropic | Collects content that may train Anthropic's models | Honoured | Future content is kept out of training | same |
| PerplexityBot | Perplexity | Surfaces and links sites in Perplexity's results; not used for training | Perplexity asks sites to allow it; changes take up to 24 hours | Your pages drop from Perplexity's results | docs.perplexity.ai, Perplexity crawlers |
| Perplexity-User | Perplexity | Fetches a page a person's question needs | "generally ignores robots.txt rules" | Only a firewall rule stops it | same |
| Googlebot | Google | Google Search, including AI Overviews and AI Mode | Honoured | Out of Google Search and its AI features | developers.google.com/search/docs/appearance/ai-features |
| Google-Extended | Google | A control token, no separate crawler: Gemini training, and grounding in Gemini Apps and Vertex AI | Honoured | Out of Gemini's training and grounding; Google says it does not affect inclusion or ranking in Search | developers.google.com/crawling, Google's common crawlers (updated 15 Oct 2026) |
| Bingbot | Microsoft | Bing's index, which Copilot answers from | Honoured | Out of Bing and Copilot | bing.com/webmasters |
| Applebot | Apple | Search in Siri, Spotlight and Safari; may also supply AI context and training | Honoured | Out of Apple's search features | support.apple.com/en-us/119829 (4 Sep 2026) |
| Applebot-Extended | Apple | A control token for training Apple's models | Honoured | Out of training; still in Apple's search | same |
| CCBot | Common Crawl | Builds an open web archive that researchers and many model makers use | Honoured | Out of future archives | commoncrawl.org/ccbot |

Each vendor's page changes; read it before you write rules. OpenAI, Anthropic and Perplexity publish their crawlers' IP ranges there, so a firewall can verify that a request claiming to be their bot really is.

**Choosing.** Allow every search and user-fetch bot. Training bots are a business choice: blocking them keeps your pages out of future models' training, and allowing them may help a new name become known to future models (a practitioner belief; no study shows it). Blocking Google-Extended also removes you from Gemini's grounding, so it costs Gemini visibility.

## robots.txt

A bot obeys the group that names it, and only falls back to `User-agent: *` when no group names it. So when you add a named group, repeat your private paths in it.

**Allow everyone, keep private paths out, name the sitemap:**

```
User-agent: *
Allow: /
Disallow: /api/
Disallow: /account/

Sitemap: https://www.example.com/sitemap.xml
```

**Allow search and user-fetch bots, keep training bots out:**

```
User-agent: GPTBot
User-agent: ClaudeBot
User-agent: Applebot-Extended
User-agent: CCBot
Disallow: /

User-agent: *
Allow: /
Disallow: /api/
Disallow: /account/

Sitemap: https://www.example.com/sitemap.xml
```

**What goes wrong:**
- A staging site's `User-agent: *` / `Disallow: /` shipped to production.
- A copied "block all AI" list that includes OAI-SearchBot, Claude-SearchBot and PerplexityBot along with the training bots.
- A host's or CDN's managed robots.txt that replaced yours. Fetch `/robots.txt` from outside and read what is actually served.

## The CDN and the firewall

robots.txt is a request; a firewall is a wall. A CDN's bot rules apply whatever robots.txt says, and bots blocked there never read it.

- Cloudflare changed its default to block AI crawlers on 1 July 2025. On 1 July 2026 it split AI crawlers into Search, Agent and Training, and said that from 15 September 2026 new domains block Training and Agent by default on pages that show ads, with Search allowed. Crawlers that do more than one job, such as Googlebot, Applebot and Bingbot, are blocked when Training is blocked (Cloudflare blog, 1 Jul 2026).
- Other CDNs, hosts and security plugins have their own bot settings. Find who controls the one in front of your site.

**Check it in the dashboard and the logs.** A curl from your own machine with a bot's name in it reaches the site from your IP, while the real bot comes from the vendor's IP ranges and may be treated differently. The CDN's bot or AI crawler report, or the server's logs, show whether verified OAI-SearchBot, Claude-SearchBot, PerplexityBot, Googlebot and Bingbot requests got a 200.

## Testing what crawlers see

The main AI crawlers did not run JavaScript in Vercel's 2024 measurement; Google's and Apple's crawlers do. Whatever a buyer must read (what the product is, the price, the answer, the comparison table) has to be in the HTML the server sends.

Status per bot, for each key page:

```
URL=https://www.example.com/pricing
for BOT in OAI-SearchBot ChatGPT-User GPTBot Claude-SearchBot Claude-User ClaudeBot PerplexityBot Perplexity-User Googlebot bingbot Applebot; do
  printf '%-18s ' "$BOT"
  curl -s -o /dev/null -w '%{http_code} %{redirect_url}\n' -A "Mozilla/5.0 (compatible; $BOT/1.0)" "$URL"
done
```

A 403 or a challenge page for one bot and a 200 for a browser means a bot rule is in the way.

What the server sends, without JavaScript:

```
curl -s -A "Mozilla/5.0 (compatible; OAI-SearchBot/1.0)" "$URL" -o page.html
grep -ioE '<title>[^<]*|name="description" content="[^"]*|rel="canonical" href="[^"]*|noindex' page.html
curl -sI "$URL" | grep -i 'x-robots-tag'
sed -e 's/<[^>]*>/ /g' page.html | tr -s ' ' | grep -io 'per month.\{0,60\}'
```

Replace the last search with a sentence that must be on the page. If it is missing from the server HTML but visible in a browser, it is drawn by JavaScript, and AI crawlers will not see it.

Also check: pages answer 200 (not a redirect chain, not a soft 404); the canonical points to the page itself; no `noindex` in a meta tag or header on pages you want found; text in images has the same words in the HTML; answers are not only inside tabs or expanders that load on click.

## Indexing, and telling "not indexed" from "not chosen"

- **Sitemap:** every public page, with a last-modified date that changes only when the content changes. Bing says that date should be "the true last modification time" (Bing Webmaster blog, 31 Jul 2025).
- **Bing Webmaster Tools:** verify the site and submit the sitemap. Bing's index feeds Copilot. Its AI Performance report (public preview since February 2026) shows citations, cited pages and the grounding queries behind them, across Copilot, Bing and partner AI experiences.
- **IndexNow:** ping on each change. Bing, Yandex, Naver, Seznam, Yep and Amazon take part; Google does not. Submitting does not guarantee indexing (indexnow.org FAQ).
- **Google Search Console:** indexed pages, and pages "Discovered, currently not indexed". Its generative AI performance report (announced 3 June 2026, for all sites since 31 August 2026) shows impressions, pages, countries, devices and dates in AI Overviews, AI Mode and Discover's AI features. Search Console also gained a setting, reported in June 2026, to keep a site out of Google's generative AI features: check it says what you intend.
- **The index check:** search each engine's underlying search for `site:yourdomain` and for each key page's exact title in quotes (Google, Bing, Brave). If a page is missing there, the fix is indexing. If it is there and the panel never cites it, the fix is the page or your presence elsewhere.
- **Logs:** count hits per bot per URL each week. A ChatGPT-User, Claude-User or Perplexity-User hit means a live answer opened that page.

## The weekly site check

`ai-visibility/site-check.md`, or a section of the week's report:

```markdown
# Site check, YYYY-MM-DD

Site: https://... Previous: YYYY-MM-DD or none. Summary: [n] pass, [n] warn, [n] fail.

| Status | Check | Detail |
|---|---|---|
| pass/warn/fail | Home answers 200; http and www redirect permanently (301 or 308) | [codes] |
| | robots.txt as served: search and user-fetch bots allowed, sitemap named, private paths out | |
| | CDN or firewall: AI search bots and Googlebot and Bingbot allowed, confirmed in the dashboard or logs | |
| | Sitemap: every public page, true dates, nothing that should stay unlisted | |
| | Each key page, server HTML: 200, title, description, own canonical, no noindex, key sentences and prices present | [one row per page] |
| | Each bot gets each key page (200) | [one row per bot] |
| | Structured data matches what the page shows (hygiene only) | |
| | Bing Webmaster Tools, sitemap submitted, IndexNow pinging | |
| | Search Console: indexed and not indexed counts, generative AI impressions, the AI features setting | |
| | Index check: [n] of [n] queries return your pages | |
| | Logs: which bots fetched which pages this week | |
| | Profiles and listings: the same name and one-line description everywhere, linking back | |

## Changed since the last check
## Needs fixing
| What | Who | How |
```

A check that times out is a warn, never a pass. Quote status codes and headers as you saw them.
