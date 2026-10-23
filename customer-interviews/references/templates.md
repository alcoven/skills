# Templates and a worked example

Three documents: the guide (before), the note (after each interview), the synthesis (after a round). Each has its title as the first heading. The example uses an invented company and invented people.

## The interview guide

```markdown
# Interview guide: [topic], [date]

- Decision: [what the team will decide with this, and by when].
- We must learn: 1. [...] 2. [...] 3. [...] (three at most).
- What would change the plan: [the answer that would make us stop, change or go].
- Already known: [finding, with its source and date]; [...]. Not asking again.
- Who: [segment, why them, how many this round]; [...].
- Interviewers: [who leads, who takes notes].

## Before the call
- Consent: who we are, why we ask, what we record, who sees it, how long we keep it, that they can stop at any time. Ask before recording.

## Opening (2 minutes)
- Thank them. "There are no right answers; we want to hear how it really goes for you."
- "Tell me a bit about your work. What does a normal week look like?"

## The story (most of the time)
- "Tell me about the last time you [did the thing]."
- Dig: When was it? What happened just before? Who else was involved? What did you use? Where did it go wrong? How did it end? What did it cost you?
- What have you tried for this? What happened with it? What do you spend on it now?

## The switch (only for buying, switching or leaving)
- First thought: "When did you first think you needed something different?"
- Looking: "What did you look at? What made you start looking for real?"
- Deciding: "What made you decide then? What almost stopped you?"
- Forces: push (what went wrong before), pull (what you hoped for), anxiety (what worried you), habit (what was hard to leave).

## Closing (5 minutes)
- "What should I have asked that I didn't?"
- "Who else should I talk to?"
- Commitment, when there is something real: [what we ask for: a second call, their real data, an introduction, a pre-order].

## Do not ask
- "Would you use...?", "How much would you pay...?", "Do you like...?", "What features do you want?"
```

## The interview note

Write it the same day. One note per interview.

```markdown
# Interview [code]: [segment], [date]

- Interviewed by: [lead], notes by [note-taker]. Recorded: yes / no.
- Consent: given for [notes / recording], kept until [date].
- Quick facts: [role, size of their business, what they use today, how long].

## The story
1. [What happened, in order, with dates and amounts where they gave them.]

## Did
- [Facts: what they did, spent, built, switched.]

## Said
- [Opinions, predictions, wishes, feature ideas, marked as such.]

## Quotes
- "[word for word]" ([code], [date], [minute or line])

## We think
- [Our interpretation, kept apart from what they said.]

## Commitment
- Asked for: [...]. Given: [yes / no / what].

## Flags
- [Leading questions, pitches or hypotheticals in this interview, from the review.]
```

## The synthesis

```markdown
# What we learned: [topic], [date]

- Decision: [...]. Questions: [the three].
- Interviews: [n], [dates], by segment: [segment: n]; [...]. Planned but not held: [...].
- Notes: [list, each with its address].

## Findings
### F1. [The finding, in the customers' words]
- Who: [n of N], by segment.
- Evidence: [Did / Said], and what kind (money, workaround, story, commitment).
- Quotes: "[...]" ([note], [date]).
- Against: [contradictions, outliers].
- Confidence: [low / medium / high], because [...].

## Answers to our questions
1. [Question]: [what the evidence supports], [what it does not], [confidence].

## What this does not show
- [Sizes, prices, future behaviour, segments we did not reach.]

## Next step
- [More interviews with whom / a survey to size F[n] / a test with its pass line / the decision, for whom, by when.]
```

## Worked example (invented)

Crumb makes an ordering app for small bakeries. Its founder wants to build automatic order reminders and asks the AI: "Write me some questions to check bakeries want reminders."

**What the AI does first.** It asks for the decision ("build reminders this quarter, yes or no, by 1 November"), reads the project's support notes, and finds two tickets about missed orders. It rewrites the research questions: how do orders get missed today, what does a missed order cost, and what have bakeries tried. It says once: "Asking whether they want reminders will get polite yeses. Asking about the last missed order will tell you whether it is worth building." The founder agrees.

**Who.** Four owners using Crumb, two owners who cancelled in their second month, one owner who chose a rival app. Round one: seven.

**From the guide.** "Tell me about the last order that went wrong. When was it?" "What did you do about it?" "What do you use to keep track of orders now?" Closing commitment for current customers: "Could we look at your order list together next week?"

**A review flag.** In interview P2, the co-founder asked: "Wouldn't reminders have saved you there?" The AI flags it as leading and hypothetical, notes that P2's "yes, definitely" is fluff, and suggests: "What would have needed to happen for that order not to slip?"

**From the synthesis.**

```markdown
### F1. Missed orders come from phone and chat orders that never reach the order list
- Who: 5 of 7 (3 of 4 owners on Crumb, 2 of 2 who cancelled, 0 of 1 who chose a rival).
- Evidence: Did. Five described a specific missed order in the last month; P1 and P4 showed the notebook they copy from.
- Quotes: "The ones that go wrong are always the ones that come by text." (P4, 2026-10-15)
- Against: P6, on Crumb, takes every order through the app and has missed none this year.
- Confidence: medium. Consistent among owners who take orders by message; only one person who chose a rival.

## Answers to our questions
1. How do orders get missed? Mostly before they reach Crumb, so a reminder on orders already in Crumb would not have caught 4 of the 5 cases described.

## What this does not show
- How many bakeries take orders by chat; whether owners would pay for a fix.

## Next step
- Consider three interviews with owners who take most orders by chat, and a look at whether getting chat orders into Crumb is the better thing to build. The founder decides by 1 November.
```

The interviews changed the question: the problem is real, and reminders, as first imagined, would not fix most of it.
