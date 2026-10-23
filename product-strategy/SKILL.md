---
name: product-strategy
description: Writes, reviews and applies a product strategy, meaning the diagnosis of the challenge, the guiding policy, coherent actions and what the team will not do, then 1 to 3 measured outcomes, a roadmap in three columns (now, next, later) and a check of new work against it. Use at planning time, or when someone asks "write our strategy", "review this strategy", "what should we focus on", "set our OKRs", "build the roadmap", "we have too many priorities", "prioritise the backlog" or "does this project fit our strategy". Grounds every claim in evidence, flags goals and feature lists posing as strategy, and gets the team to agree to one version they can repeat.
license: MIT
metadata:
  source: https://alcoven.co/skills/product-strategy
  version: "2"
---

# Product strategy: name the challenge, choose, and say no

A strategy is a short argument: what is really going on (the diagnosis), the approach the team will take to it (the guiding policy), and a few actions that carry it out together (Richard Rumelt's kernel, 2011). You can tell it is a strategy by what it rules out. Most documents called a strategy are a goal ("triple revenue"), a list of features, or both. The person asking is usually at planning time, or has a team stretched over too many things. They fear committing everyone to the wrong bet in public, and a document nobody reads after the offsite. Keep it to a page or two, ground each claim in evidence, and make it short enough that anyone on the team can say it back.

Strategy chooses the few problems worth solving and the outcomes that show progress. Deciding what to build for each problem is discovery's job (the product-discovery skill).

## What you need

- **The vision**: the future the product is working toward, for its customers, in a sentence or a paragraph. If there is none, draft one sentence from the brief for the person to confirm.
- **The numbers today**, each with its date. For choosing the measures themselves, use the metrics skill if the project has it.
- **The insights**: what customers do and say (discovery notes, interviews), the market and competitors (the market-watch skill's briefs), what technology now makes possible, and the business's limits (cash, people, time).
- **What exists**: the current strategy, roadmap, OKRs, backlog, promises made to customers, decisions on record and anything people agreed to. Look in `strategy/`, `roadmap/`, `planning/`, `okrs/` and the brief.

## Pick the part

To write a strategy, do every step. To review one, use the review below. Outcomes or OKRs are step 6 (with no strategy, write a short diagnosis first), the roadmap is step 7, and "does this fit" or "prioritise this list" is step 8. A whole company's strategy gets the full method; one team's cycle inside an agreed strategy gets steps 6 to 8.

## The method

1. **Read the record and list the insights** (one of Cagan's four parts of product strategy): about customers, data, technology, the industry. Read before asking anything. Give each its source and date, and mark which are evidence and which are beliefs. *Output: the insight list.*
2. **Write the diagnosis.** One paragraph: what is going on, what makes it hard, and the crux, the part of the challenge that matters most and that the team can actually do something about (Rumelt, *The Crux*, 2022). Name the obstacle; a target says where you want to be and nothing about what stands in the way. *Output: the diagnosis, with its evidence cited.*
3. **Choose the guiding policy.** One or two sentences: the approach to the crux. It must rule out things someone on the team wants, and it should rest on an advantage (an insight others lack, a strength, focus). Write the two or three approaches you considered and why they lost. *Output: the policy and the alternatives.*
4. **Name the coherent actions.** Three to five actions that reinforce each other, each with an owner and the people or money it needs. Make the first ones close enough to reach with what the team has (Rumelt's proximate objectives). Actions that pull in different directions are a to-do list. *Output: the actions.*
5. **Write what you will not do.** Specific things people want or have asked for: customer segments, markets, features, projects to stop. Each with one line of why and when to look again. *Output: the not-do list.*
6. **Set 1 to 3 outcomes.** For each: the change in what customers or the business do, the measure, today's reading with its date, the target with its date, and a guardrail that must not get worse. Prefer what the team can move in weeks (what customers do in the product) to results it can only hope for. With OKRs: one objective per outcome, two to four key results that are measures (never tasks), each marked commitment or stretch, checked every week or two. Teams propose key results; leaders agree them. *Output: the outcomes table.*
7. **Lay out the roadmap: now, next, later.** Each item is a problem to solve, tied to an outcome. Now: what teams work on this cycle. Next: what is being shaped and tested. Later: directions, deliberately loose. Give dates only for real commitments (a contract, a regulation, an event), kept in their own short list and made after discovery has reduced the risk (Cagan's "high-integrity commitments"). *Output: the roadmap.*
8. **Check proposed work against it.** Which outcome does it serve? Does it fit the policy? Is it on the not-do list? What would it push out, what does waiting a month cost, how much time is it worth, what evidence is behind it? Answer: fits (to discovery, or into Now), doesn't fit (cite the line), or challenges the strategy (propose an edit). A score such as RICE can sort a long list and start the conversation. Methods and limits: [references/prioritising.md](references/prioritising.md). *Output: a cited verdict per proposal.*
9. **Get agreement, then keep it current.** Ask the team to agree to one version. Then test it: can two people each say the strategy in two sentences? If not, shorten it. Read the outcomes at a fixed rhythm; revisit the strategy each quarter, or sooner when the diagnosis changes (a failed bet, new evidence, a market move). Record each change and why.

The kernel, the review checks, outcomes, OKRs and roadmaps in detail: [references/method.md](references/method.md). The document's template and a worked example: [references/template-and-example.md](references/template-and-example.md).

## Reviewing a strategy

Start with what is strong. Then check it against Rumelt's four hallmarks of bad strategy and the kernel: **fluff** (grand words that commit to nothing), **failure to face the challenge** (no obstacle named), **goals mistaken for strategy** (targets with no approach), and **bad strategic objectives** (too many, or out of reach). Add: no not-do list, a roadmap of features with dates, outcomes with no baseline or date, and a strategy nobody can repeat. Give the two to four gaps that matter most, each with its fix, as suggestions.

## Common mistakes

| The mistake | Why it hurts | Instead |
|---|---|---|
| **A goal called a strategy.** "Our strategy is to reach $2M ARR." | It says where you want to be and nothing about what is in the way. | Diagnose the obstacle; the goal becomes one outcome (Rumelt). |
| **A feature list called a strategy.** | At least half of ideas won't work as hoped (Cagan); a list of them commits to guesses. | Problems and outcomes on the roadmap; features come out of discovery. |
| **No diagnosis.** | Nobody can judge whether the plan meets the real challenge. | Name the crux, with evidence. |
| **Fluff.** "Customer-centric, AI-first excellence." | Big words hide that no choice was made. | Plain sentences someone could disagree with. |
| **Too many priorities.** | Effort spreads thin and nothing moves. | One to three outcomes; the rest on the not-do list. |
| **Never saying what you won't do.** | Every request stays a maybe, and the team drifts back to everything. | A not-do list, looked at each quarter. |
| **A roadmap of features and dates promised to customers.** | Dates set before discovery harden into promises; teams ship on time and miss the result. | Now, next, later by problem; dates only for real commitments. |
| **OKRs as a task list.** "KR: launch the mobile app." | Done tasks, unchanged customers. | Key results that measure a change; tasks go in the plan. |
| **OKRs set and left.** Too many, cascaded per function, set low, no check-ins. | Functions chase separate goals; the quarter ends in surprise. | Few objectives per team, stretch marked, a weekly check-in on confidence (Christina Wodtke). |
| **A formula's false precision.** "RICE 412 beats 389." | Guesses multiplied together look like facts. | Sort with the score, then decide in conversation, with cost of delay and the evidence in view. |
| **A strategy nobody can repeat.** | If people can't say it, they can't decide with it. | Two sentences anyone can say; ask the team to agree to it. |
| **Set once, or rewritten weekly.** | A stale strategy gets ignored; a constantly changing one directs nothing. | A fixed rhythm; change it on new evidence, with the reason on record. |

Since AI made building cheaper (2023 to 2026), output is plentiful and proves little: teams that use AI to speed up a feature roadmap ship more without better results (Cagan, 2026). The not-do list and the outcomes matter more now.

## Speaking up

- **Once, with evidence and the cheapest fix.** "This draft reads as three goals. One paragraph on what stands in the way (churn after month two, numbers/retention, 20 Oct) would make it a strategy before the board sees it. Shall I draft it?"
- **Credit what is strong first. If they go ahead, do the work**, and note the open risk once in the document.
- **Match their pace**, and never repeat a concern they have decided on.

## What you never do

- Refuse or water down work because a step was skipped.
- Invent market data, benchmarks, customer evidence or targets. Targets come from the person; missing evidence is said to be missing.
- Change the strategy, a target or the roadmap on your own. Propose the edit.
- Promise dates to customers for the team.
- Treat a score as the decision, or rank people.

## In Alcoven

Pass the project's slug and cite by § address.

1. `open_project`: the brief, the home widgets with their readings, what is agreed and open. `agreed` with `about:` the strategy or the subject; `numbers` for each baseline and its date.
2. `related` with the draft diagnosis or the proposed work: what the project already holds on it, and anything that conflicts.
3. `add_document` for the strategy (for example `strategy/2026-q4.md`), after showing the person the text; changes later go through `edit_document`, which the person confirms.
4. `hand_out` with `ask: agree` and the person's own line on top: each member gets up to three passages that concern them (the not-do list to sales, an outcome to the team that leads it) and is asked to agree to this version.
5. One widget per outcome, from the source that holds its measure, with `- Compare: target 45 by 2026-12-31` and `- On home: yes` (four at most on the home).

To check new work, run `agreed` and `related` on the proposal and answer with § addresses; put the verdict on the proposal with `add_note`. Add a `task` for each check-in on the outcomes.

## Elsewhere

Keep the strategy as one file in `strategy/`, outcomes and roadmap inside it. Read the project's files first, use `git log` for what changed since the last version, and cite file paths. Record in the file who agreed, and when. With only the conversation, ask for the brief, the numbers and the current plan, and say what you could not see.

## Files

- [references/method.md](references/method.md): the kernel, the review checks, vision and strategy, outcomes and OKRs, roadmaps, what changed since 2023, sources.
- [references/prioritising.md](references/prioritising.md): prioritising methods and their limits, appetite and the betting table, saying no, checking work against the strategy.
- [references/template-and-example.md](references/template-and-example.md): the strategy document's template and a worked example.
