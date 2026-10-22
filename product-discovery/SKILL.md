---
name: product-discovery
description: Decides, one customer problem at a time, what is worth building before it is built, by finding the outcome to move and the problem behind a request, comparing several ideas and testing the riskiest assumptions in days. Use when someone asks "should we build this", "is this feature worth it", "a customer asked for X", "what should we build for this goal" or "test this idea", or brings a feature request, a stakeholder's idea or a prototype to judge. Works with the product manager, designer and engineer together, keeps a weekly conversation with customers going, and writes each decision down with the evidence behind it.
license: MIT
metadata:
  source: https://alcoven.co/skills/product-discovery
  version: "1"
---

# Product discovery: learn what is worth building, then build it

At least half of a team's ideas will not work, and the ones that do usually need several rounds before they pay off (Marty Cagan's two "inconvenient truths", 2013). Discovery tells the two apart before weeks go into building: find the problem, try several ideas against it, and test what must be true for each, in days. The person asking usually has a request in hand (a big customer wants an export) and a week at most. They fear a month spent on something nobody uses, and saying no to someone important without a reason. Keep the pass in proportion to the stakes, and end it with a decision and its evidence.

The strategy sets the outcomes this work serves (the product-strategy skill). Discovery works one problem at a time inside them.

## What you need

- **The outcome**: a change in what customers do, with a measure and today's reading, from the strategy, the goals or the numbers. If there is none, ask: "If this works, what will customers do differently, and how would we see it?"
- **The request or idea**, in the words it arrived in, and who brought it.
- **The evidence on record**: interview notes, support tickets, sales notes, usage numbers, earlier discovery notes, in folders such as `discovery/`, `research/` or `feedback/`, and decisions on record.
- **The trio**: a product manager, a designer and an engineer, working together from the start (Teresa Torres's term). If no engineer is named, ask who it is.
- **The business's constraints**: dates, money, legal limits, partners, what sales has promised.

## Size the pass

| The work | Examples | The pass |
|---|---|---|
| **Small or easy to undo** | a label, a setting, a change behind a flag | Name the problem and the assumption that matters; ship to a few customers, watch one number. |
| **Medium** | a feature, a new step in a flow, an integration | Steps 1 to 8, over a few days. |
| **Large or hard to undo** | a new product area, a pricing model, custom work for one big customer | The full method, more than one round of tests, and the decision handed out to the people it affects. |

## The method

1. **Start from the outcome**, as a change in customer behaviour with its measure and today's reading: "bakeries taking 20 or more repeat pre-orders a week: 18 (numbers, 20 Oct)". Prefer what the team can move in weeks to what it can only hope to move, such as revenue. *Output: the discovery note's first line.*
2. **Find the problem behind the request.** Ask whoever brought it for the last time a customer hit the problem: what they were doing, what went wrong, what they did instead; then how many customers have it, and how often. Write it in the customer's words with source and date. With no real instance behind it, it is a hypothesis; mark it so. *Output: the problem, who has it, how often, the evidence and its age.*
3. **Map the problems around the outcome.** Outcome at the top; under it the needs, pains and wishes customers described in their stories (Torres's opportunity tree), grouped by the moment in their week where each happens. To catch an idea dressed as a problem, ask "is there more than one way to answer this?" Pick one target by how many people have it, how often, how much it hurts and how well it serves the strategy; leave effort out for now. *Output: the tree, target marked.*
4. **Talk to customers every week.** The trio holds at least one conversation a week about a specific recent time ("tell me about the last time you...") and writes a one-page snapshot straight after. Revisit the tree every three or four conversations. For running interviews, use the customer-interviews skill if the project has it. *Output: a snapshot per conversation.*
5. **Generate at least three ideas for the target**, with the engineer in the room: they know what has just become possible and what is costly. Include one that is not software (a message, a manual service). *Output: the ideas, a line each.*
6. **List what must be true for each idea.** Customers want it (value), can work out how to use it (usability), it can be built (feasibility), it works for the business (viability: cost, sales, legal, brand), it does no harm (ethics). Walk the idea step by step as a customer would to find them. Write each as something a person does ("regulars set up a standing order in their first week"), and mark how much it matters and how much evidence exists. *Output: the assumption table; the riskiest matter most and have least evidence.*
7. **Test the riskiest few, across the ideas.** The smallest test that answers each in hours or days: data already held, a one-question survey about past behaviour, a prototype in front of five customers, an engineer's spike, a working prototype on real data for a few customers. Write the pass line before the test runs. Run one test on several ideas where you can, so the result compares them. For experiment design and A/B tests, use the lean-experiments skill if the project has it. *Output: each test with pass line, date and result.*
8. **Decide on the evidence, and write it down.** Compare the ideas. Rate confidence by the kind of evidence (Itamar Gilad's confidence meter: opinions and a few requests count for little, tests with real customers for more, launch data for most). Decide: build, change and test again, park, or drop. Write the decision, the evidence, what was dropped and why. *Output: the discovery note's decision; the chosen idea goes to the ux-designer skill for the experience, then to delivery.*
9. **After it ships, read the outcome** on the date you set. Expect another round; take what you learned back to the tree.

A prototype is built to learn; the product is built to earn, by engineers, to the standard customers rely on (Cagan, 2025). Cheap AI-made prototypes make that line easy to cross by accident. Prototypes, tests and evidence levels: [references/method.md](references/method.md).

## Common mistakes

Name one when you see it, once, with the evidence and the fix.

| The mistake | Why it hurts | Instead |
|---|---|---|
| **The feature request is the requirement.** "Acme wants CSV export, add it to the sprint." | The customer knows the problem; the feature is one guess at it, often copied from another tool. | Ask for the last time it happened, then compare ideas for that problem. |
| **One idea at a time.** "Should we build X?" | A yes-or-no question invites a yes; the first idea is rarely the best. | Compare at least three ideas for one problem (Torres). |
| **Testing to confirm.** Showing fans, asking leading questions. | A test built to pass will pass, and nobody learns anything. | Test what is most likely wrong, with the pass line written first. |
| **Asking customers what to build, or whether they would use it.** | Predictions of future behaviour are unreliable; people say yes to be kind. | Ask what they did last time; watch what they do with a prototype. |
| **Shipping the prototype.** | It skips security, scale, edge cases and support; customers come to rely on something nobody can run. | When an idea passes, engineers build it properly (Cagan, 2025). |
| **Discovery as a phase.** "We did research in Q1." | Learning stops when building starts, though the outcome has not moved yet. | Weekly conversations and tests beside delivery (Torres). |
| **A senior person's or big customer's idea skips discovery.** | At least half of ideas fail, whoever has them (Cagan); skipping only hides the risk. | Ask for the problem, the customers, the measure and the constraints; test their idea beside two others (Jones and Cagan, 2025). |
| **The engineer joins after the spec.** | Brought in late, they can only say no; what has newly become possible goes unseen. | The trio works together from the first interview. |
| **Features shipped count as success.** | Output rises while nothing changes for customers. | Name the outcome first; read it after release. |
| **The last interview or loudest customer sets the plan.** | One story is one data point; the plan swings weekly. | Revisit the tree every three or four conversations; size problems across customers. |

## Speaking up

- **Once, with the evidence and the cheapest check.** "This came from one customer (sales/notes.md, 14 Oct). Two calls with other bakeries this week would tell us whether it's common. Shall I draft the questions, or start the spec?"
- **Credit what the team knows first. If they go ahead, do the work**, and write the untested assumption once where the team will see it: the note, the task or the spec.
- **Match their pace.** On a deadline the check is one line. Never repeat a concern they have heard and decided on.

## What you never do

- Refuse, delay or water down work because a step was skipped. The person decides.
- Invent customer quotes, findings, test results or rates. Missing evidence is said to be missing.
- Present an assumption as a finding, or five people as proof about everyone.
- Move a pass line after the result is in. If it was wrong, say so and set a new one for the next test.
- Contact customers or send anything outside the project without the person's yes.
- Keep more about interviewees than the team needs: a first name or a role is enough.

## In Alcoven

Pass the project's slug and cite by § address.

1. `open_project`: the brief, the outcomes on the home with their readings, what is agreed (the strategy).
2. `related` with the request in a sentence: earlier interviews, notes and decisions on the same problem. `grep` for the customers' own words in `discovery/`; `numbers` for the outcome's reading and date.
3. `add_document`, after showing the person the text, for each snapshot (`discovery/interviews/YYYY-MM-DD-<who>.md`), the tree (`discovery/opportunities.md`) and each note (`discovery/<slug>.md`), with `read` set to the § addresses used.
4. `task` for the next conversation, for the trio member holding it, due on the day, standing on the tree; add the following week's when this one is done. `add_note` with `to` on the request, asking whoever brought it for the last time it happened.
5. `hand_out` the decided note (`ask: read`, with the person's own line on top) to those who asked, each with the passage that answers them. A decision that changes the strategy or a commitment goes on record (the decision-making skill).

To see when the habit stops, log each conversation with `add_rows` in `discovery/touchpoints.csv`, with a `.source.md` beside it that expects a row every week.

## Elsewhere

Keep the same documents as plain files in `discovery/`. Read the strategy, research and decisions first, use `git log` for what changed, and cite file paths. With only the conversation, ask for the outcome and the evidence, and say what you could not see.

## Files

- [references/method.md](references/method.md): the four risks, the trio, outcomes, the opportunity tree, weekly conversations, assumptions and tests, prototypes, the confidence meter, what changed since 2023, sources.
- [references/templates-and-example.md](references/templates-and-example.md): the discovery note, snapshot, tree and assumption table, and a worked example.
