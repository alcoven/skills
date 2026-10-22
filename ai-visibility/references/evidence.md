# The evidence: how engines pick sources, and what studies show

Every claim here has a date and one of three labels:

- **Vendor says:** the engine's owner (or the platform), in its own docs or posts.
- **Measured:** a study with a stated method. Most such data comes from companies selling tracking or SEO tools: large, observational, gathered through their own prompts, and often in disagreement. That is noted.
- **Practitioner belief:** reasoned from the evidence or from experience, with no study behind it.

Engines change monthly. Re-check anything older than six months, and treat one vendor's "engine X changed on date Y" as provisional until a second source sees it.

## 1. How each engine finds its sources

| Engine | Vendor says | Measured or reported |
|---|---|---|
| ChatGPT search | OAI-SearchBot crawls for ChatGPT search; sites that opt out are not shown in its search answers (OpenAI crawler docs, undated, read 2026-10-22). At launch, OpenAI said search draws on third-party search providers and partners' content (OpenAI, 31 Oct 2024). | Peec AI (tracking vendor, Sep 2026) inferred an own index plus at least eight outside providers, Bing mainly in Deep Research. Ahrefs (vendor, 15 Apr 2026, 1.4M prompts): about half the URLs retrieved are cited; cited pages' titles are closer to the prompt. |
| Claude | Claude-SearchBot indexes for search, Claude-User fetches for a person's question; both honour robots.txt (Anthropic, 7 Apr 2026). | Brave Search joined Anthropic's subprocessor list in March 2025, and Claude's citations matched Brave's results (Simon Willison, 21 Mar 2025). Claude cited sources in 55% of responses, averaging 13 links when it cited (Muck Rack, May 2026). |
| Perplexity | Its own index tracks over 200 billion URLs (Perplexity, 25 Sep 2025). PerplexityBot surfaces sites; Perplexity-User "generally ignores robots.txt rules". | Reddit was its most cited domain at 6.6% of citations, YouTube second at 2.0% (Profound, tracking vendor, 680M citations, Aug 2024 to Jun 2025). |
| Google AI Overviews and AI Mode | "There are no additional requirements to appear in AI Overviews or AI Mode": a page must be indexed and eligible for a snippet; both may run several related searches ("query fan-out") (Google, 10 Dec 2025). | 37.9% of AI Overview citations were in the query's top 10, against about 76% in July 2025, with a changed method (Ahrefs, 2 Mar 2026, 863k keywords). |
| Gemini app | Google-Extended controls Gemini training and grounding in Gemini Apps; it does not affect inclusion or ranking in Google Search (Google, updated 15 Oct 2026). | |
| Copilot | Answers from Bing's index; freshness signals affect how fast updates reach AI answers, and "no tool can guarantee when or how your content will appear" in them (Bing, 31 Jul 2025). | |
| Apple | `nosnippet` keeps content out of Apple's broad AI answers (Apple, 4 Sep 2026). | |

**Rendering, measured.** None of the major AI crawlers ran JavaScript; Google's and Apple's did; about 34% of ChatGPT's and Claude's crawler fetches hit 404s (Vercel with MERJ, 17 Dec 2024). Old; no later study of AI crawlers and JavaScript was found (searched 2026-10-22).

## 2. What AI answers cite

- **Earned media, measured.** Of over 25 million links in ChatGPT, Claude and Gemini answers, 84% went to earned media (82 to 89% across three editions since July 2025), 27% to journalism, 0.3% to paid content (Muck Rack, a PR software company, May 2026). A University of Toronto preprint found the same pattern: AI search showed a "systematic and overwhelming bias towards Earned media"; in one US vertical, 81.9% of GPT search's citations were earned media against 45.1% of Google's top results (Chen, Wang, Chen and Koudas, University of Toronto, arXiv 2509.08919, Sep 2025).
- **Mentions over links, measured.** Across 75,000 brands, branded web mentions correlated with AI Overview visibility at 0.664, backlinks at 0.218 (Ahrefs, 26 May 2025). YouTube mentions correlated most strongly, about 0.737, across ChatGPT, AI Mode and AI Overviews (Ahrefs, 12 Dec 2025). Correlation only, on brands above a size threshold.
- **Lists, measured.** "Blog lists" averaged 43.8% of the pages ChatGPT cited for one kind of product-category query (Ahrefs, 13 Mar 2026). G2 was among ChatGPT's ten most cited domains (Profound, 2025).
- **Communities are volatile, measured.** Reddit appeared in close to 60% of ChatGPT responses in early August 2025 and around 10% by mid-September (Semrush, 10 Nov 2025, 230,000 prompts).

## 3. What on-page work does

- **The GEO paper, measured in a lab.** Aggarwal and colleagues (KDD 2024) built a 10,000-query benchmark and a test engine that handed the top five Google results to GPT-3.5-turbo. Adding citations, quotations and statistics to a source worked best: 30 to 40% relative gains on position-adjusted word count, 15 to 30% on subjective impression. Keyword stuffing scored below baseline. Lower-ranked sources gained most (citing sources raised the fifth-ranked by 115.1% and lowered the top-ranked by 30.3%). On Perplexity.ai, adding quotations gained 22%.
- **Its limits.** Each page was already one of five sources handed to the model, so crawling and ranking were skipped. A 2026 survey found that retrieved content can be shifted in how it is cited, but "no reviewed technique shows a stable, longitudinal, cross-platform causal effect" (Martinez, arXiv 2607.14035, Jul 2026).
- **Google, vendor says.** No AI text files, markup or Markdown needed; no need to break content into tiny pieces; no special schema for AI search; pages made for query variations break the scaled content abuse policy; original content from your own knowledge helps (Google guide to generative AI features in Search, 10 Jul 2026).
- **Microsoft, vendor says.** Titles that summarise the page, clear headings, questions with direct answers, lists and tables help; don't hide answers in tabs or put key facts only in images (Microsoft Advertising, 8 Oct 2025).
- **Structured data, measured.** 1,885 pages that added JSON-LD, against 4,000 matched controls: no lift anywhere; AI Overviews down 4.6% (significant), AI Mode and ChatGPT up about 2% (not distinguishable from zero). The pages were already heavily cited (Ahrefs, 11 May 2026).
- **Position and freshness, measured.** 44.2% of ChatGPT citations came from the first 30% of a page (Kevin Indig's 1.2 million citations, reported by Ahrefs, 13 Mar 2026). AI assistants cited content about 25.7% fresher than organic results (Ahrefs, 13 Mar 2026), yet the median page ChatGPT cited from its index was about 500 days old (Ahrefs, 15 Apr 2026) (practitioner belief: freshness matters most for time-sensitive questions).

## 4. llms.txt

- **What it is:** a proposed Markdown file at `/llms.txt` listing a site's key pages for language models (Jeremy Howard, llmstxt.org, Sep 2024).
- **Vendor says:** Google Search does not use such files; they neither help nor harm (Google, 10 Jul 2026). OpenAI's, Anthropic's and Perplexity's crawler docs do not mention it (read 2026-10-22).
- **Measured:** 97% of llms.txt files got no requests in May 2026; AI retrieval bots made 1.1% of the requests that did arrive (Ahrefs logs, 137,000 domains, reported by PPC Land, 2 Jul 2026).
- **Practitioner belief:** useful for developer docs that coding agents read; expect nothing for a marketing site.

## 5. What AI answers do to clicks

- **Measured, independent.** In March 2025 browsing by 900 US adults, people clicked a traditional result in 8% of visits to a Google page with an AI summary against 15% without; clicked a link inside the summary in 1%; and ended browsing in 26% against 16% (Pew Research Center, 22 Jul 2025). Association only.
- **Measured, vendors.** Position-one click-through on keywords with an AI Overview was 34.5% lower (Ahrefs, Apr 2025), about 58% lower in December 2025 data (Ahrefs, Feb 2026). Brands cited in an Overview got 35% more organic clicks than those not cited, cause unproven (Seer Interactive, Sep 2025, 3,119 queries).

## 6. Measuring

- **Answers vary, measured.** Across 2,961 runs of 12 prompts on ChatGPT, Claude and Google's AI, the same brand list came back under 1% of the time; how often a brand appears across runs was steadier. Rand Fishkin: "any tool that gives a 'ranking position in AI' is full of baloney" (SparkToro with Gumshoe, a tracking vendor, 30 Jan 2026; not peer reviewed).
- **Referrals, reported.** ChatGPT's `utm_source=chatgpt.com` tag is partial, and practitioners reported in October 2026 that tags and referrers dropped, moving visits into Direct (limy.ai, Relevant Audience; not confirmed by OpenAI).
- **First-party reports, vendor says.** Search Console's generative AI report (impressions, pages, countries, devices, dates) and Bing's AI Performance report (citations, cited pages, grounding queries). Neither shows where in an answer you appear.
- **Paid trackers** (Profound, Peec AI, Otterly, Semrush, Ahrefs Brand Radar and others) sample by their own method: check app or API, location and runs before comparing with your numbers.

## 7. Rules and risks

- **Google, vendor says.** Spam includes "attempting to manipulate generative AI responses in Google Search", hidden text, scaled content abuse and site reputation abuse (spam policies, 28 Aug 2026).
- **Hidden instructions, shown once.** The Guardian showed in December 2024 that hidden text could change what ChatGPT search said about a page. OpenAI may have closed that gap since; Google's spam policy forbids the practice in Google Search either way.
- **Fake reviews, law.** The US FTC's rule bans writing, buying or selling fake reviews and testimonials and buying fake social signals, with civil penalties, since 21 Oct 2024.
- **Crawler defaults, vendor says.** Cloudflare's AI crawler defaults changed on 1 Jul 2025 and from 15 Sep 2026 (crawlers-and-site-check.md).

## 8. Practitioner beliefs

From teams running weekly panels; no study shows these.

- A review or directory profile is more often an entry ticket for "best software" answers than the cited page.
- For a question about another vendor's product, its help pages are cited first; a dated, accurate how-to can be the second source.
- The same name and one-line description on every profile helps engines tell a young product from lookalikes.
- Engines invent specifics for thin brands (a setup URL, an install command, a price). Fix the source they read; redirect an invented URL.
- A finding is noise until it repeats in a later week.

## Sources

Read 2026-10-22 unless stated.

- Google Search Central: "AI features and your website" (updated 10 Dec 2025); guide to generative AI features in Search, Fundamentals docs (updated 10 Jul 2026); blog, "Introducing Search Generative AI performance reports in Search Console" (3 Jun 2026, all sites from 31 Aug 2026); spam policies (updated 28 Aug 2026); common crawlers and Google-Extended (updated 15 Oct 2026). All at developers.google.com.
- 9to5Google, on Google's control to opt out of AI Overviews and AI Mode (2 Jun 2026).
- OpenAI: "Overview of OpenAI crawlers" (developers.openai.com/api/docs/bots, undated); "Introducing ChatGPT search" (31 Oct 2024; it refused automated reading on 2026-10-22, so this rests on launch coverage).
- Anthropic, "Does Anthropic crawl data from the web, and how can site owners block the crawler?" (support.claude.com, updated 7 Apr 2026).
- Perplexity: crawlers (docs.perplexity.ai); "Architecting and evaluating an AI-first search API" (25 Sep 2025).
- Bing Webmaster blog: sitemaps in AI powered search (31 Jul 2025); AI Performance public preview (Feb 2026); AI visibility insights (16 Jun 2026). Microsoft Advertising blog, content for AI search answers (8 Oct 2025).
- Apple, "About Applebot" (support.apple.com/en-us/119829, 4 Sep 2026). IndexNow FAQ (indexnow.org). Common Crawl, CCBot (commoncrawl.org/ccbot).
- Cloudflare blog: "Content Independence Day" (1 Jul 2025) and its 2026 follow-up on Search, Agent and Training crawlers (1 Jul 2026).
- Vercel with MERJ, "The rise of the AI crawler" (17 Dec 2024).
- Pranjal Aggarwal, Vishvak Murahari, Tanmay Rajpurohit, Ashwin Kalyan, Karthik Narasimhan and Ameet Deshpande, "GEO: Generative Engine Optimization", KDD 2024 (arXiv 2311.09735).
- Olivier Martinez, critical survey of GEO, 2023 to 2026 (arXiv 2607.14035, Jul 2026).
- Mahe Chen, Xiaoxuan Wang, Kaiwen Chen and Nick Koudas, University of Toronto, on winning in AI search (arXiv 2509.08919, Sep 2025).
- Muck Rack, "What Is AI Reading?", May 2026 edition.
- Ahrefs blog: brand factors and AI Overviews (26 May 2025); AI brand visibility correlations (12 Dec 2025); AI Overview citations and the top 10 (2 Mar 2026); how to rank on ChatGPT (13 Mar 2026); why ChatGPT cites pages (15 Apr 2026); schema and AI citations (11 May 2026); AI Overviews reduce clicks (Apr 2025, updated Feb 2026).
- PPC Land, llms.txt adoption and Ahrefs' request data (2 Jul 2026). Jeremy Howard, the /llms.txt proposal (llmstxt.org, Sep 2024).
- Semrush, most cited domains in AI search (10 Nov 2025). Profound, AI platform citation patterns (Jun 2025, updated Aug 2025). Peec AI, ChatGPT search result providers (Sep 2026).
- Simon Willison, "Anthropic use Brave" (21 Mar 2025).
- Pew Research Center, on Google clicks when an AI summary appears (22 Jul 2025). Seer Interactive, AI Overviews and click-through, September 2025 update.
- SparkToro and Gumshoe, consistency of AI recommendations, reported by Search Engine Journal (30 Jan 2026).
- limy.ai and Relevant Audience, on ChatGPT referral tagging (Oct 2026).
- The Guardian, tests of ChatGPT search and hidden text (Dec 2024, as reported by Search Engine Journal).
- US Federal Trade Commission, final rule on fake reviews and testimonials (14 Aug 2024; in force 21 Oct 2024).
