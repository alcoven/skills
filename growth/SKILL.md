---
name: growth
description: Grows a product some people already want. Checks must-have first (the Sean Ellis survey, retention by cohort), finds the aha moment, sets a north star and a growth model, then runs a weekly test cycle. Use when someone asks "how do we grow", "why don't new people stick", "what should we test next", "set up a growth team", "should we spend on ads", "build a referral programme", "is our activation good", or plans a growth sprint or a weekly growth meeting. Puts the order before the tactics (must-have, then the leaks, then more people in), names the common mistakes (growing before must-have, too many channels at once, copying a famous company's hack, a vanity north star, tests too small to read, learning nobody wrote down) and keeps a test log the team learns from.
license: MIT
metadata:
  source: https://alcoven.co/skills/growth
  version: "2"
---

# Growth: grow what people already want

Growth work multiplies what the product already does for people. If few would miss it, more people in means more people leaving. So first ask: would a group of customers be very disappointed to lose it? Then find the moment they first get the value, the number that counts it, and the few levers that move it, tested every week and written down. The person asking usually has a target, a few people who can ship, and a few weeks, and fears spending them on tactics that don't stick. The method is Sean Ellis and Morgan Brown's *Hacking Growth* (2017) and the practitioners who built on it; depth and sources are in [references/method.md](references/method.md).

## What you need

- **The brief:** who the product is for and what it does for them; ask if it is missing.
- **Must-have evidence:** answers to "How would you feel if you could no longer use it?", and retention by cohort (of the customers who started in a given week or month, the share still active weeks later). Ask for retention by cohort first.
- **The numbers on the way in:** visits, sign-ups, activation, active and paying customers, referrals, by week and by source, each with its definition.
- **The test log** and the plan with its targets, if they exist, and **who can ship** a product change this week.

Look in `growth/`, `metrics/`, `numbers/`, `gtm/` or `analytics/`. If you only have what was pasted, work with it and list what is missing.

**With no numbers yet,** get rough ones before anything else: in an hour, from the billing records, how many customers paid each month for the last six months, who stopped, and how each current customer found the product; then, this week, three calls with customers who stayed and three who left. Ask for nothing more until those are in.

## Plain words, the right customer, small numbers

- **Say it in the person's words first.** "Do enough customers love it" before "must-have", "the moment a new customer first gets value" before "aha moment", "the one number that shows customers getting value" before "north star". Define a term once, in a line, when it helps.
- **Ask which customer.** When the one who pays differs from the one who uses (a shop and its shoppers, a company and its staff), ask which side "customers" means, and check both: the payer rarely keeps paying for long once the users stop.
- **With few customers, change the method.** With a few dozen customers, a survey percentage means little and growth loops have too few people to turn. Count by hand, talk to the customers who stayed and the ones who left, and look for what the stayers did early. Use the 40% survey line (step 1) and the loops once there are enough customers for a share to mean something.
- **If customers are leaving, start there.** Hand over to the retention skill, if the project has it, before any work on bringing in more; for a broad "how do we make more money", the product-coach skill finds where it leaks first.

## The method

Scale it to the ask. One tactic ("should we add a referral link?") gets step 1 as a quick check and step 6 for the test. A growth plan, a new growth team or real money on acquisition gets every step.

1. **Check must-have first.** The survey: the share of recently active customers answering "very disappointed" to Sean Ellis's question, where 40% is the line Ellis drew after comparing nearly a hundred startups. Retention: cohort curves that flatten at some level, which Brian Balfour rates the stronger signal. If the evidence is missing or below the line, say so and offer the must-have engine before any tactic: start from the customers who answered "very disappointed", learn what they love, find what holds back the "somewhat disappointed" who love the same thing, and split the next work between the two (Rahul Vohra at Superhuman). **Output:** met, not met or unknown, with the evidence and its date.
2. **Find the aha moment:** when a new customer first gets the value (the first order delivered, the first document a teammate opened). Compare people who stayed with people who left: which action did the stayers take early, and how soon? Ask a few of each (the customer-interviews skill helps, if the project has it). Write it as an action and a time ("sets up a standing order within 14 days"), a hypothesis until retention confirms it. The share of new customers who reach it is activation. **Output:** the aha moment, its activation rate, the steps before it.
3. **Set the north star and the growth equation.** The north star counts value delivered, grows as more customers get more of it, and leads revenue without being revenue (Ellis). Break it into the inputs that multiply or add up to it, such as new teams × share activated in week one × share still active in week eight. To choose, define and read these numbers, use the metrics skill if the project has it. **Output:** the north star, 3 to 5 inputs, the equation in one line.
4. **Draw the growth model.** Write how new customers arrive, as loops where you can: a cycle whose output brings the next input, like a shared page that brings a reader who shares the next page (Reforge). Check Brian Balfour's four fits: market and product, product and channel (products are built to fit channels), channel and model (what a customer pays must cover what the channel costs), model and market. If the product gets better as more people in a group use it, fill one atomic network (Andrew Chen: the smallest group where it works on its own) before the next. **Output:** the main loop, its weakest step, the weakest fit.
5. **Pick one focus area.** Fix the leaks before pouring more in. Ellis's order: activation, then engagement and retention, referral, revenue, and acquisition last. Choose the stage with the weakest step, one input metric, and a target with a date. In acquisition, work one or two channels at a time. **Output:** focus area, metric, baseline and target, each with its date.
6. **Run the weekly test cycle.** Analyse the focus area; collect ideas from anyone; prioritise by scoring Impact, Confidence and Ease from 1 to 10 (ICE, from *Hacking Growth*); test; write down what was learned. Each idea carries its evidence, the metric it should move, and a pass line set before it starts. For test design, sample size and stopping rules, hand over to the lean-experiments skill if the project has it. **Output:** this week's tests, each a row in the test log.
7. **Hold the weekly growth meeting.** Same agenda every week: the north star and inputs; tests launched against plan; what finished and what it taught; this week's tests; the idea pipeline. Someone who can ship product changes is in the room. **Output:** a short dated note of decisions and learnings.
8. **Review the model monthly or quarterly.** Channels wear out as novelty fades and competitors arrive (Andrew Chen), and the fits shift when the product, price or market changes. Re-run the must-have survey on newer cohorts; Vohra warns the score can fall as the customer base broadens. **Output:** changes to the model, proposed for the person's yes.

## Keep it current

*Hacking Growth* came before three shifts (method.md has the sources). With product-led growth, people find, try and buy without a sales call, so activation and the step from free to paid carry the growth. Buyers ask AI assistants what to use, and the engines name products mentioned and cited across the web: treat that as a channel, asking the engines your buyers' questions monthly and recording who is named. Community and content work as loops: a useful post brings a reader who shares the next one.

## Common mistakes

1. **Growing before must-have.** People sent to a product few would miss leave, and some become critics. Instead: step 1 first; below the line, work on the product for the people who love it (Ellis and Brown).
2. **Pouring in while retention leaks.** Paying for new customers while most of them leave buys the same loss at a larger size. Instead: fix activation and early retention first.
3. **Too many channels at once.** Five half-run channels give five unreadable results. Instead: test a few cheaply, then put the effort into the one that works (the Bullseye in Weinberg and Mares's *Traction*).
4. **Copying a famous company's hack.** A tactic from another market, years ago, rarely carries over. Instead: borrow the principle, test it on your customers, expect it to fade.
5. **A vanity north star.** Total sign-ups, page views and downloads only grow and say nothing about value (Eric Ries). Instead: count value received, such as teams that shared a document this week.
6. **Tests too small or too short to read.** A button colour on a trickle of visits, or a winner called on day two, teaches nothing. Instead: changes big enough to matter, pass line and run length set first.
7. **Learning nobody wrote down.** The team repeats a failed test. Instead: a log row for every test with one line of learning, losses included.
8. **A growth team without engineering.** Growth lives in the product (onboarding, invites, pricing), so a marketing-only team can change ads and emails and little else. Instead: a small cross-functional team with someone who ships code (Ellis and Brown).
9. **Stages run as separate kingdoms.** Acquisition brings people who never activate, and retention pays for it (Reforge). Instead: judge every test by the north star and its guardrails.
10. **Reading the survey's average.** The total hides the group for whom it is already a must-have (Vohra). Instead: segment the answers; build for the highest-scoring group.

## Speaking up

When a step was skipped or the evidence points elsewhere, say it once, with the evidence and the cheapest check: "Before we buy ads: of September's new customers, [n] were still active in week four (product dashboard, read 22 Oct). A short survey of recent customers would tell us within a week whether to fix the product first. Shall I draft it?" Then do what the person decides, note the risk where the team will see it (the plan, the test log), and carry on. Never refuse work over a skipped step, and never repeat the warning.

## What you never do

- Invent a number, a benchmark or a "typical" rate. A benchmark appears only with its source and date.
- Trick customers: fake scarcity, invites sent from someone's contacts without their clear yes, hidden cancellation, pre-ticked consent.
- Send messages, invite anyone, publish or spend money without the person's yes.
- Call a test before its pass line and run length, or move the pass line after seeing the data.
- Change the plan, the targets or the north star on your own: propose the edit.

## In Alcoven

Pass the project's slug and cite by § address.

1. `open_project`: the brief, the home widgets with their readings, and what is agreed (a north star on record is settled).
2. `numbers` on the product's `.source.md`: the north star and the focus input `by: "week"`, with `compare: "the period before"` or a target; `by:` a field such as `source` shows which channel brings customers who stay. The answer ends with the question as a widget file: offer to keep the north star on the home (four widgets at most there):

```markdown
# Teams sharing a document each week

- Show: line
- Measure: teams sharing
- From: product.source.md
- By: week
- Compare: target [n] by 2026-12-31
- On home: yes

Why it's here: our north star; every growth test is judged by it.
```

3. `add_rows` on the test log, `growth/tests.csv`: a row when a test starts, one when it ends ([references/test-log.md](references/test-log.md) has the columns and a `.source.md` that turns the log into numbers).
4. `add_note` with `day:` on the north star's widget for the day a test launched or a change shipped: the reason shows in the margin at that day.
5. `add_document` for the growth model and meeting notes (show the text first), `hand_out` the north star and targets for agreement, and `task` an owner and due day for each test.

## Elsewhere

Keep `growth/model.md`, `growth/tests.csv` and `growth/meetings/YYYY-MM-DD.md`. Quote every number with its source and date; `git log` or the tool's history shows what shipped when. In a chat with no files, ask for retention by cohort and the test log, and hand back rows to paste.

## Files

- [references/method.md](references/method.md): each framework in depth, what changed by 2026, and the sources.
- [references/test-log.md](references/test-log.md): the test log and its `.source.md`, the idea card, the meeting note, the growth model, and a worked example.
