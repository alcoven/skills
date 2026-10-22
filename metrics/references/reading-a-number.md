# Reading a number honestly

Run these checks before saying what a number or a change means. They go roughly from cheapest to dearest, and the first three catch most mistakes. A small reading (one number, a quick question) gets the first five in a minute; a reading the team will act on gets all of them. Every example below is invented.

## The checklist

### 1. Is the number real?

Twyman's law, as Kohavi, Tang and Xu use it: any figure that looks interesting or different is usually wrong. Before explaining a surprise, look for the mistake: a change to the tracking code, a new or broken filter, bots or a monitoring service, events counted twice, a time zone change, a backfill of old data, a source that went quiet.

*Example.* Crumb's visits to its pricing page doubled on a Tuesday. One address had opened the page every minute since Monday night: an uptime checker someone had set up. Without it, visits were flat.

### 2. Is the definition the same on both sides?

A changed definition, a new exclusion, or a different source makes two numbers that can't be compared.

*Example.* Active teams rose by a third in October. On 1 October, "active" had changed from "changed something on two of the last seven days" to "opened the app". Under the old rule, active teams were level.

### 3. Like with like?

Same length, same days of the week, same season. Weekdays differ, month ends differ, holidays, school terms and paydays move many numbers.

*Example.* Support tickets fell by a quarter week on week, and the team was ready to credit the new help page. The week had a public holiday on Monday. Against the same week last year, tickets were about level.

### 4. What is the denominator?

A rate can move because its base moved. Put the counts beside every percentage, and name the group in the denominator.

*Example.* Harbor Studio's on-time share rose from 60% in July to 80% in August. July was 12 of 20 deliveries; August was 4 of 5, with most clients on holiday. The rise rests on a quarter of the usual work and one delivery's difference.

### 5. Are there enough to tell?

Small numbers swing on their own. Give the counts, and when a handful of cases decides the reading, say "too few to tell". If someone on the team can put a range of plausible values on it, ask them; never fake a precision the counts can't carry.

*Example.* Trial to paid went from 3 of 10 to 5 of 12. Written as 30% to 42% it looks like a jump; written as counts it is two more people.

### 6. Old and new customers mixed?

A total over all customers mixes people at different ages. Read by cohort: the customers who started in the same week or month, each followed over time. A large new cohort can drag a total down while every cohort behaves as before (Sequoia's data science team notes that one cohort much larger than others can dominate the total).

*Example.* Thirty-day retention fell in November. A campaign had brought in a cohort three times the usual size, and campaign sign-ups leave faster. Every earlier cohort's curve was unchanged, and the campaign cohort's curve was flattening, lower.

### 7. Did the mix change? (Simpson's paradox)

A total can move one way while every group inside it moves the other, when the share of each group changes. Before reading a total, split it by the field most likely to have shifted: source, plan, country, device, customer type. The classic real case is the 1973 graduate admissions at Berkeley, where the overall rate seemed to favour men while most departments, read one by one, did not (Bickel, Hammel and O'Connell, 1975).

*Example.* Crumb's average order value fell in October. It rose for cafés and rose for home bakers; home bakers, whose orders are smaller, went from a quarter of orders to a half.

### 8. Is it regression to the mean?

An extreme period is usually followed by a more ordinary one, whatever was done in between. Daniel Kahneman (*Thinking, Fast and Slow*, 2011) tells of flight instructors who believed praise made pilots worse and criticism made them better; regression explained the pattern on its own.

*Example.* Late deliveries hit their worst week of the quarter, and the studio brought in a checklist. The next week was better. Weeks after a bad week were usually better before the checklist too; it needs a few more weeks, or a comparison, before it gets credit.

### 9. Who is missing? (survivorship)

Data about people who stayed says nothing about those who left. Abraham Wald's wartime work on aircraft armour is the classic case: the holes in returning planes showed where a plane could be hit and still fly home (Mangel and Samaniego, 1984).

*Example.* "Customers who use the reports feature stay longer." Only customers who stayed long enough ever found the reports page. Compare customers of the same age.

### 10. What else happened?

Lay out a timeline of the period: releases, campaigns, newsletters, price changes, outages, holidays, a competitor's news, changes to tracking. In Alcoven, `- Mark: releases of app/` on a widget and the notes left with `day:` put most of this on the chart.

*Example.* Sign-ups rose 40% in launch week. The newsletter went out the same morning. Split by source, the newsletter brought most of the rise; sign-ups from the new page were level with the week before.

### 11. Is it a cause, or does it line up in time?

Two things moving together, or one following the other, leave the cause open; a test can settle it. For a split test's design, size and stopping rules, use the lean-experiments skill if the project has it. When a test isn't possible, say what else could explain the change and how likely each is.

### 12. What can't these numbers show?

Write it down every time: the question the data can't answer, the group it doesn't cover, the period it doesn't reach. A reading without this line claims more than it knows.

## The written reading

Use this shape for any reading the team will act on, in the conversation and in a kept document.

```markdown
# Reading: [metric], [today's date]

- What moved: [metric] from [n of n] ([period]) to [n of n] ([period]). Source: [source and rule], newest [date].
- Checked: [the checks run and what each found, in a few words].
- Most likely meaning: [one or two sentences, with how sure: likely, possible, can't tell].
- Can't show: [what these numbers can't tell].
- Would settle it: [the check or test, what it costs, how long it takes].
- Decision rule on record: [the rule set beforehand, and what it says now] | none was set.
```

*Example (invented).*

```markdown
# Reading: sign-ups, 22 Oct 2026

- What moved: sign-ups from 212 (week of 6 Oct) to 297 (week of 13 Oct). Source: product.source.md, sign-ups by week, newest 19 Oct.
- Checked: tracking unchanged; no bot pattern; same weekdays; split by source, the newsletter brought 71 of the 85 extra.
- Most likely meaning: the newsletter caused most of the rise; the new page's effect can't be told apart yet.
- Can't show: whether newsletter sign-ups activate or stay.
- Would settle it: activation of the newsletter cohort at day 14 (ready 27 Oct); a split test of the new page against the old (two to three weeks).
- Decision rule on record: "keep the new page if sign-ups from search rise by a fifth within four weeks", read on 10 Nov.
```

## Sources

All read on 2026-10-22.

- Ron Kohavi, Diane Tang and Ya Xu, *Trustworthy Online Controlled Experiments*, Cambridge University Press, 2020 (Twyman's law; trust checks on data).
- Sequoia Capital data science team, "Retention", around 2018. articles.sequoiacap.com/retention
- P. J. Bickel, E. A. Hammel and J. W. O'Connell, "Sex Bias in Graduate Admissions: Data from Berkeley", *Science*, 1975.
- Daniel Kahneman, *Thinking, Fast and Slow*, Farrar, Straus and Giroux, 2011.
- Marc Mangel and Francisco Samaniego, "Abraham Wald's Work on Aircraft Survivability", *Journal of the American Statistical Association*, 1984.
- Alistair Croll and Benjamin Yoskovitz, *Lean Analytics*, O'Reilly, 2013.
