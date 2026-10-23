# Test cards, learning cards and the experiment log

Each test is one document: the test card, written and dated before the test starts, with the learning card added when it is read. Every test also gets two rows in the experiment log. The pivot, persevere or stop call is a decision on record of its own. A worked example follows the templates.

## The test card

Save as `experiments/YYYY-MM-DD-<slug>.md`, dated the day it is written. Its four middle headings follow the Strategyzer Test Card (Osterwalder, 2015; Bland and Osterwalder, 2019): what must be true, how you will test it, what you will measure, and the line that says you were right.

```markdown
# Test: [short name]

- Status: planned | running | read
- Owner: [member id]
- Dates: [start] to [end]
- Decision it feeds: [what the team will do differently depending on the answer]

## We believe that

[The belief, as something people will do.]
Kind: [value | growth | desirable | viable | feasible]. Why it comes first: [what fails without it; the evidence so far, its rung and source].

## To verify that, we will

[The test: who sees it, how they reach it, what they see, what is real and what is done by hand.]

## And measure

[The count and what it is a share of; where it is counted; who is left out (the team, friends, bots) and how.]

## We are right if

At least [X]% of [Y] will [Z] by [date]. X comes from: [the plan's economics, or "a guess"].
We stop if: below [n]%.
In between: [what we will do].
Stopping rule: [end date or number of people, whichever comes first]. No reading before then, except to stop for harm.

## Cost

[People's time, money, anything else.]
```

## The learning card

Added to the same document on the day the test is read. Its four parts follow the Strategyzer Learning Card (Amarsy, 2015): what you tested, what you observed, what you learned, what you will do.

```markdown
## Result, [date]

[pass | fail | grey]: [count] of [denominator] ([rate]), [first day] to [last day]. Pass line: [X]%.
Left out: [what and why]. During the test: [incidents, or none].
Evidence rung: [say | did | do | commit | keep].

## We believed that
## We observed
## From that we learned
## Therefore we will

[persevere: next test | pivot: kind, next test | stop] (decided by [member ids], [date], [§ address of the decision])
```

## The experiment log

`experiments/log.csv`, one row per event, appended and never rewritten: a `card` row when the test card is written, a `result` row when it is read.

| Column | What goes in |
|---|---|
| date | YYYY-MM-DD: the day the card was written, or the day the result was read |
| id | E-01, E-02 and so on, one per test |
| stage | `card` or `result` |
| belief | The belief under test, short |
| test | The kind of test, from the catalogue |
| pass_line | The XYZ line as written on the card |
| result | `pass`, `fail` or `grey` (result rows only) |
| rate | The rate with its counts, such as `3.1% (25 of 804)` |
| evidence | `say`, `did`, `do`, `commit` or `keep` |
| decision | `persevere`, `pivot: <kind>`, `stop` or `tune` |
| owner | Member id |
| card | Path to the test card |

Beside it, `experiments/log.source.md` tells Alcoven how to count the log:

```markdown
# Experiment log

- Service: File in the project
- File: experiments/log.csv
- Days: column date
- Owner: [member id]

## Measures

- tests designed: rows where stage is card
- tests read: rows where stage is result
- passed: rows where result is pass
- failed: rows where result is fail
- grey: rows where result is grey

Every test the team designs and reads, so anyone on the project can see what was tested and what held.
```

If the team asks about these counts more than once, offer a widget on the project's home, for example `experiments/tests.widget.md` with `# Tests read`, `- Show: line`, `- Measure: tests read`, `- From: experiments/log.source.md`, and a line on why it is there.

## The decision on record

```markdown
# [Persevere | Pivot | Stop]: [the idea], [date]

- Decided by: [member ids]
- Stands on: [test cards' § addresses; the log]

[One paragraph: what we tested, what came back, what we will do.]

- What we keep: [what held]
- What changes: [for a pivot, its kind and the part of the plan that changes]
- What we go ahead without testing: [beliefs still untested, if any]
- What would reopen this: [a measure and a line, or a date]
```

When others must agree, hand it out for agreement. For decisions with more at stake than one test, use the decision-making skill if the project has it.

## Worked example (invented)

Crumb is an app showing what is fresh at neighbourhood bakeries. Its team: a product lead (m-7q2d4k), a developer who builds (m-3h8r1c), and an account manager who looks after the bakeries (m-5w9z6p). The idea: "Pre-order for tomorrow", where people order in the evening, collect in the morning, and Crumb takes a fee on each order. The developer puts the full build (payments, a bakery screen, stock holds) at ten weeks.

**Beliefs, mapped:**

| # | Belief | Kind | Matters? | Evidence so far |
|---|---|---|---|---|
| B1 | People near a partner bakery will pre-order for the next morning | Value, desirable | Plan fails without it | None |
| B2 | Bakeries will set stock aside by 7 a.m. | Feasible | Plan fails without it | Three owners said yes (rung 1) |
| B3 | Bakeries accept a fee on each order | Viable | Plan fails without it | None |
| B4 | Payments take four weeks to build | Feasible | Delays it | The developer has built it before (rung 2) |
| B5 | People hear about it at the bakery counter | Growth | Slows it | None |

B1 goes first: the plan fails without it, nothing supports it, and B3 only matters if B1 holds.

**Pass line.** The product lead's model says the feature pays back its ten weeks within a year only if at least 5% of people who see it pre-order. About 400 people a week open Crumb near Linden Bakery (Crumb's own numbers), far too few for an A/B test, so the test has one arm and a pass line.

**The test card,** written 28 Sep 2026:

```markdown
# Test: pre-order at Linden Bakery

- Status: running
- Owner: m-7q2d4k
- Dates: 29 Sep 2026 to 12 Oct 2026
- Decision it feeds: build Pre-order (ten weeks), change it, or drop it

## We believe that
People who open Crumb near a partner bakery will pre-order for the next morning.
Kind: value. Why first: the plan fails without it; no evidence yet.

## To verify that, we will
Show a "Pre-order for tomorrow" button to people who open Crumb within 1 km of Linden Bakery. It opens a short form. The account manager phones the orders to Linden at 8 p.m.; Crumb confirms by text; people pay at the counter.

## And measure
Completed pre-orders as a share of people who saw the button, counted once each. Team accounts and the team's friends left out.

## We are right if
At least 5% of people near Linden who see the button pre-order by 12 Oct. X comes from: the product lead's payback model.
We stop if: below 2%.
In between: one more round with one change; no build.
Stopping rule: 12 Oct. Read on 13 Oct.

## Cost
Two days of the developer's time; an hour of the account manager's each evening.
```

**What came back.** 817 people saw the button. Left out: 9 team accounts, and 4 of the team's friends, who placed 4 of the 29 orders. That leaves 25 orders from 804 people: 3.1%. The rough 95% range (rate plus or minus 1.96 standard errors) is 1.9% to 4.3%, so even its top is under the pass line. One evening brought 11 orders, which looked like a counting error; it was an office ordering a team breakfast, so it stays. 17 of the 25 orders were for four items or more, most on weekday mornings, and 9 came from three offices. Linden missed 2 orders and asked for an 8 p.m. cutoff.

**Learning card:**

```markdown
## Result, 13 Oct 2026
grey: 25 of 804 (3.1%), 29 Sep to 12 Oct. Pass line: 5%.
Left out: 9 team accounts; 4 of the team's friends and their 4 orders. During the test: none.
Evidence rung: do.

## We believed that
People near a partner bakery would pre-order for the next morning, at least 5% of them.

## We observed
3.1%. 17 of 25 orders were group orders, 9 from three offices. Linden missed 2 orders.

## From that we learned
Single pre-orders fall short of what the plan needs. Group orders from offices look like the stronger pull. This test wasn't built for them, so that stays a lead until a test built for it says more.

## Therefore we will
Pivot (customer segment): test paid group pre-orders for offices before building anything. (Decided by m-7q2d4k, 13 Oct 2026.)
```

**Log rows** in `experiments/log.csv`:

```csv
date,id,stage,belief,test,pass_line,result,rate,evidence,decision,owner,card
2026-09-28,E-07,card,People near a partner bakery will pre-order for the next morning,concierge,"At least 5% of people near Linden who see the button pre-order by 12 Oct; stop below 2%",,,,,m-7q2d4k,experiments/2026-09-28-pre-order-linden.md
2026-10-13,E-07,result,People near a partner bakery will pre-order for the next morning,concierge,"At least 5% of people near Linden who see the button pre-order by 12 Oct; stop below 2%",grey,3.1% (25 of 804),do,pivot: customer segment,m-7q2d4k,experiments/2026-09-28-pre-order-linden.md
```

**The next test card (E-08)** reaches a higher rung: "At least 20% of the 30 office managers within 1 km of Linden whom the account manager contacts will place a paid group pre-order within three weeks." X comes from the product lead's model: six offices ordering weekly would pay for a group-order version. Stop below 2 offices.

**The decision on record,** handed out for agreement to the developer (their ten weeks move) and the account manager (they run E-08): no build of single pre-orders; test group orders for offices next; reopen single pre-orders if E-08 fails and a second bakery's area shows more than 5% in the same test.
