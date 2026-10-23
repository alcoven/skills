# Templates and a worked example

Fill each template from the record, with a source for every fact. Leave out a line that has nothing in it. Templates marked **private** stay with the manager unless they choose a place for them and who sees it.

## 1:1 prep (private)

```markdown
# 1:1 with [name], [date]

Last 1:1: [date]. Their agenda: [their topics, if shared].

## I owe them
- [what they are waiting on from me, with source]

## Thanks
- [one specific thing they did, what it made possible] ([source])

## Ask
- [two or three open questions, from what the record shows]

## Load
- [open and past-due tasks, unanswered notes asking them] ([source]). Ask, don't assume.

## One thing to raise (if any)
- [feedback in situation, behaviour, impact form]

## From last time
- [what was agreed, who, done or not]

## After (fill in at the end)
- Decided: ...
- They will: ... by ...
- I will: ... by ...
```

## Feedback

```markdown
Situation: [when and where]
Behaviour: [what they said or did, as anyone present would describe it]
Impact: [the effect on the work, a teammate, a customer]
Their view: [the question you will ask, e.g. "How did it look from your side?"]
Request or question: [one specific ask, or an open question]
```

Check before it goes: one behaviour, no labels, no guess at motive, within days, would read fairly if they saw your notes. Praise uses the same shape.

## Delegation brief

```markdown
# [The work], for [name]

- Outcome: [what done looks like, and why it matters]
- By: [date]
- Limits: [budget, what must not change, who must be consulted]
- Authority: [plain words, e.g. "You decide; tell me after" (level 6 of 7)]
- Context: [documents, people, past attempts]
- Check-ins: [when, and what to bring], set by their experience with this work
- Review: [who reviews the result before it counts as done]
- Agents: [if an AI agent does part of it: who answers for its work, who reviews it]
```

## Expectations and goals

```markdown
# [Name]'s role and goals, [period]

## What the role owns
- [areas, and the decisions they make alone]

## What good looks like
- [one or two concrete examples]

## Goals for [period]
1. [an outcome] measured by [measure], by [date]. Tied to [team goal].
2. ...

## How we work together
- 1:1 [how often]; updates [where, how often]; I step in when [condition].

Agreed by [both names] on [date]. Look again on [date].
```

## Team meeting

```markdown
# Team meeting, [date]

Purpose: [why we meet]. Updates: read [where] before the meeting.

| Item | Owner | Decision needed? | Minutes |
|---|---|---|---|
| ... | ... | yes / no | ... |

## Decisions
- [decision], owner [name], by [date]

## Blockers
- [blocker], who helps, by [date]
```

## Retro

```markdown
# Retro, [period], [date]

Frame: everyone did the best they could with what they knew, their skills, the time and the tools.

## Last retro's actions
- [action]: done / not done, and why

## What happened
- [facts and events, from the record and from people]

## Why
- [causes the team agrees on]

## Changes (one to three)
- [change], owner [name], check on [date]
```

## Team health read (private)

```markdown
# Team health, [date] (for [manager] only)

| Signal | Source | Question for a 1:1 |
|---|---|---|
| ... | ... | ... |

What the record can't show: calls, coaching, thinking time, work done elsewhere.
```

## Improvement plan (informal stage)

```markdown
# Working together on [area], [name], [date]

- The standard: [what is expected, and where it was set]
- What happened: [situation, behaviour, impact, with dates]
- Their view: [in their words]
- What good looks like by [date]: [specific, observable]
- Support: [training, pairing, time, a lighter load]
- Check-ins: [dates]
- Next step if it doesn't change: the organisation's policy, with HR.

Shared with [name] on [date].
```

## A worked example (invented)

Harbor Studio is a small design studio, led by its manager. The team: a new designer, four months into the job; a senior designer; and a developer. The senior designer works with a research agent that summarises client interviews.

The manager asks: "Prep my 1:1 with the new designer tomorrow, and I need to give them feedback about Tuesday's client call."

**What the record shows** (read 22 Oct): the new designer finished the Crumb onboarding screens (tasks/crumb-onboarding.md, done 17 Oct). They have two open tasks, one past due since 15 Oct (tasks/crumb-icons.md). A note from the senior designer asking them about icon sizes has been open since 14 Oct (design/crumb/icons.md). The new designer asked the manager on 16 Oct to approve the type scale; the manager hasn't answered (design/crumb/type.md, note to the manager).

**The prep:**

```markdown
# 1:1 with the new designer, 23 Oct

## I owe them
- An answer on the type scale they asked about on 16 Oct (design/crumb/type.md).

## Thanks
- The Crumb onboarding screens: the bakery owners in the test finished set-up without help (tasks/crumb-onboarding.md).

## Ask
- What's taking longest on the icons?
- What did you make of Tuesday's call?

## Load
- Icons past due since 15 Oct; the senior designer's note on sizes open since 14 Oct. Ask if they're stuck or swamped.

## One thing to raise
- Situation: Tuesday's call with Crumb, when the client asked about the launch date.
- Behaviour: you said "end of the month" before checking with the developer.
- Impact: the developer's estimate is mid-November, so we now need to correct a date the client has written down.
- Their view: "How did that moment feel from your side?"
- Request: when a client asks for a date, say you'll confirm within a day, then check with whoever builds it.
```

**Speaking up.** The manager's draft said "you were careless on the call". The AI offered once: "Want me to put it as what they said and what it caused? They can act on that." The manager agreed. The AI also pointed out that the new designer has little experience of client calls, so a short practice before the next one would help more than the feedback alone (task-relevant maturity).

**Delegation.** The manager then hands the icon set's review to the senior designer: outcome "an icon set the new designer can finish this week"; authority "you decide sizes and style; tell me after" (level 6); check-in Friday. The senior designer's research agent will check the icons against the interview notes: the senior designer answers for its summary and reviews it before the new designer uses it.

**Team health read.** The record shows the developer holding most of the team's past-due tasks and the only person changing the build folder for a month. The read gives the manager one question for the developer's 1:1: "What could you hand over or drop?" Nothing about it goes in a team document.
