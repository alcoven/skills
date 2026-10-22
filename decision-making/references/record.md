# Decision records, scripts and a worked example

Use the project's own decision format when it has one. Otherwise use these. Every fact in a record carries a source and a date.

## A two-way door: one paragraph

```markdown
# [Decision in a few words]

[Date]. We will [the decision] because [the reason, with source]. We also considered [other option] and [why not]. Decided by [name]. We look again on [date], or sooner if [condition].
```

## A one-way door: the full record

```markdown
# [Decision in a few words]

- Status: proposed | accepted | superseded by [link]
- Decided by: [one name], [date]
- Input from: [names]
- Agreed by: [names, with dates, once they agree]
- Door: one-way
- How sure: [a number, e.g. about 65%]
- Revisit: [a condition: a state and a date]; checked by [name]

## Decision
We will [the decision, one sentence].

## Why, and why now
[The situation and the forces at play. What waiting would cost.]

## What is already on record
- [earlier decisions or agreed lines this touches, with addresses]

## Criteria (set before the options)
1. [must-have], shown by [evidence]
2. [important], shown by [evidence]

## Options
| Option | [criterion 1] | [criterion 2] | [criterion 3] | Outcome |
|---|---|---|---|---|
| A ... | | | | chosen |
| B ... | | | | rejected: [why] |
| C: wait | | | | rejected: [why] |

## Evidence
- Fact: [what], [source], [date]
- View: [whose], [what], [how sure]
- Assumption: [what we take as true], [what would show it wrong]
- Base rate: [how similar cases went, with source], or "no record of similar cases"

## Pre-mortem: main risks
- [risk] → [change to the plan, or tripwire: signal, date, who watches]

## Dissent
- [name, only if they agree to be named]: [their view, in their words]

## Consequences
- What changes: ...
- What we give up: ...
```

## An options table, criteria first

Write the criteria column headings before filling any row. Rate each option on each criterion from the evidence, with a source in the cell, never from a feeling. A criterion no option meets is a sign the options are too narrow: widen them before deciding.

## Asking for independent views

Send each contributor the same question and the same facts, separately, before any meeting:

> Before we meet on [date]: which option would you choose, why, and how sure are you, as a percentage? Please write it before reading anyone else's answer.

Collect the answers. Show them side by side at the start of the meeting, with no names if people prefer. Spend the meeting on where they differ.

## A pre-mortem script

1. **Brief** the plan in five lines.
2. **Set the scene:** "It is [a date a year from now]. This decision failed badly. Take a few minutes, alone, and write every reason it failed."
3. **Share in turn:** each person reads one reason, round the table, until all are out. The decider writes them down. No debate yet.
4. **Group and pick:** the reasons most likely and most damaging.
5. **Act on each:** change the plan, or set a tripwire (a signal, a date, and who watches it).
6. **Record** the main risks and tripwires in the decision record.

For a two-way door, a two-minute version works: "If this goes wrong, what is the most likely reason?"

## Looking at it again

```markdown
# Review of [decision], [date]

- What we knew then: ...
- What we could have learned at a reasonable cost: ...
- How we decided: roles, options, evidence, pre-mortem
- What happened: ...
- What was luck, and what was the decision: ...
- Keep doing / change next time: ...
- Next: keep the decision | change it (a new record that supersedes this one)
```

## A worked example (invented)

Crumb is an app bakeries use to take orders. Ines is the founder; Tom builds the app; Ada handles sales and holds the budget; Noor looks after the bakeries once they sign up.

### A two-way door

Noor asks: "Should the weekly summary email go out on Monday instead of Friday?" The email's send day can be changed in a minute and affects one email. The AI sizes it as a two-way door, checks the record (nothing decided), and writes:

```markdown
# Weekly summary on Mondays

21 Oct 2026. We will send the weekly summary on Monday mornings because three bakeries said they plan the week's baking on Monday (support/notes.md, 14 to 18 Oct). We also considered Sunday evening; bakeries told us they don't read email then. Decided by Noor. We look again on 30 Nov, or sooner if fewer bakeries open it.
```

### A one-way door

Ines asks: "Help us decide which payment provider we launch card payments with."

**1. The record.** `related` and `agreed` find a decision of 10 June: invoices only during the pilot (decisions/2026-06-10-invoices-for-pilot.md), with a revisit condition, "when more than half of bakeries ask for card payments". Noor's notes show that condition met in October (support/requests.md, 3 Oct). The AI says so: the old decision named its own trigger, so reopening it is in order.

**2. Framing.** "Which provider do we launch card payments with, by 15 Nov?" Decider: Ines. Input: Tom, Noor. Must agree: Tom (he owns the payments code) and Ada (budget). To know: the whole team.

**3. Size.** One-way door: moving bakeries' saved cards to another provider later is slow and needs each bakery to act.

**4. Criteria first.** (1) Pays bakeries out within two working days, a must-have from Noor's notes. (2) Fees at Crumb's volume. (3) Effort for Tom to build. (4) How hard it is to leave later.

**5. Options.** Provider A, Provider B, and C: keep invoices until January and decide then. The vanishing options test adds D: let bakeries use their own card terminals and record payments in Crumb.

**6. Independent views.** Each contributor answered before the meeting: Ines A (60%), Ada A (70%), Noor A (55%), Tom C (65%), because his team is busy with the October release.

**7. Pre-mortem.** Top reasons it failed: payouts delayed and bakeries left; the build slipped past Christmas orders. Tripwires: Noor tracks payout complaints weekly; Tom flags by 1 Dec if the build is at risk.

**8. Decision and record.** Ines chooses A, about 65% sure. Tom disagrees, agrees to be named, and commits. Revisit: "five or more payout complaints by 31 Jan, or the build not live by 10 Dec; Noor and Tom check." The old June record is marked superseded and linked.

**9. On record.** The AI shows Ines the record, then writes it to decisions/2026-10-22-card-payments.md. `hand_out` asks Tom and Ada to agree, with Ines's line "Please agree or tell me what's missing by Friday"; the team gets it to read. A task for Ines is due 31 Jan to look at it again.
