# The positioning canvas

One page the whole team can read in five minutes and check copy against. Fill the sections in order (each feeds the next), cite a source on every line, and grade the evidence (Strong, Medium, Weak, Assumed; see method.md). Write the summary paragraph last. Keep it as one living document: a new version when it changes, with the change noted at the end.

## Template

```markdown
# Positioning: [product, offer or company]

- As of: [date] · Version: [n] · Status: draft | agreed
- Decided by: [person] · Worked on with: [people, by role]
- Next review: [date, about six months on], or sooner on a signal below

## Summary

[Written last, two sentences. For [best-fit customers] who [situation], [product] is a
[market category] that [lead value]. Unlike [main alternative], it [the difference that
makes the value possible].]

## 1. Best-fit customers we started from

| Customer | Why they count (bought fast, stayed, grew, referred) | In their words | Source |
|---|---|---|---|

## 2. Competitive alternatives

| Approach | What it looks like | What it does well | Where it falls short for our best-fit customers | Source |
|---|---|---|---|---|
| Doing nothing | | | | |

Watched, left out (never in deals): [names, and why].

## 3. Differentiated capabilities

| Capability | Which alternatives lack it | How we prove it |
|---|---|---|

## 4. Differentiated value

| Value theme | Capabilities behind it | What it is worth to the customer | Proof | Grade |
|---|---|---|---|---|

Lead theme: [one]. Considered and dropped: [themes, and why].

## 5. Who cares a lot

- What makes them care: [situation, current tools, frequency, trigger]
- Signs we can spot: [what a seller, an ad or a sign-up form can see]
- Who we leave out: [segments, and why]

## 6. Market category

| Candidate | Who buyers compare us with | Features they expect | Who buys | Price they expect | True of us? |
|---|---|---|---|---|---|

Chosen: [category], style [head-to-head | big fish, small pond | new game], because [reason].

## 7. Point of view (optional)

[The change in the market that makes the value urgent now, its evidence, and how it
connects to what the product does today. Or: none yet.]

## 8. Evidence and gaps

| Line | Grade | Gap | How we close it | Who, by when |
|---|---|---|---|---|

## 9. Signals to watch

- [What would make us revisit this, and where it would show]

## Changes since the last version

- [Date: what changed and the evidence that changed it]
```

Rules for filling it in:

- A line with no source says Assumed and gets a row in section 8.
- Alternatives come from customers and deals. Every row says what the alternative does well.
- Capabilities are facts you can show today. Planned work goes in no section above.
- Value themes are one to three. If you have more, you have features: group them again.
- A category row is filled in for every candidate, including the one you have today.

## Worked example (invented)

Crumb is an invented app for independent bakeries. Maya founded it after running a bakery; Tomás sells and runs demos; Ines builds the product. Crumb launched as "online ordering for bakeries": a shop page where locals pre-order. Growth was slow, prospects compared it with delivery marketplaces and asked about delivery, and shop-only bakeries left within a few months. Customers who supplied cafés stayed and told other bakers. Maya asked for a positioning pass before rewriting the homepage.

```markdown
# Positioning: Crumb

- As of: 14 Oct 2026 · Version: 2 · Status: agreed
- Decided by: Maya · Worked on with: Tomás (sales), Ines (product)
- Next review: April 2027, or sooner on a signal below

## Summary

For independent bakeries that supply cafés every morning, Crumb is wholesale order
management that turns each café's standing order and last-minute changes into the night's
bake sheet and the week's invoices. Unlike messages and a spreadsheet, every change lands in
one place before the cut-off, so the bake and the deliveries are right without typing orders
up at night.

## 1. Best-fit customers we started from

| Customer | Why they count | In their words | Source |
|---|---|---|---|
| Rye & Co | Signed after one demo, 9 months in, referred two bakeries | "I used to retype café orders at ten at night. Now I print the sheet." | interviews/2026-09-rye-and-co.md |
| Kettle Bakehouse | Added all 11 café accounts in week one | "The cafés change their own orders. I stopped answering texts in bed." | interviews/2026-09-kettle.md |
| North Loaf | Stayed through a price rise | "Wrong deliveries were costing us the cafés." | sales/wins/north-loaf.md |

## 2. Competitive alternatives

| Approach | What it looks like | What it does well | Where it falls short for them | Source |
|---|---|---|---|---|
| Doing nothing | Absorb wrong deliveries, apologise | No cost, no change | Cafés drift away after repeated mistakes | sales/wins/north-loaf.md |
| Messages and a spreadsheet | Cafés text or call; baker types orders into a sheet at night | Free, flexible, everyone knows it | Late changes get lost; totals by hand; errors found at delivery | interviews/ (5 of 6) |
| Till system's pre-order add-on | Shop customers order ahead | Already paid for, good for shop pre-orders | No standing orders per café, no cut-off, no invoices | calls/2026-08-*.md |
| General AI assistant | Paste the evening's messages, ask for totals | Quick, handles messy messages | Baker still collects and pastes every message and checks totals; standing orders and cut-offs live nowhere | calls/2026-10-03-oven-house.md |

Watched, left out: industrial bakery suites (built for factories; never in a deal).

## 3. Differentiated capabilities

| Capability | Which alternatives lack it | How we prove it |
|---|---|---|
| Standing orders per café, each day's changes closed at that café's cut-off | Spreadsheet, till add-on, AI assistant | Demo; Kettle's account |
| Cafés change their own orders through a link, no account needed | All | Demo |
| Bake sheet: all orders as quantities and batches per recipe, ready at cut-off | Till add-on, spreadsheet without formulas | Demo; Rye & Co's printed sheet |
| Delivery notes and weekly invoices from the same orders | Till add-on, AI assistant | Demo |

## 4. Differentiated value

| Value theme | Capabilities behind it | What it is worth | Proof | Grade |
|---|---|---|---|---|
| Every wholesale order right, without typing orders up at night | Standing orders, café self-changes, bake sheet | Kept café accounts; evenings back | Rye & Co and Kettle quotes; North Loaf win note | Strong |
| Invoices that match what was delivered | Delivery notes and invoices from orders | Fewer disputes, paid sooner | Tomás's call notes, three bakeries | Medium |

Lead theme: the first. Dropped: "a beautiful shop page" (the till add-on and shop builders do it as well).

## 5. Who cares a lot

- What makes them care: supplies five or more cafés or restaurants that order most days and change orders often; the owner or head baker plans the bake; orders arrive by message today.
- Signs we can spot: talks about "the sheet" and "cut-off"; wholesale prices on their site; a delivery van.
- Who we leave out: shop-only bakeries (they want delivery and a shop page); industrial bakeries with a suite.

## 6. Market category

| Candidate | Compared with | Features expected | Who buys | Price expected | True of us? |
|---|---|---|---|---|---|
| Online ordering for bakeries (today) | Marketplaces, shop builders | Shop page, delivery, card payment | Shop owner | Commission per order | No: our strength is wholesale |
| Bakery management software | Suites | Stock, staff, till, accounts | Owner, accountant | High monthly fee | No: we would look thin |
| Wholesale order management for bakeries | Spreadsheets, generic order tools | Standing orders, cut-offs, invoices, production | Owner or head baker | Monthly fee by accounts | Yes |

Chosen: wholesale order management for bakeries, style big fish, small pond, because its
assumptions are true of Crumb and the comparison is with the spreadsheet, which Crumb beats.

## 7. Point of view (optional)

Cafés now expect to change orders the evening before by message; the bakeries that keep them
make changes easy and still bake the right amount. Hypothesis: two interviews say it. Keep it
out of ads until the next five calls confirm it.

## 8. Evidence and gaps

| Line | Grade | Gap | How we close it | Who, by when |
|---|---|---|---|---|
| "Five or more cafés" | Weak | Based on four customers | Check accounts per customer against who stayed | Ines, 28 Oct |
| AI assistant as an alternative | Weak | One prospect named it | Ask "what would you use otherwise?" on the next five calls | Tomás, 4 Nov |
| Invoices theme | Medium | Call notes only | Two interviews with bakeries that invoice monthly | Maya, 11 Nov |

## 9. Signals to watch

- Shop-only bakeries still signing up from search (the old frame lingers).
- Café chains asking for several sites in one account (a new segment).
- A till company adding standing orders (a new alternative in deals).

## Changes since the last version

- 14 Oct 2026: category moved from online ordering to wholesale order management; shop-only
  bakeries left out. Evidence: sections 1 and 2.
```

What the example shows:

- The default frame ("online ordering") came from where the product started; the customers who stayed pointed elsewhere.
- Doing nothing and a general AI assistant are on the list, each described fairly.
- One lead theme with strong proof; a second with medium proof, marked as such.
- The category table shows why two familiar frames were wrong, using the buyers' assumptions.
- The point of view is kept as a hypothesis and out of ads until evidence arrives.
- Each weak line has a person and a date to close it.
