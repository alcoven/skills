# The panel, the weekly measure and the report

How to build the panel, run it, record and count the answers, and write the week's report. A worked example with an invented company is at the end.

## Building the panel

**Where the questions come from,** best first:

1. What buyers asked you: sales-call and demo notes, support tickets, chat transcripts, interview notes. Their exact words.
2. What they typed: Search Console queries, and autocomplete and "people also ask" for your problem. Engines turn a question into short searches before answering, so typed search is the nearest public proxy for what people ask an AI.
3. Where they ask each other: threads in the communities your buyers use, and questions on review sites.
4. The engine's own follow-ups: the "related" questions an AI offers after answering one of yours.

**Three levels.** Most of the panel is category and problem questions, where a buyer who has never heard of you could meet you. Brand questions are a handful.

| Level | What it measures | Examples |
|---|---|---|
| Category | Whether you are named when a buyer asks for a kind of tool | "Best scheduling app for a small clinic", "Alternatives to [rival]", "[rival] vs [rival 2]" |
| Problem | Whether you are named when a buyer describes the job, with no category | "How do I stop patients missing appointments?" |
| Brand | Whether engines find your own pages and describe you right | "What is [product]?", "[product] pricing", "[product] vs [rival]", "Is [product] safe for patient data?" |

**Wording rules.** One question per item. Write it as the buyer would, with their kind of business and their constraint ("for a two-person bakery", "without a website"). Never put your brand in a category or problem question. If buyers are local, put the place in the question or run from that place, and say which.

**Fix it.** The panel's value is the trend. Add questions; never reword or delete old ones (mark a retired one and keep its history). Note every change in that week's report.

Panel file:

```markdown
# AI visibility panel

Updated: YYYY-MM-DD. Engines: [list]. Runs per question per engine: 3. Location and language: [country, language].

| Id | Level | Question | Source of the wording | Added |
|---|---|---|---|---|
| C1 | category | [question] | [sales call, 2 Oct; Search Console query] | YYYY-MM-DD |
| P1 | problem | [question] | [support ticket #] | YYYY-MM-DD |
| B1 | brand | [question] | [standard] | YYYY-MM-DD |
```

## Running it

| Engine | By hand | By script, where the team has keys | Notes |
|---|---|---|---|
| ChatGPT | Fresh chat, search on, signed out or a clean account | OpenAI's API with its web search tool | The API's model and settings differ from the app |
| Claude | Fresh chat, web search on | Anthropic's API with its web search tool | Claude decides when to search; note answers given without one |
| Perplexity | Fresh thread | Perplexity's API | |
| Gemini | Fresh chat | Gemini API with grounding in Google Search | |
| Google AI Overviews and AI Mode | A signed-out browser in the target country | Read by hand | AI Overviews appear only on some searches |
| Copilot | Fresh chat | Read by hand | Answers from Bing's index |

- **Clean context:** a clean account, a fresh API call with a neutral system prompt, or a script run from an empty folder; never an AI that knows your product from the project's files, its memory or a custom instruction.
- **Same conditions each week:** country, language, search on, the model written down. When an engine changes its default model, say so in the report.
- **Keep the raw answers** with date, engine, model and run, so a doubtful count can be checked.
- **Size:** 30 questions on five engines at three runs is 450 answers. By hand, start with the engines buyers use most; by script, log the cost per run.

## The results table

`ai-visibility/results.csv`, one row per answer:

| Column | What goes in it |
|---|---|
| `date` | The run's date, YYYY-MM-DD |
| `engine` | chatgpt, claude, perplexity, gemini, google-ai, copilot |
| `mode` | app or api |
| `model` | As shown, or "default" |
| `question_id` | From the panel |
| `level` | category, problem or brand |
| `run` | 1, 2, 3 |
| `named` | yes or no: the body of the answer names you (a sources list alone does not count) |
| `first_position` | 1 if you are the first product named, 2 if second, and so on; empty if not named |
| `recommended` | yes if the answer suggests you for the asker's case; no if it only mentions you |
| `our_url_cited` | yes or no: a page on your domain is among the citations |
| `cited_urls` | Every cited URL, separated by spaces |
| `products_named` | Every product the body names as an option, separated by semicolons, one spelling per product |
| `described_right` | Brand questions only: yes, no, or partly |
| `wrong_claim` | The wrong sentence, quoted exactly |
| `searched` | yes or no: whether the engine searched the web for this answer, when you can tell |

`ai-visibility/results.source.md`:

```markdown
# AI visibility results

- Service: File in the project
- File: ai-visibility/results.csv
- Days: column date
- Expect: every week
- Owner: [member id]

## Measures

- named: rows where named is yes
- cited: rows where our_url_cited is yes
- wrong: rows where described_right is no
```

`ai-visibility/weekly.csv`, one row per weekly run, for the trend:

```
date,engines,questions,answers,named,cited,mention_rate,citation_rate,brand_answers,described_right,accuracy
```

`answers`, `named` and `cited` count the category and problem answers only; the rates are percentages of `answers`. `accuracy` is `described_right` out of `brand_answers`. Its `.source.md` has the same shape, with `## Measures` such as `- mention rate: column mention_rate, latest` and `- citation rate: column citation_rate, latest`. A rate is a level, so `, latest` takes each week's newest run and a second run in the same week counts once.

## Counting rules

1. **Read every answer.** A filter can find candidates; you decide each yes.
2. **Mention rate** = category and problem answers that name you, out of all category and problem answers that ran. Failed runs are left out and counted in the report.
3. **Citation rate** = answers whose citations include a page on your domain. A cited third-party page that mentions you is worth noting, but it is not a citation of your site, and it is a mention only if the answer's own text names you.
4. **Share of voice** = for each product, the answers naming it out of the same answers. Leave out the general AI assistants when they are only the subject of the question.
5. **Accuracy** = brand answers that describe you right, out of brand answers. Quote every wrong claim.
6. **Compare like with like:** the same questions and engines in both weeks. When the panel or an engine's model changed, say so and compare the overlap only.
7. **Noise:** a single mention in one run of one engine is noise until it repeats in a later week.
8. **Never a rank.** `first_position` is context for one answer; the trend is the rate.

## The weekly report

`ai-visibility/reports/YYYY-MM-DD.md`, under about a thousand words:

```markdown
# AI visibility, YYYY-MM-DD

Engines: [list, with models]. Runs per question: [n]. Questions: [n] ([changes since last run]). Previous run: YYYY-MM-DD or baseline.

## The numbers
- Mention rate: [n]% ([named] of [answers]), last run [n]%. By engine: [...].
- Citation rate: [n]%, last run [n]%.
- Accuracy on brand questions: [n] of [n], last run [n] of [n].
- Site check: [n] pass, [n] warn, [n] fail.
- Search Console generative AI impressions and Bing AI Performance citations: [figures with dates], or "not read this week".

## What changed since the last run
## Share of voice
[The products named most, with shares, and who gained.]
## What engines say about us
[Right or wrong, quoted, with question id, engine and run. Lookalikes offered instead.]
## Site and crawl
[Each warn or fail: what it is, who fixes it, how.]
## Outreach list
[Up to ten third-party pages cited for category and problem questions: URL, what it covers, which question ids cite it, the honest action.]
## Gaps
[One line each: kind (access, content, presence, accuracy, measurement), new or still open or closed, evidence, what would close it.]
## Last week's steps
[Each, word for word: done, open or dropped, and what happened.]
## Steps this week
1. **[Title].** What to do. Who. Size. The gap it closes and the question ids to watch.
## Not measured
[Engines skipped and why; dashboards not read; questions to try by hand in the consumer apps.]
```

## A worked example (invented)

Crumb is a pre-order and pickup app for independent bakeries, with a marketing lead and a developer who built the site. Its rivals in buyers' words are OvenList, Bakeboard, and "an order form and a spreadsheet". The marketing lead builds a 30-question panel from sales notes and support tickets: 12 category, 14 problem, 4 brand. Three of them:

| Id | Level | Question | Source |
|---|---|---|---|
| C3 | category | What's the best app for a small bakery to take pre-orders without a website? | Demo call, 2 Sep |
| P2 | problem | How do I stop customers forgetting to pick up their bread orders? | Support ticket |
| B2 | brand | Crumb vs OvenList: which is better for a two-person bakery? | Standard |

The marketing lead's baseline (two runs, a week apart, before changing anything) and the third week's report, abridged:

```markdown
# AI visibility, 2026-10-20

Engines: ChatGPT (app), Claude (app), Perplexity (app). Runs per question: 3. Questions: 30, unchanged. Previous run: 2026-10-13.

## The numbers
- Mention rate: 4% (9 of 234), last run 4% (9 of 234). ChatGPT 0 of 78, Claude 3 of 78, Perplexity 6 of 78.
- Citation rate: 1% (2 of 234), last run 0.
- Accuracy on brand questions: 21 of 36, last run 21 of 36.
- Site check: 9 pass, 1 warn, 2 fail.

## Share of voice
OvenList 53%, Bakeboard 31%, "an order form and a spreadsheet" 22%, Crumb 4%.

## What engines say about us
- "Crumb charges a fee on every order" (B3, ChatGPT, runs 1 and 3). Wrong since August; the old price is on a directory listing engines cite.
- Two answers to B1 described a recipe app with a similar name.

## Site and crawl
- fail: the CDN's "block AI bots" setting is on; Claude-SearchBot and PerplexityBot are refused in the logs. The developer, small.
- fail: the pricing table is drawn by JavaScript; curl as OAI-SearchBot returns no prices. The developer, small.
- warn: the sitemap's dates are all the build date. The developer, small.

## Outreach list
1. A hospitality blog's "best bakery pre-order apps" list: cited in 19 answers to C1 to C4. A factual note to the author with what Crumb does and a trial; no payment.
2. A thread in a bakery owners' community asking about no-show pre-orders: cited in 8 answers to P2. The marketing lead answers in their own name, saying they work at Crumb, with steps that work in any tool.

## Gaps
- Access, new: AI crawlers blocked at the CDN. Closes: step 1.
- Content, new: P2 has no good page anywhere; engines cite generic retail advice. Closes: step 3.
- Accuracy, new: the per-order fee. Closes: step 2.

## Steps this week
1. **Allow search and user-fetch bots at the CDN,** and confirm in the logs. The developer, small. Access gap; watch every question's citation rate.
2. **Fix the price where engines read it:** pricing in the server HTML, and the directory listing updated. The developer and the marketing lead, small. Watch B3.
3. **Write "How to stop no-show bread pre-orders",** the answer in the first three sentences, with steps that work without Crumb and one line on how Crumb sends reminders. The marketing lead, medium. Watch P2 and P3.
```

What the marketing lead did not do: hide a line for AI on the pricing page, post in the community from a second account, or report Crumb's "rank". They record the day each fix went live, and read P2 and B3 again in two and four weeks.
