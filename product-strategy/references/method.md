# Product strategy: the method in detail

The ideas behind each step, with where they come from. Sources at the end, each read on 2026-10-22.

## The kernel

Richard Rumelt (*Good Strategy Bad Strategy*, 2011) defines good strategy as coherent action backed by an argument, and gives it three parts:

| Part | What it is | Test it with |
|---|---|---|
| **Diagnosis** | An explanation of what is going on, simple enough to act on: it picks out the few things that matter from everything that is true. | Does it name an obstacle? Could a smart outsider disagree with it? Is there evidence for it? |
| **Guiding policy** | The overall approach to the obstacle the diagnosis names. It works like a guardrail: it rules some paths out without listing every step. | What does it rule out that someone wants? What advantage does it rest on? |
| **Coherent actions** | Steps that carry out the policy and support each other, with the resources committed. | Do the actions reinforce each other, or would each make sense in any strategy? Who does them, with what? |

**The crux.** In *The Crux* (2022), Rumelt sharpens the diagnosis: of all the challenges, find the one that is both important and addressable, where action promises the most progress. He borrows the word from climbing, where it means the hardest move on a route. A team that names the crux spends its effort there.

**Proximate objectives.** The first actions should be close enough that the team can reach them with what it has, given the diagnosis. A far goal with no near step leaves people unsure what to do on Monday.

## The four hallmarks of bad strategy

Rumelt's list, with the question to ask of a draft:

1. **Fluff.** Grand, abstract words that sound like thinking ("customer-centric excellence through innovation"). Ask: what does this sentence commit us to? If nothing, cut it.
2. **Failure to face the challenge.** The document never says what is hard. Ask: what is the obstacle, in one sentence? If nobody can say, there is nothing to judge the plan against.
3. **Mistaking goals for strategy.** Targets and wishes ("grow 3x", "be the leader in...") presented as the plan. Ask: how will we get past what stands in the way?
4. **Bad strategic objectives.** Too many, unrelated, or out of reach; a long list of things to do, labelled strategic. Ask: if we did only three of these, which, and why those?

Add the checks this skill uses: no not-do list; a roadmap of features with dates; outcomes without a baseline or a date; and a strategy nobody on the team can repeat.

## Vision and product strategy

Marty Cagan separates the two (SVPG, 2020 and 2023; Cagan and Jones, 2020):

- **Product vision**: the future the company is trying to create for its customers, usually several years out, meant to inspire and to guide choices. It changes rarely.
- **Product strategy**: how the team will move toward the vision while meeting the business's needs. Cagan names four parts: **focus** (choose the few objectives that matter most, which means deciding what not to pursue), **insights** (from customers, data, technology, the industry, the business), **action** (turn the insights into problems for specific teams to solve), and **management** (leaders stay involved, help teams with obstacles and adjust as they learn, without dictating how).

In Cagan's product model, deciding which problems to solve is a leadership job guided by the vision and strategy; deciding how to solve them is the team's job (the product-discovery skill). Rumelt's kernel and Cagan's strategy fit together: the diagnosis comes from the insights, the guiding policy is the focus, and the coherent actions are the problems handed to teams.

## Outcomes, and OKRs done well

An outcome is a change in what customers or the business do, with a measure, a baseline and a dated target. Output is what the team ships. Cagan's 2026 framing is that every company trades outcomes against predictability: a culture that ranks "delivered what we promised" first gets output, whatever its slides say.

**Choose one to three.** More spreads the team thin. For each, add a guardrail: a health measure that must not get worse while you push (support load, refunds, reliability).

**OKRs** are one way to write outcomes. Andy Grove used them at Intel; John Doerr brought them to Google and wrote them up in *Measure What Matters* (2018):

- The **objective** says what you want to achieve, in plain words.
- The **key results** say how you will know: specific, time-bound and measurable, so each is clearly met or not. Doerr's site suggests three to five per objective; Christina Wodtke (*Radical Focus*, 2016, 2nd edition 2021) suggests one objective per team and three key results.
- Mark each as **committed** (expected to be met in full) or **aspirational** (a stretch). Google's guide grades key results from 0.0 to 1.0 and calls 60 to 70% the sweet spot; always scoring 1.0 means the goals were too easy.
- **Key results measure outcomes.** Words like "launch", "build", "consult" or "analyse" signal a task. Google's guide says the same.
- **Check in weekly.** Wodtke's Monday check-in covers this week's three or four priorities, confidence in each key result out of ten, the next month's work, and two health measures to protect. She suggests setting a stretch at about 5 out of 10 confidence. A Friday session shows what was finished.
- **OKRs and KPIs differ.** A KPI tracks the health of something already running; an OKR aims at a change. Keep health measures as guardrails.

**Common OKR failures** (Doerr's site, Google's guide, Wodtke, Cagan): too many objectives; key results that are tasks or features; sandbagging (targets set low to be safe); no check-ins until the quarter ends; objectives cascaded down each function, so the engineer, designer and product manager on one team chase different goals (Cagan's central complaint, "Team Objectives", 2020); individual OKRs tied to performance reviews; and OKRs used in a company that still hands teams a feature roadmap, so the objective is decoration. Cagan's conclusion in 2020 was that OKRs rarely help until teams are given problems to solve.

## Roadmaps

**Why feature roadmaps fail.** Cagan (2015) gives roadmaps two real purposes: making sure teams work on what matters most, and letting the business plan around dates it truly needs. A list of features with dates serves neither well: the problem behind each feature is often unstated, at least half the ideas will not work as hoped, and the ones that work need several rounds. Teams ship on time and miss the result.

**The alternative.** Give each team its problems and outcomes, from the strategy, and let it discover what to build. For the few cases that need a date, make a **high-integrity commitment**: a date given only after enough discovery to know the work is valuable and feasible, used sparingly (Cagan; Jones and Cagan, 2025).

**Now, next, later.** Janna Bastow and Simon Cast at ProdPad drew the roadmap as three columns with no dates: what the team is working on now, what comes next, and what is further out. Bastow describes a roadmap as a strategic communication document: if an item is not part of the strategy, it is not on the roadmap. Detail falls as the horizon grows: Now items are specific problems with owners; Next items are problems being shaped and tested; Later items are directions. Write each as a problem tied to an outcome, with no date.

## What changed, 2023 to 2026

- **Building got cheap.** Andrew Ng argued in January 2025 that as AI makes writing software cheaper, the scarce skill is deciding what is worth building. Cagan wrote in 2026 that building is no longer the hard part.
- **Output stopped proving anything.** Teams using AI to speed up the old feature roadmap ship more and see no better results (Cagan, "The AI Productivity Paradox", 2026). Cagan quotes Hilary Gridley's line that it has never been easier to run fast in the wrong direction.
- **So the strategy's job of saying no grows.** When a team can build three things in the time one used to take, the temptation is to build all three. The not-do list, the one to three outcomes, and checking each proposal against them are what keep cheap building from turning into scattered work.

## Sources

- Richard P. Rumelt, *Good Strategy Bad Strategy*, Crown Business, 2011; "The perils of bad strategy", McKinsey Quarterly, 2011. Summaries read 2026-10-22: Perdoo's and Kellblog's reviews of the book.
- Richard P. Rumelt, *The Crux: How Leaders Become Strategists*, PublicAffairs, 2022. https://www.hachettebookgroup.com/titles/richard-p-rumelt/the-crux/9781541701243/, read 2026-10-22.
- Marty Cagan, "Product Strategy Overview", SVPG, 2020. https://www.svpg.com/product-strategy-overview/, read 2026-10-22.
- Marty Cagan, "The Product Operating Model: An Introduction", SVPG, 2023. https://svpg.com/the-product-operating-model-an-introduction, read 2026-10-22.
- Marty Cagan, "Team Objectives: Overview", SVPG, 2020. https://www.svpg.com/team-objectives-overview/, read 2026-10-22.
- Marty Cagan, "The Alternative to Roadmaps", SVPG, 2015. https://svpg.com/the-alternative-to-roadmaps/, read 2026-10-22.
- Marty Cagan, "The Inconvenient Truth About Product", SVPG, 2013. https://www.svpg.com/the-inconvenient-truth-about-product/, read 2026-10-22.
- Marty Cagan, "Predictability vs Outcomes", SVPG, 2026, and "The AI Productivity Paradox", SVPG, 2026. https://www.svpg.com/predictability-vs-outcomes/ and https://www.svpg.com/the-ai-productivity-paradox/, read 2026-10-22.
- Chris Jones and Marty Cagan, "Stakeholders and the Product Model", SVPG, 2025. https://www.svpg.com/stakeholders-and-the-product-model/, read 2026-10-22.
- Marty Cagan and Chris Jones, *Empowered*, Wiley, 2020; Marty Cagan and others, *Transformed*, Wiley, 2024.
- John Doerr, *Measure What Matters*, Portfolio, 2018; "OKR meaning, definition and examples", What Matters. https://www.whatmatters.com/faqs/okr-meaning-definition-example, read 2026-10-22.
- Google re:Work, "Set goals with OKRs". https://rework.withgoogle.com/en/guides/set-goals-with-okrs, read 2026-10-22.
- Christina Wodtke, *Radical Focus*, 2016, 2nd edition 2021; "The Art of the OKR", 2014, and "Monday Commitments and Friday Wins", 2014, Eleganthack. https://eleganthack.com/the-art-of-the-okr/ and https://eleganthack.com/monday-commitments-and-friday-wins/, read 2026-10-22.
- ProdPad, "About us" (Now-Next-Later). https://www.prodpad.com/about-us/, read 2026-10-22; Janna Bastow interview summaries, read 2026-10-22.
- Andrew Ng, "AI Product Managers Will Be In-Demand", The Batch, 15 January 2025. https://www.deeplearning.ai/the-batch/ai-product-managers-will-be-in-demand/, read 2026-10-22.
