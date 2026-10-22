# Prioritising, saying no, and checking work against the strategy

The strategy does most of the prioritising: it names the few outcomes and what the team will not do. The methods below only order what is left inside it. Each gives a number that looks precise and is built from guesses. Use them to sort a long list and to start the conversation, then decide in the conversation with the evidence in view. Sources at the end, each read on 2026-10-22.

## Methods and their limits

| Method | How it works | Good for | Watch for |
|---|---|---|---|
| **RICE** (Sean McBride, Intercom) | Reach (people per period) × Impact (3 massive, 2 high, 1 medium, 0.5 low, 0.25 minimal) × Confidence (100%, 80%, 50%), divided by Effort (person-months). | A long list of comparable product ideas, where usage data gives the reach. | Impact and confidence are guesses, and multiplying them hides it. McBride himself treats the score as a guide: dependencies or a sales need can justify a lower score, and a result that looks wrong should be re-examined. |
| **ICE** (Sean Ellis, for growth tests) | Impact, Confidence and Ease, each scored 1 to 10. | Ranking many small, cheap tests quickly. | Confidence is usually a feeling. Itamar Gilad's confidence meter ties it to the kind of evidence (opinions low, test results and launch data high). |
| **Cost of delay** (Don Reinertsen, 2009) and **CD3** (Joshua Arnold, Black Swan Farming) | Ask what each week without this costs: lost revenue, rising cost, a missed window, a growing risk. CD3 divides that by how long the work takes, and does the highest first. | Ordering work when the team's capacity is the limit; making urgency visible beside value. | The estimates are rough; the value estimate matters more than the duration. Dividing by duration rewards splitting work small, which is usually good. |
| **Kano** (Noriaki Kano, 1984) | Sorts features by how customers react: expected (their absence angers), more-is-better, delighting (unexpected), indifferent. | Deciding what a release cannot ship without, and what would set it apart. | It rests on what customers say in a survey, and delights become expectations over time. |
| **Opportunity scoring** (Anthony Ulwick) | Customers rate how important each need is and how well it is met today; important and poorly met marks an opportunity. | Finding needs the market serves badly. | Needs a careful survey of many customers; it ranks needs and says nothing about whether you can meet them. |
| **Appetite and the betting table** (Ryan Singer, *Shape Up*, Basecamp, 2019) | Decide how much time a problem is worth (the appetite, such as two or six weeks) and shape the work to fit. A few senior people bet on a few shaped pitches for the next six-week cycle, with two weeks of cool-down between cycles. No central backlog; work that runs past its bet gets no extension by default. | Fixed time and flexible scope; stopping work from growing without limit. | Shaping takes skill and seniority. The bets must still answer to the strategy's outcomes. |

**Appetite and estimate differ.** An estimate starts from a design and ends at a number; an appetite starts from a number (the time the problem is worth) and ends at a design that fits it. Ask for the appetite first: it turns "how long will this take?" into "how much is this worth to us?".

## A short way to order work inside the strategy

1. **Drop what doesn't belong.** Anything on the not-do list, or serving no outcome, comes off, with the line it conflicts with.
2. **Write four facts per item.** The outcome it serves; the evidence behind it, by kind; its appetite; what waiting a month costs.
3. **Sort.** High cost of delay and strong evidence first. An item with weak evidence goes to discovery before it gets build time (the product-discovery skill).
4. **Score only to break ties** in a long list, and show the inputs beside the score so anyone can question them.
5. **Decide together, and write the order and the reasons** where the team will find them.

## Saying no

- **The not-do list.** Jim Collins argued that a stop-doing list matters as much as a to-do list (2003). Each entry names something people want, why not now, and when to look again. Revisit it each quarter, and read it aloud when the next big request arrives.
- **Saying no to a customer or a colleague.** Thank them, and name the line of the strategy the request runs against. Say what you can do: the problem behind it goes onto the discovery tree, and there is a date to look again. Never offer a delivery date to soften the no.
- **A big customer's request** is weighed by the strategy like any other. If it should change the strategy, propose that edit openly so the team can agree to it; slipping it into the roadmap moves the strategy without anyone deciding.
- **The backlog.** *Shape Up* keeps no central backlog: ideas that matter come back. At the least, close anything untouched for two cycles, with a note saying why.
- **Cheap building makes no harder to say.** Since AI tools made building faster, teams can say yes to more, and scatter. Each yes still costs attention, support and upkeep, and pushes something else out.

## Checking a proposal

Answer each proposal in this shape, citing the strategy's sections:

```markdown
**[The proposal]** ([who asked, where, date])

- Serves: [which outcome], or none.
- Fits the guiding policy: yes or no, because [the line, with its address].
- On the not-do list: yes or no.
- Pushes out: [what the team would stop or delay].
- Cost of waiting a month: [what], or not known.
- Evidence: [its kind: opinions, requests, data, tests, launch data].
- Appetite: [the time it is worth].
- Verdict: fits, to discovery | fits, into Now | doesn't fit ([line]) | challenges the strategy: propose [edit].
```

A proposal can fit and still wait: "fits, to discovery" is the usual answer for an idea with little evidence behind it.

## Sources

- Sean McBride, "RICE: Simple prioritization for product managers", Intercom blog. https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers/, read 2026-10-22.
- Itamar Gilad, the confidence meter and ICE. https://itamargilad.com/the-tool-that-will-help-you-choose-better-product-ideas/, read 2026-10-22.
- Donald G. Reinertsen, *The Principles of Product Development Flow*, Celeritas, 2009.
- Joshua J. Arnold, "Cost of Delay Divided by Duration", Black Swan Farming. https://blackswanfarming.com/cost-of-delay-divided-by-duration/, read 2026-10-22.
- Noriaki Kano and others, "Attractive quality and must-be quality", 1984.
- Anthony W. Ulwick, "Turn Customer Input into Innovation", Harvard Business Review, January 2002. https://hbr.org/2002/01/turn-customer-input-into-innovation, read 2026-10-22.
- Ryan Singer, *Shape Up*, Basecamp, 2019, chapter "The Betting Table". https://basecamp.com/shapeup/2.2-chapter-08, read 2026-10-22.
- Jim Collins, on the stop-doing list, USA Today, 30 December 2003. https://www.jimcollins.com/article_topics/articles/best-new-years.html, read 2026-10-22.
