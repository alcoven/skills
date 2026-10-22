# Choosing measures: the frameworks

The ideas behind steps 1 to 8 of the skill, with where each comes from. Use them to explain a choice to the team in a sentence; the team needs the reasoning, rarely the theory. Sources at the end, each read on 2026-10-22.

## What makes a good metric

Alistair Croll and Benjamin Yoskovitz (*Lean Analytics*, 2013) give four qualities:

| Quality | The test |
|---|---|
| Comparative | Can you compare it with last week, another group, or a target? "2% conversion" says little; "up from 1.5% last month" says something. |
| Understandable | Can people remember it and talk about it? If not, a change in it never becomes a change in what people do. |
| A ratio or rate | Rates compare by nature and put opposing forces in one number (orders per active customer, refunds per order). |
| Changes behaviour | The one that matters most: what would you do differently if it moved? |

The book also contrasts pairs worth naming when a team argues about a number: vanity and actionable, exploratory and reporting, leading and lagging, correlated and causal. Eric Ries (*The Lean Startup*, 2011, and a 2010 Harvard Business Review column) asks that metrics be actionable (they show cause and effect), accessible (people can get and read them) and auditable (people can check them against real customers).

## One Metric That Matters, by stage

*Lean Analytics* asks a team to focus on one metric at a time, chosen by the stage it is in and its business model. The stages are empathy (do we understand a real problem), stickiness (do people keep using what we built), virality (do they bring others), revenue (does it pay) and scale (does it grow efficiently). The metric changes when the stage changes, and the authors warn against moving to the next stage before the current one's metric shows it is done. The book offers its own reference points for many metrics; quote one only with the book's edition and year, and say how alike the businesses are.

## The north star and its inputs

Amplitude's *North Star Playbook* (John Cutler and colleagues) frames the north star as the one metric that best captures the value customers get, with a handful of inputs beneath it that teams work on directly. Its checklist: the metric expresses customer value, represents the product's vision and strategy, is a leading indicator of results, is actionable, is understandable, is measurable, and is no vanity metric. Amplitude also sorts products into three games, which help choose:

- **Attention:** value grows with time spent absorbed in the product (a reading app).
- **Transaction:** value grows with exchanges completed (a marketplace, a shop).
- **Productivity:** value grows with work done well and quickly (a team tool).

A good north star is often too slow to act on in a week; the inputs carry the weekly work. Sean Ellis (2024) adds that it should be able to grow as the company grows and be tied to revenue without being revenue. That makes it usually a count per period, while inputs and guardrails are usually rates; this sits fine beside Croll and Yoskovitz's preference for rates.

## Controllable input metrics

Colin Bryar and Bill Carr (*Working Backwards*, 2021) describe how Amazon separates output metrics (revenue, profit, share price), which no team can move directly, from controllable input metrics, which teams act on and which drive the outputs. Outside Amazon, inputs are often called leading indicators and outputs lagging ones.

Their best-known story is about selection. The first input was the number of new product pages created. Teams added pages for items few people wanted, so the metric moved and sales didn't. It became page views, then the share of page views where the item was in stock, then the share in stock and ready for fast delivery. Each version closed a way to move the number without helping customers. Finding the right input took trial and error, checked against the output week after week in the Weekly Business Review, where the same metrics appear in the same order every week and each one has an owner who explains its exceptions. Amazon also has a finance team, independent of the teams it checks, that certifies the data (Cedric Chin, Commoncog, 2023).

## Metric trees

Abhi Sivasailam (Data Council, 2023) treats a business as an input-output system described by a formula, drawn as a tree:

- At the top, an output: financial (revenue, margin), customer value (the north star) or strategic.
- Below it, **components**: parts that add or multiply to it by definition (orders = active customers × orders per active customer).
- Below those, **influences**: things believed to move a component (delivery on time is believed to move orders per customer). Influences are hypotheses to test; components are arithmetic.

A tree shows each team which branch it owns, and shows when a change in one branch is paid for by another.

## Guardrails and counter-metrics

Andy Grove (*High Output Management*, 1983) warns that an indicator steers what people do, so they may overreact to it. His answer is to pair indicators, so that both the effect and its counter-effect are measured: inventory levels paired with shortages, speed paired with quality.

Ron Kohavi, Diane Tang and Ya Xu (*Trustworthy Online Controlled Experiments*, 2020) sort an organisation's metrics into goal metrics, driver metrics and guardrail metrics. Guardrails come in two kinds: those that protect the business (load time, errors, revenue, complaints) and those that check the data can be trusted (whether groups that should be equal in size are).

Pick 1 to 3 guardrails for the inputs the team will push hardest.

## When a measure becomes a target

- **Goodhart's law.** Charles Goodhart (1975), writing on monetary policy: "Any observed statistical regularity will tend to collapse once pressure is placed upon it for control purposes." The common wording, "When a measure becomes a target, it ceases to be a good measure", is Marilyn Strathern's (1997).
- **Campbell's law.** Donald T. Campbell ("Assessing the impact of planned social change", 1976; journal version 1979): the more a number is used for social decisions, the more it is pressed to be corrupted, and the more it distorts the work it was meant to watch.
- **Three ways to meet a target.** Donald Wheeler (*Understanding Variation*, 1993), crediting Brian Joiner: people under pressure to hit a number can improve the system, distort the system, or distort the data. Cedric Chin (Commoncog, 2023) argues this form is more useful than Goodhart's: design so that improving the system is the easiest of the three.

What to do: target inputs more than outputs; pair each target with a guardrail; show counts and definitions so a bent number is visible; have someone outside the team check the data now and then; and replace a metric once people have learned to move it without moving the work.

## Deciding with incomplete data

- **What would change the decision?** Douglas Hubbard (*How to Measure Anything*, 2007) treats measurement as a reduction in uncertainty, worth paying for only when it could change a decision. He also notes that teams often measure what is easy and skip the few unknowns that matter most. List the unknowns, mark the ones that could flip the choice, and measure those.
- **Price the wait.** Set the cost of a wrong decision against the cost of waiting (a month of the old way, a competitor moving, a team idle). When the decision is easy to undo, decide sooner: Jeff Bezos's 2016 letter to shareholders suggests most decisions can be made with around 70% of the information you wish you had.
- **Set the rule first.** Write the decision rule (the line, the date, what happens on each side) before the data arrives. Kohavi, Tang and Xu ask for the same before an experiment: decide the success metric before seeing the results.
- **Judge the decision apart from the outcome.** Annie Duke (*Thinking in Bets*, 2018) calls judging a decision by its result "resulting": a good decision can turn out badly and a poor one can get lucky. Review what was known and how it was weighed. The decision-making skill covers this in full.

## Sources

All read on 2026-10-22.

- Alistair Croll and Benjamin Yoskovitz, *Lean Analytics*, O'Reilly, 2013 (O'Reilly also lists a 2024 printing). Summaries checked: productcompass.pm/p/are-you-tracking-the-right-metrics; mixergy.com/course-cheat-sheet-lean-analytics
- Eric Ries, *The Lean Startup*, Crown Business, 2011; "Entrepreneurs: Beware of Vanity Metrics", Harvard Business Review, 2010.
- Amplitude, *North Star Playbook*. amplitude.com/books/north-star; checklist as listed by the Open Practice Library, openpracticelibrary.com/practice/north-star-framework; the three games, amplitude.com/blog/product-games-activity
- Lenny Rachitsky with Sean Ellis, Lenny's Newsletter, 5 September 2024. lennysnewsletter.com/p/the-original-growth-hacker-sean-ellis
- Colin Bryar and Bill Carr, *Working Backwards*, St. Martin's Press, 2021, chapter 6 (input and output metrics, the Weekly Business Review).
- Cedric Chin, "Goodhart's Law Isn't as Useful as You Might Think", Commoncog, 11 January 2023 (updated 2026). commoncog.com/goodharts-law-not-useful
- Donald J. Wheeler, *Understanding Variation*, SPC Press, 1993.
- Abhi Sivasailam, "Designing and Building Metric Trees", Data Council, 2023. datacouncil.ai/talks/designing-and-building-metric-trees
- Andrew S. Grove, *High Output Management*, Random House, 1983.
- Ron Kohavi, Diane Tang and Ya Xu, *Trustworthy Online Controlled Experiments*, Cambridge University Press, 2020.
- Charles Goodhart, "Problems of Monetary Management: The U.K. Experience", 1975.
- Marilyn Strathern, "'Improving ratings': audit in the British University system", *European Review*, 1997.
- Donald T. Campbell, "Assessing the Impact of Planned Social Change", 1976; *Evaluation and Program Planning*, 1979.
- Jeff Bezos, 2016 Letter to Shareholders, Amazon, April 2017. aboutamazon.com
- Annie Duke, *Thinking in Bets*, Portfolio, 2018.
- Douglas W. Hubbard, *How to Measure Anything*, Wiley, 2007 (third edition 2014).
