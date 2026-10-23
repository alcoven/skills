# The test log, the idea card, the meeting note and the growth model

The four documents a growth team keeps, and a worked example. Keep them in one folder (`growth/` unless the project has another place), so every member and every AI on the project reads the same record.

## The test log

A table with one row each time a test starts or ends. Rows are only ever added, so the log is also a history: what the team tried, when, and what it learned.

| Column | What goes in |
|---|---|
| date | The day of the event, YYYY-MM-DD. |
| test | A short id and name: `T7 prefilled standing order`. |
| event | `planned`, `started` or `ended`. |
| stage | `acquisition`, `activation`, `retention`, `referral` or `revenue`. |
| metric | The input metric the test should move. |
| pass_line | On `started` rows: the result that counts as a win, the day it is read, and the least number of people it needs. |
| ice | On `started` rows: the ICE score. |
| owner | The member id of who runs it. |
| result | On `ended` rows: `win`, `loss`, `flat` or `unclear`. |
| learning | On `ended` rows: one line, what the team now knows. Losses get one too. |
| link | The idea card or the change that shipped. |

The header line: `date,test,event,stage,metric,pass_line,ice,owner,result,learning,link`. Put a field in double quotes when it holds a comma.

A `.source.md` beside it, `growth/tests.source.md`, turns the log into numbers the team can chart (tests started a week, wins by stage):

```markdown
# Growth tests

- Service: File in the project
- File: growth/tests.csv
- Days: column date
- Expect: every week
- Owner: m-4f2k9a

## Measures

- tests started: rows where event is started
- tests ended: rows where event is ended
- wins: rows where result is win
- stage: by column stage
```

## The idea card

One per idea worth scoring, in `growth/ideas/`.

```markdown
# [The idea in a few words]

- Stage: [acquisition | activation | retention | referral | revenue]
- Metric: [the input it should move]
- Hypothesis: If we [change], [metric] goes from [baseline, with its date] to [expected], because [evidence].
- Evidence: [customer words, data, a past test, each with its source and date]
- ICE: Impact [1 to 10], Confidence [1 to 10], Ease [1 to 10]; score [combined the team's usual way]
- Pass line: [the result that counts as a win], read on [date], with at least [n] people.
- Guardrail: [what must not get worse]
- Owner: [member id]. Builds it: [member id]
```

Confidence cites its evidence; a hunch scores low. Ease counts engineering time.

## The weekly meeting note

```markdown
# Growth meeting, [date]

Focus until [date]: [stage], moving [metric] from [baseline, date] to [target] by [date].

1. North star and inputs: [reading, newest date, source]; what moved and the likely reason.
2. Tests launched: [n] of [n] planned; what slipped and why.
3. Finished: [test]: [result]; [one line of learning].
4. This week: [tests, owners, pass lines].
5. Pipeline: [ideas added; stages with too few ideas].

Decisions: [a changed focus, target or test, and who decided].
```

## The growth model document

```markdown
# Growth model, [date]

- Must-have: [met | not met | unknown]; [evidence, date].
- Aha moment: [action and window]; activation [n of n, period].
- North star: [metric]; [reading, date]. Equation: [inputs].
- Main loop: [step 1] → [step 2] → [step 3] → back to step 1. Weakest step: [step, evidence].
- Fits: market and product [..]; product and channel [..]; channel and model [..]; model and market [..]. Weakest: [..].
- Guardrails: [metrics that must not get worse].
- Focus until [date]: [stage, metric, target].
- Next review: [date].
```

## A worked example (invented)

Crumb lets cafés order next-morning bread and pastries from local bakeries. The team is a growth lead, an engineer and a marketer. The growth lead asks: "We want twice the orders by February. Should we run ads to cafés?"

**Step 1, must-have.** No survey exists, so the AI drafts one and the growth lead sends it to the 74 customers who ordered at least twice in the past two weeks. 58 answer; 6 say they no longer use Crumb and are left out, as agreed before counting. 18 of 52 are very disappointed: 35%, under Ellis's line. Split by persona: cafés with a daily order, 13 of 20; home bakers ordering for events, 5 of 32. Cohort retention says the same: café cohorts flatten from week 6, home-baker cohorts keep falling.

**Speaking up, once.** "Before ads: cafés are well above the line and home bakers far below it, so ads should go to cafés only. But of the cafés that signed up in September, 9 of 31 set up a standing order within 14 days. Ads would bring cafés into that leak. Four weeks on activation first?" The growth lead agrees, and asks the marketer to prepare the café ads for December.

**Step 2, the aha moment.** Of August's cafés, those with a standing weekly order in their first 14 days were still ordering at week 8 far more often: 11 of 13, against 4 of 15 without one. Written as a hypothesis: "sets up a standing order within 14 days".

**Step 3, the north star.** Standing orders delivered per week. The equation: new cafés × share with a standing order within 14 days × share of standing orders still running at week 8 × cafés brought in by each bakery. Guardrails: the share of orders delivered late, and refunds.

**Step 4, the model.** The main loop: a bakery joins, invites the cafés it already supplies, those cafés order and discover other bakeries, and those bakeries join to serve them. The weakest step: 3 of 11 bakeries sent any invites. The weakest fit: product and channel, as the invite is a link buried in settings.

**Step 5, the focus.** Activation, until 15 December: the share of new cafés with a standing order within 14 days, from 9 of 31 (September) to half of November's cafés.

**Step 6, the ideas.**

| Idea | Impact | Confidence | Ease | ICE |
|---|---|---|---|---|
| After the second order, suggest a standing order filled in from the first two | 8 | 7 | 6 | 7.0 |
| Discount on the first standing order | 6 | 4 | 9 | 6.3 |
| Call each new café on day 3 | 7 | 6 | 4 | 5.7 |

The first goes ahead. The log gets two rows, one at the start and one at the end:

```
date,test,event,stage,metric,pass_line,ice,owner,result,learning,link
2026-11-03,T7 prefilled standing order,started,activation,standing order within 14 days,at least half of new cafés by 2026-11-28 with at least 30 cafés,7.0,m-4f2k9a,,,growth/ideas/t7.md
2026-11-28,T7 prefilled standing order,ended,activation,standing order within 14 days,,,m-4f2k9a,win,17 of 33 new cafés set one (52%); cafés take a filled-in suggestion more readily than a blank form,growth/ideas/t7.md
```

The note on the north star's widget, on 3 November, says "T7 live: standing order suggested after the second order", so the rise that follows has its reason beside it. The meeting note on 1 December records the honest limit: a before-and-after reading is weaker than a split test; November had no holiday and nothing else shipped for cafés, so the team keeps T7 and plans a split test of the discount idea next. The growth lead's café ads start in December, with the activation rate as their guardrail.
