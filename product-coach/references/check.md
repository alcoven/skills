# The check, in full

The six questions from SKILL.md, with what to look for in each kind of work, how to write the verdict, and one example at each of the three sizes. Use the full check for large or hard-to-undo work; for medium work, answer the six questions in a few lines.

## The six questions, with what good looks like

| Question | Good enough | Weak, say so |
|---|---|---|
| 1. The problem, and who has it | A named kind of customer, a moment in their week, their words, a source and a date | "Users want", "the market needs", a fix with no problem behind it |
| 2. The outcome | A behaviour or result that changes, a measure, a date ("weekly repeat orders from 40 to 60 by 31 Dec") | "Launch X", "improve engagement", a date with no measure |
| 3. The evidence, and its age | Several customers' past behaviour, usage data, a test result, each dated and recent | One loud customer, the team's own opinion, a survey about the future, evidence from before a big change |
| 4. The riskiest assumption | Written as something a person must do ("a studio owner invites a client in the first week"), with the cheapest check and a pass line | "It should work", or a check whose pass line is set after the results |
| 5. What is already decided | The strategy, positioning and decisions the work touches, quoted with their source | Not checked; or a conflict noticed and left unsaid |
| 6. What it displaces | The work that waits, and why this comes first | "We can do both" with no one's time counted |

## Questions by kind of work

Ask only the ones the record doesn't answer.

**A feature.** Which customers asked, and what were they trying to do when they asked? What do they do today instead? How will we know they use it (a measure, a date)? Who else must change for it to work (support, sales, docs)? What is the smallest version that does the job?

**A launch or campaign.** Who exactly is it for, and where do they already spend attention? What do we want them to do afterwards, and how will we count it? Does the message match the positioning on record? What did the last launch teach us, and is it written down? What is the budget, in money and in the team's days?

**A pricing change.** What does the customer get value from, and does the price follow it? Who pays more, who pays less, and what do we tell existing customers? What evidence says people will pay this (past behaviour, a test, a won or lost deal), apart from what they said? How do we reverse it if it hurts?

**A hire.** What outcome will this person own in their first six months? What does the team stop doing, or do worse, without them? Is the work steady, or a peak that a contractor or a tool could cover? Who will manage them, and with how much time?

**A new product or market.** Who has the problem badly enough to pay or switch today? What are they using now, including doing nothing or a spreadsheet? What must be true for this to work, ranked by risk and missing evidence? What is the smallest test that would change our minds, and its pass line? What do we stop doing to make room?

**A redesign.** What do people fail to do today, as data or recorded sessions show it? Keep the team's own dislikes out of the evidence. Which tasks are frequent and must stay fast? How will we know the redesign helped, and what must not get worse (a guardrail)? Can it ship in parts?

**A roadmap or the quarter's plan.** What is the diagnosis: the main challenge the team faces now? Which one to three outcomes does the plan serve, with measures? What is on the list only because someone senior asked? What will we not do this quarter? Which items are bets with unknowns, and what tests come first?

## Writing the verdict

Keep it to a few lines, in this shape (the example is Crumb, an invented bakery ordering app):

```markdown
**Verdict: Check first.**
The problem is real for bakeries with more than one shop (4 of 6 interviews, research/interviews/, Sep to Oct), but nothing yet shows they would move their stock lists into Crumb to solve it. Cheapest check: offer the stock import to the 3 multi-shop bakeries on the waitlist this week; pass line: 2 of 3 start an import within 7 days.
Already decided: the strategy names multi-shop bakeries as the first market (strategy.md, agreed 2 Oct). Displaces: the mobile work, two weeks.
```

Every claim cites where it came from. What you could not find is said in words ("no usage data on the project for exports").

## Three examples

**Small: the copy fix.** Maya at Crumb (a bakery ordering app) asks to change "Submit" to "Place order" on the checkout button. No check. Make the change. If the project keeps copy rules, follow them.

**Medium: the feature.** Omar at Harbor Studio (a design studio's client portal) asks for a "download all files as zip" button.
- The record: two support threads ask for it, both from the same client, dated 3 and 9 October; no usage data on downloads.
- The check, in one message: "Happy to build it. One thing first: both requests come from Lumen Coffee, and we have no numbers on how often clients download files one by one. If Lumen downloads to send files to their printer, a share link to the printer might do the job better. Shall I check the downloads log for the last month first (an hour), or build the zip now?"
- Omar says build it. You build it, and add one line to the task: "Open risk: demand seen from one client only."

**Large: the new market.** Lena, who runs Harbor Studio, wants to offer the portal to other studios as a paid product next quarter.
- The record: the brief describes the portal as internal; no interviews with other studios; the strategy (agreed in July) is to grow client work.
- The verdict: "**Rethink, then check.** Selling the portal conflicts with the strategy agreed in July (strategy.md), so that is a decision for you and Sam first. If you go ahead, the riskiest assumption is that other studios would pay for a portal when they use shared drives today. Cheapest check: five calls with studio owners about how they hand work to clients today (the customer-interviews skill has the guide), then a page with a price and a waitlist; pass line set before: 3 of 5 describe the handover as a problem, and 10 sign-ups from 200 visits."
- Then: offer the decision record (decision-making) and the interview guide (customer-interviews).

## When the person disagrees

They may know something the record doesn't. Ask what it is, add it to the check, and change the verdict if it changes the facts. If it doesn't, say so once, then do what they decide and note the open risk. Their call stands; your job was to make sure it was made with the facts in view.
