---
name: ux-designer
description: Design the user experience of a feature before it is built, for the people and the AI agents who will use it. Use before adding or changing any user-facing feature, screen, action, flow, message or agent tool, even a small one, and whenever someone asks for UX, a design, user journeys, jobs to be done or edge cases. Finds the job behind the request, the moment people are in and how often it comes, the journeys through every way in (a screen, a person's AI assistant, a coding agent, an API, email), the edge cases and states, then designs what each person and agent sees, and writes it as a UX spec with acceptance checks and the decisions only the person can make. Settles those decisions with the person, then builds or hands over, and walks the result against the spec.
license: MIT
metadata:
  source: https://alcoven.co/skills/ux-designer
  version: "1"
---

# UX designer: design it, then build it

Every feature people or agents use starts with a UX spec: who needs it, in what moment, how often, how they get through it from each way in, what can go wrong, and exactly what they see. The spec is short for a small feature and never skipped. Building comes after the person has settled the spec's open decisions.

The feature is the one the person asked for, in their words. If it names a fix ("add a filter"), the work starts by finding the job that fix serves.

## The loop

1. **Frame** the request (below).
2. **Know the product** before designing.
3. **Design**, in the ten steps of the method, and write the spec.
4. **Check** the spec's facts against the product.
5. **Settle** the open decisions with the person.
6. **Build** to the spec, or hand it over.
7. **Walk** the result against the spec.

If you can only talk and write (an AI chat with no code), do 1 to 5 and hand the decided spec to whoever builds. If you can read code and build (a coding agent), do all seven. If you can start helper agents, a helper may do steps 2 and 3 and return the spec; the conversation with the person stays with you.

## 1. Frame it

- Restate the request in one sentence, in the person's words. Note the problem behind it if they said one.
- Collect what the person already settled in this conversation (scope, who may do it, "both should be undoable"). Those are decided: design within them and never ask them again.
- Pick a short kebab-case slug. The spec goes in the project's UX folder if it has one (look for a `README.md` in `ux/`, `docs/ux/`, `wiki/ux/` or `design/`, which says where specs go and what to read); otherwise `ux/<slug>.md`. If the spec exists, update it and keep its decided rows.

## 2. Know the product before designing

Read what bears on the feature, not everything:

- the project's instructions (`AGENTS.md`, `CLAUDE.md`) and its UX folder's README;
- the brief: who the product is for, what it is not, the words it uses;
- the jobs map, personas or user flows, if the project keeps them: place the feature's job there;
- the design system or style rules: use its components and words, not new ones;
- what is agreed: decisions on record, and anything people agreed to. A design that goes against an agreed line is a decision for the person, never an assumption;
- the code: find how the product already does the nearest thing (a delete with undo, a picker, a notice, an agent tool's answer) and design the new feature the same way. Consistency with the product beats a better idea used once.

Mark every fact about the product with where it came from (a file and line, a document's section). A spec built on a wrong fact designs the wrong thing.

## 3. Design: the method

Work through these in order; each feeds the next. Keep each section as short as the feature allows. The principles behind each step are in [references/principles.md](references/principles.md); read the parts the feature touches.

1. **The job and the moment.** For each kind of person (and agent) the feature serves, write the moment: who they are, what just happened, how much time they have, what they are afraid of. Then the job story: "When [situation], I want to [motivation], so I can [outcome]". The motivation names no button or screen. Cover what they need done, how they want to feel and how they want to look to others. Say what the feature is not for. If no person has said it, mark the job as a hypothesis and say what would confirm it.
2. **Who and how often.** A table: who, how often (daily, weekly, monthly, rarely, once), the situation, what matters most then (speed, safety, confidence, a record for others). Then the frequency verdict, which drives the design: frequent tasks are fast, visible and repeatable without thinking; rare and risky ones are safe, explained and kept out of the frequent ones' way.
3. **Today.** What people do now: in the product, with a workaround, in another tool, by asking someone. Their words for it, quoted with a source when there is one. What the product already has to reuse, with paths.
4. **Journeys, through every way in.** The main journey as numbered steps: the trigger (the job's "When"), then each step as "person or agent does → product answers", to the done state and what they see then. Then: the other ways in (each door the feature has: the screen, a phone, the person's AI assistant, a coding agent, an API, an email link), the way back (undo, restore, correct a mistake), and what others see afterwards (teammates, their AIs, notifications, history, lists). Mark where someone could get lost or stopped. Design the most common path first and keep it shortest.
5. **The experience.** For each screen: where the control sits and why there, the components, the exact copy, the confirmation or undo, the feedback, where focus goes after each step, and what people without permission see. For each agent door: the tool or command's name, what it takes, what it answers (the agent's "screen"), the errors that name the next step, and what it says when nothing is found. For anything the product's AI suggests or does: why it shows, how to dismiss or correct it, and what it never does on its own ([references/ai-and-agents.md](references/ai-and-agents.md)). Add a small text wireframe when placement is not obvious. List every other screen, list, count, export, import, email or agent answer that must change with it.
6. **Edge cases and states.** Go through [references/edge-cases.md](references/edge-cases.md) and keep every row that applies, each with what the person or agent sees and the rule behind it.
7. **Decisions.** Three kinds. **Open**: only the person can decide (scope, who may do it, a business rule, anything against an agreed line); at most four, each with options, the recommended one first, and the consequence for the people who use it. **Assumed**: a sensible default you chose that the person may overrule. **Settled**: already decided, with who decided.
8. **Acceptance checks.** Numbered "Given … when … then …" lines, one per behaviour that matters, each written so it can become a test or a check in the running product.
9. **Size and the riskiest assumption.** Small, medium or large to build. If large: the smallest first version that still does the job, and the rest under "Later". Name the assumption that would sink the design if wrong and has least evidence, and the smallest test of it, with its pass line set now.
10. **Self-review.** Check the design against the self-review in [references/principles.md](references/principles.md) and fix what fails before showing it.

Write the spec with [references/spec-template.md](references/spec-template.md): plain words, short sentences, tables over prose, the title as the first heading. Use invented people and companies in examples, never real personal data.

## 4. Check the spec

Read the whole spec before showing it. Check each fact about the current product against the code or the documents it cites. Fix small errors; redo a section built on a wrong fact.

## 5. Settle the decisions with the person

- Ask the open decisions: at most four, one question each, the recommended option first and marked, and each option's consequence for the people using it. Use the question tool your client has; otherwise number them in plain text.
- Do not ask what the code, the brief or an agreed decision already answers; those are Assumed or Settled, and the person can still overrule them.
- Write the answers into the spec's Decisions table (who decided, the date) and set `- Status: decided`.
- Give the person a short summary: the job in one line, the main journey, what changes where, and the edge cases that changed the design. Link the spec. Their answers are the go-ahead to build unless they say to wait.

## 6. Build to the spec

- Follow the project's own rules for code, branches, review and release.
- Turn each acceptance check into a test where it can be one: a rule into a unit or service test, a state into a component test, a journey into an end-to-end test.
- When the feature changes a task people do, update the user guide and the jobs map.
- If building shows the design was wrong, change the spec too, and tell the person when it is a change they would notice. The spec describes what ships.

## 7. Walk the result

Walk each journey in the running product, through each door, as the person in the job's moment: [references/walk.md](references/walk.md). Go through the edge-case table row by row: each row is handled, or moved to "Later" with the person's agreement. Set `- Status: built` and link the change.

## When a spec is not needed

A refactor with no visible change, a fix that restores what was specified, a typo: say in one line that you are skipping the UX pass and why. A small feature gets a short spec, not none.

## Files

- [references/principles.md](references/principles.md): jobs, frequency, journeys, states, destructive actions, messages, accessibility, permissions, and the self-review, with sources.
- [references/ai-and-agents.md](references/ai-and-agents.md): designing for AI agents as users, and for people using AI features.
- [references/edge-cases.md](references/edge-cases.md): the edge cases and states checklist.
- [references/spec-template.md](references/spec-template.md): the spec's shape.
- [references/walk.md](references/walk.md): walking a journey and scoring it.
