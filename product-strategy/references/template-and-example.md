# The strategy document, and a worked example

One document holds the strategy, its outcomes and its roadmap, so nobody has to reconcile three. Keep it to a page or two; a reader should get the choice in a minute.

## The template

```markdown
# [Product] strategy, [period]

- Status: draft | agreed [date] | replaced by [document]
- Owner: [who]
- Agreed by: [who, and when]
- Next review: [date]

## Vision

[One or two sentences: the future for customers that this strategy moves toward.]

## Diagnosis

[What is going on, what makes it hard, and the crux: the part that matters most and that we can act on. Each claim with its source and date.]

## Guiding policy

[One or two sentences: our approach to the crux.]

Considered and set aside:
- [Another approach], because [why].

## Coherent actions

1. [Action]. Owner [who]. Needs [people, money, time].
2. [Action that supports the first.]

## What we will not do

- [Something people want or have asked for]. Why: [reason]. Look again: [date or event].

## Outcomes

| Outcome | Measure | Today | Target | Guardrail |
|---|---|---|---|---|
| [What customers or the business will do differently] | [How it is counted, and where] | [Reading] ([date]) | [n] by [date] | [What must not get worse] |

## Roadmap

**Now**: [problems teams are working on this cycle, each with its outcome]
**Next**: [problems being shaped and tested]
**Later**: [directions]

Dated commitments: [only real ones, each with the reason for the date and the discovery it rests on].

## Insights this rests on

- [Insight] ([source], [date]). Evidence | belief.

## Changes

- [Date]: [what changed, and why].
```

## A worked example (invented)

Crumb is an app independent bakeries use to take pre-orders from their regulars. It has nine people: Maya (product), Tomás (design), three engineers including Ines, Dev (sales), Lena (customer success), and the two founders. All names and numbers here are invented.

### The first draft, reviewed

The founders' draft for the fourth quarter read: "Our strategy is to grow to 200 bakeries, launch a marketplace, add point-of-sale integrations and become the leading platform for bakeries."

The review, in short:

- **Strong:** it is short, and it names a number the team can track.
- **Goal mistaken for strategy:** "200 bakeries" is where they want to be. Nothing says what stands in the way.
- **No diagnosis:** the draft never mentions that a large share of new bakeries cancel within three months (numbers/retention, 20 Oct).
- **Fluff:** "the leading platform for bakeries" commits the team to nothing.
- **Bad strategic objectives:** three large bets for three engineers, pulling in different directions.
- **Suggested fix:** start from why bakeries stay or leave, choose one approach, and say what Crumb will not do this quarter.

### The strategy, after the founders took the review on

```markdown
# Crumb strategy, Q4 2026

- Status: agreed 24 Oct 2026
- Owner: Maya
- Agreed by: the whole team, 23 to 24 Oct
- Next review: 9 Jan 2027

## Vision

Every independent bakery knows on Wednesday what its regulars want on Saturday.

## Diagnosis

Bakeries stay with Crumb when their regulars pre-order every week: of the 18 bakeries taking 20 or more repeat pre-orders a week, one has cancelled in six months. Most others use Crumb for holiday cakes and drift off, because their regulars still order at the counter: 26 of the 61 bakeries that joined from April to June had cancelled by October, and 24 of those never passed five repeat orders a week (numbers/retention, 20 Oct). In seven interviews, owners said they have no time to move regulars over (discovery/interviews, Sept and Oct).

The crux: getting a bakery's regulars to move their weekly order to Crumb in its first month. It is hard because regulars have a habit and owners have no time. It is within reach, because onboarding and the ordering flow are ours to change.

## Guiding policy

Make Crumb the weekly ordering habit for a small bakery's regulars, and judge every piece of work by whether more regulars order every week.

Considered and set aside:
- Chains: bigger contracts, but they need reporting and integrations far from regulars, and we have three engineers.
- A marketplace to match Ovenly's: it brings bakeries new customers, while owners told us their problem is keeping the ones they have.

## Coherent actions

1. Onboarding ends at the first ten regulars, with a counter card and a message the owner sends to their list. Owner Tomás with Lena.
2. The product trio works only on the weekly repeat order this quarter (discovery/regulars-reorder.md). Owner Maya.
3. Sales goes to independent bakeries that already have regulars, and pauses outreach to chains. Owner Dev.
4. Lena calls every new bakery in its third week to check how many regulars order. Owner Lena.

## What we will not do

- Multi-store reporting for chains. Why: it serves chains, which we are not pursuing. Look again: when 100 bakeries take 20 or more repeat orders a week.
- A marketplace. Why: the problem owners describe is keeping regulars. Look again: Q2 2027.
- Point-of-sale integrations. Why: three engineers, and they serve counter sales. Look again: if ten of the bakeries with 20 or more repeat orders ask.
- Custom work for a single bakery.

## Outcomes

| Outcome | Measure | Today | Target | Guardrail |
|---|---|---|---|---|
| More bakeries' regulars order weekly | Bakeries taking 20+ repeat pre-orders a week | 18 (20 Oct) | 45 by 31 Dec 2026 | No-shows on pre-orders stay under 5% (3% today) |
| New bakeries reach their regulars fast | Share of the month's new bakeries with 10+ regulars ordering in month one | 29% (Sept) | 50% by 31 Dec 2026 | Support tickets per bakery do not rise (1.2 a month today) |

## Roadmap

**Now**: regulars forget and retype their weekly order (outcome 1); onboarding to the first ten regulars (outcome 2).
**Next**: owners can't tell how much to bake for the weekend; pick-up queues.
**Later**: regulars bringing friends; bakeries with two or three shops.

Dated commitments: Christmas pre-orders open by 20 Nov, because the season sets the date; last year's holiday flow works, so only the copy changes.

## Changes

- 24 Oct 2026: first agreed version.
```

If Crumb used OKRs, the first outcome would read: Objective, "Bakeries' regulars order through Crumb every week"; key results, "18 to 45 bakeries with 20 or more repeat pre-orders a week" (stretch) and "29% to 50% of new bakeries reach ten regulars in month one" (committed).

### Agreeing it

Maya hands the strategy out for agreement. Dev's part is the not-do list and action 3; Lena's is action 4 and the second outcome; the trio's is the first outcome and the roadmap's Now. Before the review date, she asks Dev and Ines separately to say the strategy in two sentences. Both mention regulars ordering every week; Dev forgets the guardrail, so the next version moves it next to the target.

### Checking proposed work

Three proposals arrive in the following week:

```markdown
**Multi-store reporting for Hearth Bakeries** (Dev, sales notes, 18 Oct)
- Serves: none of the outcomes.
- On the not-do list: yes ("Multi-store reporting for chains").
- Verdict: doesn't fit. Reply to Hearth with the date we look again.

**Loyalty points for Rise & Co** (Dev, 14 Oct)
- Serves: outcome 1.
- Fits the guiding policy: yes, if it gets regulars ordering weekly.
- Evidence: one customer's request, low on the confidence meter.
- Appetite: two weeks at most.
- Verdict: fits, to discovery (discovery/regulars-reorder.md), beside other ideas for the same problem.

**A redesign of the bakery dashboard** (Tomás, 21 Oct)
- Serves: none directly; outcome 2 only if it shortens the way to the first ten regulars.
- Pushes out: onboarding work for outcome 2.
- Verdict: doesn't fit this quarter as proposed. Consider reshaping it around the first ten regulars, or put it in Later.
```

**What went right.** The draft's goal became one outcome with a date and a guardrail. The not-do list answered the chain's request in one line, without a debate. The loyalty request went to discovery instead of the sprint.
