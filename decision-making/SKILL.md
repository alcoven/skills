---
name: decision-making
description: Helps a team make a decision well, on evidence, and put it on record. Use when someone asks "should we do X or Y", "help us decide", "who decides this", "we keep arguing about this", "write up the decision", "is this reversible", or faces a choice that is costly to undo (a price, a hire, a platform, a vendor, a market, a pivot). Checks what is already decided, sizes the decision (can it be undone, what being wrong costs, who it affects) and scales the process, from a short record for a two-way door to criteria set first, at least three options, evidence, independent views and a pre-mortem for a one-way door. Names one decider, writes the decision record (what, why, options rejected, who decided, when, how sure, what would make us revisit) and gets it agreed. Keeps facts apart from opinions, starts from how similar cases went, asks what would change the team's mind, and judges past decisions by what was known then.
license: MIT
metadata:
  source: https://alcoven.co/skills/decision-making
  version: "1"
---

# Decision making: size it, decide it, put it on record

A decision is good when it was made well with what could be known at the time. A good outcome can follow a bad decision, and a bad outcome a good one; judging decisions by how they turned out is what Annie Duke calls "resulting". Most decisions can be undone and should be quick; a few are hard to undo and deserve care (Jeff Bezos's two-way and one-way doors). The person asking is usually stuck between options, short of time, or tired of a choice the team keeps arguing about, and fears both a wrong call they can't take back and a slow one that costs the moment. So size the decision first, spend effort in proportion, name one decider, and write it down so nobody argues it again without new evidence.

## What you need

- **The question**, in the person's words, and the date it must be decided by.
- **What is already on record:** decisions, agreed documents, the brief and strategy, earlier attempts at the same thing.
- **The people:** who decides, who knows the most, who must agree, who it affects.
- **The evidence:** numbers, research, customers' words, costs, each with its date.

If you can only see the conversation, ask for the question, the deadline and who decides, and list what you could not check.

## 1. Check the record first

- Look for a decision on record on this subject and for what people agreed to. Read why it was decided and on what evidence.
- If it is decided, say so and cite it: who, when, why. Reopening it is the decider's call, and only on new evidence or a changed situation, named in a sentence.

## 2. Frame the question

- **One sentence, as a choice:** "Which payment provider do we launch with, by 15 November?"
- **The deadline**, and what waiting costs.
- **The roles** (Andy Grove's pre-decision questions; DACI or RAPID if the team uses one): one **decider**; who gives **input**; who must **agree** (only those who must, such as whoever holds the budget or owns what it changes); who needs to **know**.
- If nobody is named as the decider, ask the person who it is. Never assume it is the most senior person or the loudest.

## 3. Size it

| | Two-way door | One-way door |
|---|---|---|
| **Undo** | in days or weeks, at small cost | slow, costly or impossible: a signed contract, a price for existing customers, a hire or a layoff, a public promise, deleted data, a foundation much else rests on |
| **Cost of being wrong** | small and contained | large, or carried by customers, money or people's jobs |
| **Who it affects** | a person or one team | customers, the whole team, outside parties |
| **The process** | one person or a small group decides quickly; a one-paragraph record with a date to look again | the full method (step 4); a full record; agreement from those who must agree |

Most decisions are two-way doors. Bezos warns that organisations slow down when they treat them like one-way doors, and suggests deciding most of them with about 70% of the information you wish you had. In between, use steps 4.1, 4.2 and 4.6. Before the full method, ask whether a one-way door can be turned into a two-way door: a pilot, a shorter contract, a first step that can be undone.

## 4. The full method, for a one-way door

1. **Set the criteria before looking at options.** What matters, in order; the must-haves; for each, the evidence that would show it is met.
2. **Widen the options to at least three.** Include waiting and doing nothing. Ask: if none of these were possible, what would we do? Look for "both, in order" and for a small test first (Chip and Dan Heath, *Decisive*).
3. **Gather the evidence.** Facts with a source and a date; opinions marked as someone's view; assumptions listed. Start from how comparable cases went, the outside view, then adjust for what is different here.
4. **Collect views independently first.** Each contributor writes their choice, the reason and how sure they are, before any discussion. The decider and the most senior person speak last. Discussion goes to where people disagree (Kahneman, Sibony and Sunstein, *Noise*).
5. **Run a pre-mortem.** Imagine it is a year later and the decision failed. Each person writes the reasons alone; share them in turn; change the plan, or set a tripwire that will tell you early (Gary Klein).
6. **Decide.** The decider decides by the deadline. People who disagree say so, and their view goes in the record if they want it there; then everyone commits to the decision (Bezos: disagree and commit). A real disagreement about direction goes to whoever sits above both sides, early.

## 5. Write the record

Every record has: the decision in one sentence ("We will..."); why, and why now; the options rejected and why; who decided, who gave input, who agreed, and the date; how sure the decider is; what would make us revisit (a condition and a date) and who checks. A one-way door adds the criteria, the evidence with sources, the pre-mortem's main risks, any dissent, and the consequences: what changes and what we give up. A two-way door fits in one paragraph. Templates in [references/record.md](references/record.md). When a decision changes, keep the old record, mark it superseded and link the new one (Michael Nygard's architecture decision records).

## 6. Put it on record and get it agreed

Show the person the text before writing it. Then ask the people who must agree to agree to that version, and give it to those who need to know. Until both happen, it is a proposal.

## 7. Look at it again

At the revisit date or when the condition is met: what was known then, whether the process was sound, what happened, and how much was luck. Judge the decision apart from the outcome. If the condition fired, change course and write a new record that supersedes the old one.

## Deciding with evidence

- Set criteria and pass lines before seeing options and data.
- Every fact carries a source and a date; every opinion a name.
- Start from the base rate of similar cases, then adjust (Lovallo and Kahneman's outside view).
- Say how sure you are as a number, and ask others to: "likely" means different things to different people (Duke).
- Ask "what would change our mind?" and write the answer as the revisit condition.
- With thin data, decide a two-way door anyway. For a one-way door, buy information cheaply first (a test, a pilot, a call) or make it reversible. For choosing measures and reading numbers, use the metrics skill; for a test, lean-experiments, if the project has them.
- A missing number is said to be missing, never estimated from memory.

## Common mistakes

Name one when you see it, once, with the evidence and the fix. Why each hurts and its source are in [references/methods.md](references/methods.md#common-mistakes-in-depth).

1. **No clear decider.** Everyone waits for someone. Instead: one named person.
2. **Waiting for everyone to agree.** The decision waits for the last holdout. Instead: input from all, a decider, disagree and commit.
3. **The loudest voice or the highest-paid person's opinion decides.** Others stop offering what they know. Instead: independent views first, the senior voice last.
4. **Reopening a settled decision without new evidence.** The team re-argues it each month. Instead: point to the record; reopen on named new evidence.
5. **Nobody wrote it down.** Newcomers accept it blindly or reverse it blindly. Instead: a short record, where the team looks.
6. **Judging the decision by its outcome.** Teams learn from luck. Instead: review what was known and how it was decided.
7. **A two-way door treated as a one-way door.** Slow, cautious, no experiments. Instead: decide fast and set a date to look again.
8. **A one-way door treated as a two-way door.** A hasty call that can't be undone. Instead: the full method, or make it reversible first.
9. **Only two options.** "Whether or not" hides better choices. Instead: at least three, including waiting.
10. **Choosing first, then finding reasons.** The criteria are bent to fit the favourite. Instead: criteria before options.
11. **Anchoring the room.** The boss, or an AI, gives a view first and everyone moves toward it. Instead: collect views before showing any recommendation, yours included.
12. **Waiting for complete data.** The moment passes. Instead: about 70% for a two-way door; cheap tests for a one-way door.

## Speaking up

- **Once, with the evidence and the cheapest step.** "This was decided on 3 March (decisions/2026-03-03-pricing.md) on churn data from February. Is there new evidence? If not, want me to list what would justify reopening it?"
- **Credit what is already good** before the gap.
- **Match their pace.** On a deadline, one line. Never repeat a point they have heard and decided on.
- Then help with the decision they choose, and note the risk once in the record.

## What you never do

- Make the decision. Recommend when asked; the decider decides.
- Present your recommendation as the team's view, or put words in anyone's mouth.
- Reopen or edit a decision on record on your own.
- Invent probabilities, base rates, costs or evidence.
- Name someone's dissent in a record without their agreement.
- Ask people to agree to anything without the person's yes.

## In Alcoven

Pass the project's slug and cite by § address.

1. `related` with the question in a sentence or two, and `agreed` with `about:` the subject: what is already decided or agreed. A choice settled on a call may live only in a document, so `search` too.
2. `why` on the passage that settled it: who decided, when, and what they read. If the new step goes against an agreed line, stop that step, tell the person, and `add_note` on that section `to` whoever put it there.
3. For a one-way door, `add_note` with `to` each contributor on the options section, asking for their choice, reason and how sure they are. Everyone who sees the document sees its notes, so ask each person to write theirs before reading the others', and show no recommendation until they have.
4. Show the person the record, check the folder with `list` (the project's decisions folder, else `decisions/YYYY-MM-DD-<slug>.md`), then `add_document` with `asked` in their words and `read`.
5. `hand_out` with `ask: "agree"` to those who must agree, and the person's own `line`; `ask: "read"` for those who need to know. Then `task` for the decider, due on the revisit date, standing on the record.

## Elsewhere

Look for a decisions folder (`decisions/`, `docs/adr/`, `wiki/decisions/`) and follow its numbering and shape. Find earlier decisions with `grep` and `git log -S "<term>"`. Get agreement in writing: a reviewed pull request, or replies to the record.

## Files

- [references/methods.md](references/methods.md): the methods in more depth, the mistakes in depth, and the sources.
- [references/record.md](references/record.md): record templates, a pre-mortem script, an options table, and a worked example.
