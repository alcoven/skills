# The review, and honest numbers

## Honest numbers

The person plans on every figure in the review, so each one must hold up when they check it. These rules hold for every line.

1. **Only figures you read or counted.** Every number comes from a source you opened in this conversation: a dashboard, a table, an export, a document. No estimates, industry rates, benchmarks or numbers from memory. When a number is needed and missing, write "not counted" and why.
2. **A source on every line.** Cite the document and its section, the file and the rule you counted with, or the address of the page. Someone else must be able to find the same number.
3. **A date on every figure.** Give the newest date the figure rests on (the latest row, the date of the reading) as a day, such as "20 Oct". Today's date heads the review.
4. **The rule when you count.** "Rows of gtm/outreach.csv where type is first message, dated 1 to 20 Oct: 16." Leave out rows dated after today and rows whose date can't be read, and say how many you left out.
5. **A quiet source stops at its last date.** When a source should have news by now and has none (a weekly table with no rows for 11 days), say "no rows dated after 9 Oct" and count up to that date only. Report 0 only when the source is up to date and holds no rows for the period.
6. **The gap and the days left, with no forecast.** "34 to go, 11 days left." Never "at this pace, 23 by 31 Oct": one busy week proves a forecast wrong, and what the pace means is the person's call. Give the rate so far, or the rate the target needs, only when asked.
7. **Two sources, two numbers.** When sources disagree, give both, say which one the target was set against, and never average them.
8. **What is missing comes first.** For each engine, what you could not count comes before any suggestion: a quiet or stopped source, a measure nobody keeps, a source you can't open, a target with no date.
9. **Suggestions are marked as suggestions.** Start each with "Consider" and tie it to a line of the review. Nothing in the plan, the records or the targets changes without the person's yes.
10. **Describe the work by engine.** Say what the team did per engine. Records may name who did what; the review never compares people.
11. **A passed target stays passed.** After its date, say "the target of 50 by 31 Oct has passed" and give that period's final count if a review or record kept it. Never present an old target as current; propose the next period's target as an edit to the plan.

## The review

Use the same shape in the conversation and in a kept review. An engine with nothing new gets one line.

```markdown
# GTM review, [today's date]

Plan: [document and section]. Window: [first day] to [today]. Last review: [date, or none].

[One sentence: which engines are on target, which are short, what can't be counted.]

## [Engine, in the plan's words]

- Target: [number] by [date] ([where the plan says it]).
- Actual: [number], newest [date] ([source, and the rule if you counted]).
- Gap: [n] to go, [n] days left. | At or above the target. | The target date has passed.
- Done: [what the team did in the window] ([source]).
- Couldn't count: [what, and why] ([source]). | Nothing missing.

## Changes to consider

Suggestions only; nothing changes without your yes.

1. Consider [a change], because [the line above that prompts it].
2. [One more at most.]

## Sources read

- [Each document, table, export or page, with the date you read it.]
```

## An example (invented)

A studio's go-to-market plan for October, reviewed on 20 October.

```markdown
# GTM review, 20 Oct 2026

Plan: gtm/plan.md, "October". Window: 13 Oct to 20 Oct. Last review: 13 Oct.

Sign-ups are at their target; outreach is 34 short and content 22 short, with 11 days left; reach can't be counted after 9 Oct.

## Outreach to studios

- Target: 50 studios contacted by 31 Oct (gtm/plan.md, "Outreach").
- Actual: 16, newest 20 Oct (rows of gtm/outreach.csv where type is first message, dated 1 to 20 Oct).
- Gap: 34 to go, 11 days left.
- Done: 6 first messages and 2 replies this week (gtm/outreach.csv, rows 35 to 42).
- Couldn't count: calls held; no table records them.

## Sign-ups

- Target: 30 by 31 Oct (gtm/plan.md, "Sign-ups").
- Actual: 31, newest 20 Oct (the product's sign-ups dashboard, read 20 Oct).
- Gap: at or above the target.
- Done: 2 posts linking the sign-up page (gtm/posts.csv, rows 12 and 13).
- Couldn't count: nothing missing.

## Content

- Target: one post a day, so 31 by 31 Oct (gtm/plan.md, "Content").
- Actual: 9 posts in October, newest 18 Oct (rows of gtm/posts.csv dated 1 to 20 Oct).
- Gap: 22 to go, 11 days left.
- Done: 3 posts this week (gtm/posts.csv, rows 11 to 13).
- Couldn't count: reach. gtm/reach.csv has no rows dated after 9 Oct and expects a row every week.

## Changes to consider

Suggestions only; nothing changes without your yes.

1. Consider a fixed daily time for first messages, because outreach needs 34 in 11 days after 16 in 20 (Outreach, Gap).
2. Consider asking whoever keeps gtm/reach.csv to add the weeks since 9 Oct before the next review, because reach can't be counted (Content, Couldn't count).

## Sources read

- gtm/plan.md, read 20 Oct.
- gtm/outreach.csv and gtm/posts.csv, read 20 Oct.
- gtm/reach.csv, read 20 Oct (newest row 9 Oct).
- The product's sign-ups dashboard, read 20 Oct.
```
