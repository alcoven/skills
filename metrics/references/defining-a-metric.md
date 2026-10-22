# Defining a metric

A metric without a written definition is a different number for everyone who pulls it. Write one for every metric the team targets or shows on its home, in one document (`metrics/definitions.md` unless the project keeps them elsewhere), and keep it current: a definition that changes gets a dated line, never a quiet edit.

## The template

```markdown
## [Metric name: the act it counts]

- Question it answers: [one line, in the team's words]
- Kind: [north star | input | guardrail | health]
- Counts: [exactly what counts]
- Doesn't count: [what is left out, and why: test accounts, the team's own use, refunds, bots]
- Formula: [numerator] ÷ [denominator], or a count of [what] per [period]
- Window: [day | week, Monday to Sunday | calendar month | rolling 28 days], in [time zone]
- Unit: [people | teams | orders | % | currency]
- Source: [the system, table or .source.md], with the exact rule or query
- Updates: [how often; how late the newest day can be]
- Keeper: [member id], who answers questions about it and fixes it
- Target: [n] by [date], from [n] on [date] | none yet
- Decision rule: If [reading] by [date], we [action]; if [reading], we [action].
- Pairs with: [the guardrail it is watched beside, or the north star it feeds]
- Known gaps: [what it misses]
- Defined: [date], by [member id]
- Changes: [date]: [what changed, and where the chart breaks]
```

## How to fill each field

| Field | The rule | Why |
|---|---|---|
| Name | Name the act: "cafés with a standing order", over "engagement". | People read the name, rarely the definition. |
| Question | One question a person would ask out loud. | If no one would ask it, the metric has no use. |
| Counts | Name the action that means value. "Active" is an action (an order placed, a document shared), never a login alone. | Logins rise with notifications and say little about value. |
| Doesn't count | List every exclusion: staff, test accounts, bots, refunds, internal projects. | Exclusions are where two people's numbers part ways. |
| Formula | Name both numerator and denominator. For a rate, say which group is the denominator: people who started in the window, or everyone active. | Most disagreements about a rate are about its denominator. |
| Window | Say the week's first day and the time zone; say whether it is a calendar or a rolling period. | A Sunday-to-Saturday week and a Monday-to-Sunday week give different answers. |
| Source | One source per metric. When two sources disagree, give both and say which the target was set against. | Naming the table and the rule lets anyone pull the same number; "the dashboard" leaves them guessing. |
| Updates | How often new data arrives and how late it can be. | A source that is a week behind reads as a drop. |
| Keeper | One person. | When everyone keeps it, nobody fixes it. |
| Target | A number and a date, with the baseline and its date. | A target without a date can't be missed, so it can't steer. |
| Decision rule | Written before the data arrives. | Afterwards, the line drifts toward the result. |
| Changes | Never overwrite a definition: add a dated line, and mark the break on the chart. | Comparing across a silent change compares two different numbers. |

## The metrics document

One page that says what the team watches and why. It sits above the definitions.

```markdown
# Metrics, [team or project], [date]

Outcome: [what should change, for whom, by when].

| Metric | Kind | Now (date) | Target (date) | Keeper |
|---|---|---|---|---|
| [name] | North star | [n] ([date]) | [n] ([date]) | [member id] |
| [name] | Input | | | |
| [name] | Input | | | |
| [name] | Guardrail | | | |

The tree: [north star] = [component] × [component]; [influences believed to move each].

Left out, and why: [metric]: [reason, such as "no one would act on it"].

Next review: [date].
```

## A filled example (invented)

Harbor Studio is a design studio of nine people. Its outcome for the quarter: "Clients get work on the day we promised, without the team working weekends, by 31 March 2027."

| Metric | Kind | Now | Target | Keeper |
|---|---|---|---|---|
| Deliveries on the promised day, per month | North star | 11 of 19 (September 2026) | 17 of 20 or better (March 2027) | m-4f2k9a |
| Projects with a signed brief before work starts | Input | 5 of 9 (Q3) | every project (Q1) | m-7h3c2d |
| Client feedback rounds answered within 2 working days | Input | not counted yet | set once counted for a month | m-7h3c2d |
| Tasks estimated before they start | Input | not counted yet | set once counted for a month | m-4f2k9a |
| Weekend hours logged | Guardrail | 26 hours (September) | fewer each month | m-9k1p5x |

Left out: "projects won", since the outcome is about delivery and sales has its own review.

The north star's definition:

```markdown
## Deliveries on the promised day

- Question it answers: Are clients getting work on the day we promised?
- Kind: north star
- Counts: a delivery sent to the client on or before the date promised in the project plan. A date moved with the client's written agreement counts against the new date.
- Doesn't count: internal reviews; work for the studio's own site. A date the studio moved alone counts against the old date.
- Formula: count of on-time deliveries per calendar month, shown beside the share: on-time ÷ all deliveries that month.
- Window: calendar month, in the studio's time zone.
- Unit: deliveries.
- Source: ops/deliveries.csv, one row per delivery (sent, project, client, promised, on_time); rule: rows where on_time is yes.
- Updates: a row on the day of each delivery; rows expected every week.
- Keeper: m-4f2k9a
- Target: 17 of 20 or better by 31 March 2027, from 11 of 19 in September 2026.
- Decision rule: If fewer than 7 in 10 deliveries are on time in January, we take no new projects in February.
- Pairs with: weekend hours logged.
- Known gaps: deliveries sent from personal email are missed unless logged by hand.
- Defined: 2026-10-01, by m-4f2k9a
- Changes: 2026-10-01: dates moved with the client's agreement now count against the new date; the chart breaks here.
```

In an Alcoven project, the table becomes a source with a `.source.md` beside it, and the north star becomes a widget:

```markdown
# Studio deliveries

- Service: File in the project
- File: ops/deliveries.csv
- Days: column sent
- Expect: every week
- Owner: m-4f2k9a

## Measures

- deliveries: rows
- on time: rows where on_time is yes
- client: by column client
```

```markdown
# Deliveries on the promised day

- Show: line
- Measure: on time, deliveries
- From: ops/deliveries.source.md
- By: month
- Since: this year
- On home: yes
- Owner: m-4f2k9a

Why it's here: our north star for the quarter; definition in metrics/definitions.md.
```
