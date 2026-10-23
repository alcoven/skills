# Templates and a worked example

The shapes of the documents discovery leaves behind, then one problem taken from request to decision. Keep each document short; a reader should get the decision in a minute.

## The discovery note

One per target problem, at `discovery/<slug>.md`. It holds the decision and the evidence for it.

```markdown
# [The problem, in a few words]

- Status: exploring | testing | decided
- Outcome: [the measure], [today's reading] ([source], [date]); target [n] by [date]
- Trio: [product], [design], [engineering]
- Asked by: [who, where, date], if it started as a request

## The problem

[In the customer's words: who has it, how often, what they do today. Each claim with its source and date.]

## Why this problem

[Its place on the tree. How many customers have it, how often, how much it hurts, how it serves the strategy.]

## Ideas compared

| Idea | In one line | Riskiest assumption | Test | Pass line | Result |
|---|---|---|---|---|---|
| A | | | | | |
| B | | | | | |
| C | | | | | |

## Decision

[Build, change and test again, park, or drop. Why, in two or three sentences. How sure we are, and the kind of evidence behind it. What was dropped and why. What we will measure after release, and on what date.]

## Open risks

[Assumptions the team went ahead without testing, and who decided.]
```

## The interview snapshot

One page per conversation, written straight after it, at `discovery/interviews/YYYY-MM-DD-<who>.md`. Use a first name or a role, never more personal detail than the team needs.

```markdown
# [First name or role], [company or kind of customer], [date]

- Quick facts: [role, size, how long a customer, anything that sets context]
- Held by: [who from the trio]

> "[One memorable quote, word for word.]"

## The story

[The specific time they described, as steps: what happened first, then, then. What they did instead when it went wrong.]

## Opportunities heard

- [A need, pain or wish, in their words where possible.]

## Insights

- [Anything worth keeping that is not an opportunity.]
```

## The opportunity tree

Kept as a nested list at `discovery/opportunities.md`. Each opportunity names the snapshots it came from, so anyone can check it.

```markdown
# Opportunities: [the outcome]

Outcome: [measure], [today's reading] ([date]); target [n] by [date].
Last revisited: [date], after [n] conversations.

- [Moment in the customer's week]
  - [Opportunity] ([snapshot], [snapshot])
    - [Smaller opportunity] ([snapshot])
- [Moment]
  - [Opportunity] ([snapshot]) ← target, chosen [date]
    - Idea A, idea B, idea C: see discovery/[slug].md
```

## The assumption table

```markdown
| Assumption, as something a person does | Idea | Kind | Matters (high, low) | Evidence (strong, some, none) | Test |
|---|---|---|---|---|---|
| [Regulars set up a standing order in their first week] | B | value | high | none | [prototype test] |
```

Kinds: value, usability, feasibility, viability, ethics. Test first the rows that matter most and have least evidence.

## A worked example (invented)

Crumb is an app independent bakeries use to take pre-orders from their regulars. Its trio is a product manager, a designer and an engineer. The first outcome in Crumb's strategy (strategy/2026-q4.md) is bakeries taking 20 or more repeat pre-orders a week: 18 of 140 bakeries on 20 October, with a target of 45 by 31 December. All names and numbers here are invented.

**The request.** On 14 October, a salesperson writes: "Rise & Co want loyalty points. They're our biggest bakery. Can we get it into next sprint?"

**Step 1, the outcome.** The product manager writes the outcome at the top of a new note, `discovery/regulars-reorder.md`, with the reading from the numbers.

**Step 2, the problem.** The product manager asks the salesperson for the last time Rise & Co hit the problem. The salesperson passes on the owner's words: "My Saturday regulars forget to order by Thursday, then they buy at the café next door." The problem is regulars missing the cut-off; points are one guess at a fix.

**Step 3, the tree.** The trio has seven snapshots from the last month. Under the outcome they group what they heard:

- Deciding to order
  - Ordering every week means remembering it and typing it all again ← target
    - "I forget until the cut-off has passed" (4 of 7)
    - "I order the same thing every week and type it all again" (5 of 7)
- Baking
  - "On Wednesday I can't tell how many loaves to bake for Saturday" (3 of 7)
- Collecting
  - "The pick-up queue is as long as the normal one" (2 of 7)

"Is there more than one way to answer this?" Yes, so the target is a real problem. They pick it because it came up in six of the seven snapshots, it happens every week, and it sits on the strategy's outcome.

**Step 4, conversations.** The designer books two more calls this week, one with a regular and one with a bakery owner, and the product manager adds a weekly task for the trio's next four conversations.

**Step 5, ideas.** With the engineer in the room:

- A. Loyalty points (the request).
- B. A standing order: set it once, it repeats every week until the customer skips or pauses.
- C. A Thursday reminder with "same as last week" in one tap.
- D. Without software: staff ask regulars at the till to sign up for a weekly order on a card, and enter it for them.

**Step 6, assumptions.** The riskiest, by how much they matter and how little evidence there is:

| Assumption | Idea | Kind | Matters | Evidence | Test, and pass line |
|---|---|---|---|---|---|
| Many regulars order the same thing most weeks | B | value | high | some | Order data: share of regulars whose last four orders were identical. Pass: a third or more. |
| Regulars set up a standing order without help | B | usability | high | none | Prototype with six regulars. Pass: four or more finish unaided. |
| Bakeries accept orders that repeat without a fresh confirmation | B | viability | high | none | Calls with five owners about their last no-show. Pass: three or more accept, with a skip rule. |
| Regulars order from a Thursday reminder | C | value | high | none | Two bakeries text their list by hand for two weeks. Pass: a quarter or more order from it. |
| Points change when regulars order | A | value | high | some | Ask five regulars about the last time they used a stamp card. Pass: three or more say it changed when they came. |
| Saved cards can be charged each week | B | feasibility | high | none | The engineer tries it with the payment provider in test mode. Pass: works in two days. |
| Regulars are never charged for a week they forgot about | B | ethics | high | none | Design rule: a notice the day before, and skip in one tap. Checked in the prototype test. |

**Step 7, tests.** Over eight days: 41% of regulars had four identical orders in a row (pass). Five of six regulars set up the standing order unaided (pass). Four of five owners accept it if customers can skip by Wednesday (pass, with a condition). The hand-sent reminder brought 22% of each list to order (just under the line). Two of five regulars said a stamp card changed when they came (fail). The engineer's spike worked in a day (pass).

**Step 8, decision.** The product manager writes:

> Build B, the standing order, with C's Thursday message reused as the skip-a-week notice. Park A: regulars collect stamps without changing when they come. Confidence: test results with real customers, short of launch data. Next: a working version with three bakeries for three weeks, pass line 15% of each bakery's regulars on a standing order. We read the outcome again on 31 December.

The product manager hands the note out to the salesperson and the head of sales to read, with the passage that answers Rise & Co, and the salesperson offers Rise & Co a place among the first three bakeries. The designer takes the standing order into the ux-designer skill for the experience.

**What went right.** The request was a fix; the problem behind it was regulars forgetting and retyping. The team compared four ideas in eight days, the requested one among them, and each test had its pass line before it ran.
