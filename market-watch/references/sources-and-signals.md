# Sources, signals and checking claims

Where to look, how to tell a signal from noise, and how to check a claim before it reaches the brief. Sources at the end.

## Sources by kind

Keep the list short: a few sources per kind, each with a reason. Read customers first and newsletters last.

| Kind | Where | What to look for | How often |
|---|---|---|---|
| Customers' own words | Support tickets, sales and lost-deal notes, interview notes, reviews of you and your rivals, community threads and forums where they gather | New words for the problem, alternatives they name, repeated complaints, what they praise in a rival | Weekly |
| Competitors | Changelogs and release notes, pricing pages, docs, job posts, their customers' stories, their own announcements | A new price or plan, a new segment, a feature that answers a job your customers have, hiring that shows where they are heading | Weekly for the two or three closest; monthly for the rest |
| What the product depends on | AI model vendors' changelogs, pricing, deprecation and terms pages; payment, app store and hosting providers' notices | Retirements, price changes, new limits, new terms, a new ability that changes what is cheap to build | Weekly |
| Rules | Regulators' and governments' own pages for your sector and places | New obligations, and dates that move | Monthly, and when a date is near |
| Analysts and newsletters | A few chosen for their track record in your market | Pointers to primary sources; data you can trace | Weekly, last, skimmed |

Example of why rules need dates: the EU's own page on the AI Act shows the high-risk obligations moved to later dates after a 2026 amendment (digital-strategy.ec.europa.eu, page updated 19 Oct 2026, read 22 Oct 2026). A brief that quoted the old dates in spring would now be wrong.

## Per competitor: what to track, and what not to

Track, for the few rivals customers actually name:

- **Who they serve:** the customers on their homepage and in their stories. A new segment matters more than a new feature.
- **Price and packaging:** plans, limits, the free tier, what moved between plans.
- **What shipped:** from the changelog, and only what answers a job your customers have.
- **Where they are heading:** job posts (a team for a new market, a new kind of engineer), and their own stated plans.
- **What their customers say:** praise and complaints in reviews and threads, in their words.

Andy Grove's test for which rival matters most (*Only the Paranoid Survive*, 1996): if you had a single silver bullet, which competitor would you save it for? Then ask whether that one is about to change.

Do not obsess over: every small release, their social posts, their funding news on its own, their homepage wording week to week, or rivals no customer has named. Amazon's 2016 shareholder letter puts the alternative plainly: you can be competitor focused, but "obsessive customer focus is by far the most protective" of a company's early energy (Jeff Bezos, 2016).

## Signal or noise: the tests

An item is a signal when it passes at least one test, and you can say how.

1. **It changes what our customers do or can do.** They have a new way to do the job, a new constraint, a new expectation.
2. **It changes their alternatives.** A rival, a free tool or a platform now does the job, or stopped doing it.
3. **It changes our costs, our dependencies or the rules.** A price, a limit, a retirement, a new obligation.
4. **It touches what won't change.** Jeff Bezos at Amazon's re:Invent in 2012 said the more useful question is what will not change in ten years, because a strategy can rest on it (for Amazon's shoppers, low prices and fast delivery). Christensen's jobs theory makes the same point: the job people need done stays steady while the ways of doing it change (*Competing Against Luck*, 2016). A new way of doing a job your customers have is a signal. Another tool in a category, with no change for the job, is noise.

Write the test it passed beside each item. "Interesting" is not a test.

## Hype

Gartner's Hype Cycle (Jackie Fenn, 1995) describes a technology rising on a trigger to a peak of inflated expectations, falling into a trough of disillusionment, then climbing a slope of enlightenment to a plateau of productivity. It is useful as a reminder that early claims run high. Use it with care: Michael Mullany's review of twenty years of Gartner's charts (2016) found that few technologies travelled the whole curve, many appeared once and vanished, and several that became mainstream were not flagged early. Roy Amara's line, known as Amara's law, is a simpler guide: we tend to overestimate a technology's effect in the short run and underestimate it in the long run.

For the brief: neither chase nor dismiss. Ask what customers do differently now, with evidence, and what would show the change is real (customers paying for it, a rival's customers moving, a platform committing to it in its terms).

## How things evolve (optional)

Simon Wardley's maps place each part of a product on a line of evolution: genesis (new and uncertain), custom built, product (bought from several suppliers), and commodity or utility (standard, metered). Parts move right over time. For the watch, the question is: which of the things we build or depend on is moving toward commodity? When a part you built by hand becomes a cheap service, your cost or your difference changes. Use it when the team already maps; it is not required.

## Checking a claim

Mike Caulfield's SIFT moves, in short:

1. **Stop.** Especially when the news is exciting or alarming.
2. **Investigate the source.** Who published it, and do they know?
3. **Find better coverage.** What do other careful sources say?
4. **Trace claims to the original.** The changelog, the pricing page, the filing, the regulator's page, the paper.

Then write two dates: when it happened (from the original) and when you read it. If the original cannot be found, mark it "unconfirmed" or leave it out. Prices, limits and model names change often; quote them with the page and the date, never from memory.

## The watchlist

An idea from Thoughtworks' Technology Radar (Neal Ford, 2016) helps: a radar names specific things, says in a line why each sits where it does, marks what is new or moved, and drops items that have not changed for about a year. A watchlist works the same way: specific items, a reason, a date checked, a status (Watch, Act, Note, Retired), and a retire rule. Template in [brief-and-watchlist.md](brief-and-watchlist.md).

## Won and lost deals

If the team sells, the best market data is why buyers chose. Pragmatic Institute's practice list: interview won and lost buyers in equal numbers, within three months of their decision; do not rely on the salesperson alone, since they are close to it, and consider someone neutral; compare findings at least each quarter; treat the buyer's view as what happened. Clozd and others add that buyers speak more freely to a third party. For the interviews themselves, use the customer-interviews skill if the project has it. Bring the reasons into the monthly look back, counted by buyer, with quotes and dates.

## Sources

Read 2026-10-22 unless stated.

- Jeff Bezos, remarks at AWS re:Invent, 29 Nov 2012, as reported by TechCrunch ("Amazon Founder Jeff Bezos Talks AWS, Innovation..."). Quote Investigator notes he made the same point in earlier interviews.
- Jeff Bezos, 2016 Letter to Shareholders (aboutamazon.com).
- Clayton M. Christensen, Taddy Hall, Karen Dillon and David S. Duncan, *Competing Against Luck* (HarperCollins, 2016).
- Andrew S. Grove, *Only the Paranoid Survive* (Doubleday, 1996): strategic inflection points, 10X forces, the silver bullet test.
- Gartner, Hype Cycle methodology (gartner.com); Jackie Fenn's 1995 report introduced it.
- Michael Mullany, "8 Lessons from 20 Years of Hype Cycles" (LinkedIn, 7 Dec 2016), as summarised by ipSpace.net (2020).
- Roy Amara, Amara's law (attributed, 1970s; original publication not traced).
- Simon Wardley, *Wardley Maps* (CC BY-SA), and wardleymaps.com's glossary of evolution stages.
- Mike Caulfield, SIFT, from "Check, Please!" (CC BY 4.0), as taught in university library guides.
- Neal Ford, "Build Your Own Technology Radar" (Thoughtworks, 6 Nov 2016).
- Pragmatic Institute, "Eight Best Practices for Win-Loss Analysis" (pragmaticinstitute.com, undated).
- Clozd, "Keys to Successful Win-Loss Analysis" (clozd.com/blog).
- European Commission, "AI Act" policy page (digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai, updated 19 Oct 2026).
