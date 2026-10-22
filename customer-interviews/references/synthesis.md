# Synthesis, surveys and AI

How several interviews become findings a team can act on, when a survey helps and how it misleads, and what an AI may and may not do in research.

## From notes to findings

1. **Gather the notes for one round.** List them with their dates, segments and interviewers. Say which planned interviews did not happen.
2. **Break each note into units.** One fact, story moment or quote per unit, each tagged with its note, its date and whether it is Did, Said or We think. A quote stays word for word.
3. **Group the units by what they share** (affinity mapping: clustering related observations so patterns show; NN/g describes the method). Start with no categories; let groups form, then split groups that hold two ideas. Name each group in the customers' words, as a short sentence ("I re-type every order from my messages"), never as a feature.
4. **Count people, once each.** One talkative person who said it five times is one person. Give the count against the total and per segment: "5 of 7 (4 of 4 owners, 1 of 3 staff)".
5. **Weigh the evidence** with the ladder below. A group built on Did lines outranks one built on Said lines.
6. **Look for what breaks the pattern.** Contradictions, outliers and segments where the finding does not hold. Keep them; they often mark the edge of who the product is for.
7. **Write each finding** in the shape below, with its quotes and their sources.
8. **Answer the research questions.** For each: what the evidence supports, what it does not, confidence, and the next step.

## The evidence ladder

From strongest to weakest:

1. **Money or time already spent** on the problem: a paid tool, a hire, hours each week.
2. **A switch or a workaround they built:** they left a product, made a spreadsheet, pay a freelancer.
3. **A specific past story** with a date, a cost and a consequence.
4. **A commitment given** in the interview: a second meeting, an introduction, a deposit.
5. **Generic claims** about habits: "I always", "we usually".
6. **Opinions and predictions:** "I would use it", "I'd pay 20 a month".
7. **Compliments.**

Report 5 to 7 only as what people said, never as evidence of demand.

## Writing a finding

```markdown
### F2. Owners re-type phone and chat orders into a spreadsheet by hand

- Who: 5 of 7 (4 of 4 owners, 1 of 3 staff).
- Evidence: Did. Four showed or described last week's spreadsheet; two named the hours (P1, P4).
- Quotes: "Every Sunday night I copy the week's orders off my phone." (P1, 2026-10-14)
- Against: P6 takes orders only through a shop page and re-types nothing.
- Confidence: medium. Consistent across owners; staff barely covered.
- Does not show: how many bakeries work this way, or that they would pay to stop.
```

## Separate what people did from what they said

Write Did, Said and We think in separate lines from the first note to the last finding. "Three said they would switch for reminders" and "three built their own reminder system" are different findings, and only the second says the problem costs them enough to act. Hall's book makes the same split between what you observed and what you interpreted.

## What interviews can and cannot tell you

| Interviews can show | Interviews cannot show |
|---|---|
| That a problem exists, in whose life, and how it plays out | How many people in the market have it |
| The words people use for it | Which wording will win on a page (test it) |
| What they tried and why it fell short | Whether they will pay a given price (ask for a commitment, or test it) |
| What pushed them to switch and what held them back | What they will do next year |
| The real alternatives, including doing nothing | Which of your ideas is best (they are not designers) |

When a decision needs what the right column holds, hand over: a survey to size, an experiment with a pass line set first (the lean-experiments skill), or the measures (the metrics skill), if the project has them.

## Surveys and their traps

Erika Hall opens her essay On Surveys (2015) by calling them "the most dangerous research tool", often misunderstood and misused: they are easy to send, and the numbers that come back look true whatever their quality. A survey earns its place after interviews, to size what the interviews found, when you know the words and the options people use.

Before sending one, check:

- **Can people answer truthfully?** Hall's test. People can report what they did last month; they cannot report why they do things or what they will do.
- **Leading or loaded wording.** "How much did our new dashboard help you?" assumes it helped.
- **Two questions in one.** "Was setup fast and easy?" cannot be answered for half of it.
- **Predictions.** "Would you buy...?" and "How likely are you to...?" measure hope.
- **Options you invented.** Use the words and categories the interviews gave you, plus "other".
- **Who answers.** The keen and the angry reply; the busy middle does not. Say who the sample is and who it misses.
- **What you will do with each answer.** Decide before sending what result would change the plan.

**Net Promoter Score.** NPS asks how likely someone is to recommend you, on a 0 to 10 scale. Jared Spool's critique (2017): it asks for a prediction rather than past behaviour, the 11-point scale adds noise, and the calculation throws away information. Keiningham and colleagues (2007) replicated the original claim and found no support for NPS predicting growth better than other measures, such as the American Customer Satisfaction Index. Jeff Sauro's review of the research (MeasuringU, 2019) concludes the literature qualifies NPS rather than discredits it. Use it, if at all, as one trend among others, with a follow-up asking what happened, and never as the measure of whether a product is wanted.

## AI in research

An AI is useful beside the team. It can:

- draft the interview guide from the decision, and check it for leading or hypothetical questions;
- transcribe, and pull every quote on a theme with its line;
- make a first pass at tagging units and grouping them, for a person to check;
- check a synthesis: does every finding have a count, a source and a date? Does any quote fail to appear in its transcript?

It never:

- **invents what customers said,** fills a gap in a note, or improves a quote;
- **stands in for customers.** NN/g's review of "synthetic users" (Rosala and Moran, 2024) found AI-generated participants give shallow and overly favourable feedback, seem to care about everything, and cannot report real past behaviour; at most they help with desk research and early hypotheses, which must then be tested with real people;
- **turns a pattern into a count it did not make,** or a count into a share of the market.

Every quote in a finding must be found word for word in a transcript or note on record.

## Sources

Read 2026-10-22 unless stated.

- Rob Fitzpatrick, *The Mom Test: How to talk to customers and learn if your business is a good idea when everyone is lying to you* (2013). momtestbook.com. Summaries checked: Matt Lynch's book report (mtlynch.io/book-reports/the-mom-test) and Yevgeniy Brikman's review (ybrikman.com, 2023). A revised second edition is listed by its publisher as forthcoming; this skill follows the 2013 edition.
- Bob Moesta with Greg Engle, *Demand-Side Sales 101: Stop Selling and Help Your Customers Make Progress* (2020); Moesta's talk "Demand-Side Sales 101", Business of Software 2020 (businessofsoftware.org/2020/10/demand-side-sales-101-bob-moesta-online), for the timeline stages and the four forces.
- The Re-Wired Group, jobstobedone.org: the live mattress switch interview with Moesta, Chris Spiek and Jason Fried, and the "Forces Friday" episodes.
- Clayton M. Christensen, Taddy Hall, Karen Dillon and David S. Duncan, *Competing Against Luck: The Story of Innovation and Customer Choice* (HarperCollins, 2016).
- Teresa Torres, *Continuous Discovery Habits* (Product Talk, 2021); "Customer Interviews" (producttalk.org/customer-interviews, updated 2026); "Interview Snapshots" (producttalk.org/interview-snapshot, 2024).
- Steve Portigal, *Interviewing Users*, 2nd edition (Rosenfeld Media, 2023), and his talk slides on question types and follow-ups.
- Erika Hall, *Just Enough Research*, 2nd edition (A Book Apart, 2019), which adds a chapter on surveys; "On Surveys" (Medium, 23 Feb 2015; republished at articles.centercentre.com).
- Jakob Nielsen, "First Rule of Usability? Don't Listen to Users" (NN/g, 2001). nngroup.com/articles/first-rule-of-usability-dont-listen-to-users
- Amy Schade, "Avoid Leading Questions to Get Better Insights from Participants" (NN/g, 2017). nngroup.com/articles/leading-questions
- NN/g, "Affinity Diagramming". nngroup.com/articles/affinity-diagram
- Maria Rosala and Kate Moran, "Synthetic Users: If, When, and How to Use AI-Generated 'Research'" (NN/g, 21 June 2024). nngroup.com/articles/synthetic-users
- Greg Guest, Arwen Bunce and Laura Johnson, "How Many Interviews Are Enough? An Experiment with Data Saturation and Variability", *Field Methods* 18(1), 2006.
- Monique Hennink and Bonnie Kaiser, "Sample sizes for saturation in qualitative research: A systematic review of empirical tests", *Social Science & Medicine* 292, 2022.
- GOV.UK Service Manual, "Getting users' consent for research" (updated 2018). gov.uk/service-manual/user-research/getting-users-consent-for-research
- Jared Spool, "Net Promoter Score Considered Harmful (and What UX Professionals Can Do About It)" (Center Centre, 20 Dec 2017).
- Timothy Keiningham, Bruce Cooil, Tor Wallin Andreassen and Lerzan Aksoy, "A Longitudinal Examination of 'Net Promoter' and Firm Revenue Growth", *Journal of Marketing* 71(3), 2007 (reference checked via MeasuringU).
- Jeff Sauro, "Has the Net Promoter Score Been Discredited in the Academic Literature?" (MeasuringU, 2019). measuringu.com/nps-discredited
