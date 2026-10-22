# Product discovery: the method in detail

The ideas behind each step of the method, with where they come from. Sources at the end, each read on 2026-10-22.

## Discovery and delivery

A product team does two kinds of work at once. **Discovery** tests, cheaply, whether an idea is worth building. **Delivery** builds it to the standard customers rely on: reliable, secure, able to grow. Marty Cagan's shorthand is "build to learn" and "build to earn" (SVPG, 2025 and 2026).

Discovery exists because of two facts Cagan set out in 2013: at least half of a team's ideas will not work (customers want them less than hoped, they are too hard to use, or they cost far more to build), and the ideas that do work usually take several rounds before they deliver. A plan that assumes each idea works first time is wrong in ways nobody sees until after the release.

## The four risks, and who owns them

Every idea carries four risks. Test them before building, and early, starting with value and business viability (Cagan, "The Four Big Risks", 2017; *Inspired*, 2nd edition, 2017).

| Risk | The question | Who leads on it |
|---|---|---|
| Value | Will customers buy it, or choose to use it? | Product manager |
| Usability | Can people work out how to use it? | Designer |
| Feasibility | Can we build it with the time, skills and technology we have? | Engineer (tech lead) |
| Business viability | Does it work for the business: sales, marketing, cost, legal, partners, brand? | Product manager |

Teresa Torres adds a fifth kind of assumption, **ethics**: whether offering it causes harm (who it serves, how data is used, trust and safety). Her five are desirability, viability, feasibility, usability and ethical (Product Talk, 2023).

## The trio, and what the product manager brings

Discovery is done by the people who will build: a product manager, a designer and an engineer, jointly responsible for one outcome, together from the first interview to the decision (Torres, "Product Trio", 2021). Engineers who only receive written requirements can't say what has just become possible, and the team pays in rework.

The product manager brings four kinds of knowledge (Cagan, *Inspired*): the customers, the data (how the product is used), the business (how it makes money and sells, and what it must not break), and the market and industry. When one is thin, say so; that is the team's blind spot.

## Outcomes over output

Teams in what Cagan calls the product model are given problems to solve and outcomes to reach, and they choose what to build; they are judged on whether it worked (Cagan, "The Product Operating Model", 2023; Cagan and Jones, 2020; Cagan, *Transformed*, 2024). An outcome is a change in what customers or the business do, with a measure.

Torres separates three kinds of measure (Product Talk, 2023):

- **Business outcome**: revenue, retention, cost. What the company needs, but slow to move and affected by much more than one team.
- **Product outcome**: a change in what customers do in the product ("regulars place a repeat pre-order each week"). The team can move it and see the effect within weeks. Prefer this.
- **Traction metric**: use of one feature ("people who click Export"). It assumes the feature is the answer, so it belongs after discovery has chosen the feature.

## The opportunity tree

Torres's opportunity tree (*Continuous Discovery Habits*, 2021) is a map from one outcome down to the tests that decide what to build:

1. **Outcome** at the root: one product outcome per tree, one tree per team.
2. **Opportunities** under it: customer needs, pains and wishes, heard in stories about specific times, grouped under the moments of the customer's experience where they happen. Larger opportunities break down into smaller ones.
3. **Ideas** under one chosen target opportunity: at least three.
4. **Assumption tests** under each idea.

Rules that keep it honest:

- An opportunity comes from what customers said or did, with a source. Before drafting one, have a clear outcome and three or four story-based interviews behind you.
- "Is there more than one way to address this?" If not, it is an idea dressed as an opportunity ("I want a loyalty card" is an idea; "my regulars drift to the café next door" is a problem).
- Choose the target by how many customers have it, how often, how much it hurts, and how it serves the strategy and the company's strengths. Leave effort out until assumptions are tested; hard problems are often the valuable ones.
- Generate ideas only for the target opportunity.
- Revisit the tree every three or four interviews; one interview, sales call or support ticket is no reason to redraw it. Start a new tree only when the outcome changes.

## Weekly conversations with customers

Torres defines continuous discovery as, at a minimum, weekly touchpoints with customers by the team building the product, running small research activities toward a desired outcome. The team that builds talks to customers itself (reports and personas don't replace it), and the activities are small enough to fit beside delivery.

**Ask for stories.** "Tell me about the last time you..." draws out what the person actually did. Questions about what they would do, or what they want, draw out guesses. Keep them on one specific time; when they drift to "usually", bring them back.

**Write a snapshot straight after.** One page per conversation, filled in while it is fresh: who it was with and quick facts about them, one memorable quote, a sketch of their story as steps, the opportunities heard (in their words), and any insights that are not opportunities. Torres suggests a 45-minute slot: about 20 to 30 minutes of interview, the rest to write the snapshot together.

**Make recruiting automatic** so the habit survives a busy week: a standing ask in the product, a list of customers who agreed to talk, a fixed weekly slot.

For how to run the conversation itself (questions, traps, synthesis), use the customer-interviews skill if the project has it.

## Assumptions and how to test them

Testing a whole idea means building it, which is slow. Testing the assumptions it rests on is fast, and lets weak ideas drop early (Torres, "Assumption Testing", 2023).

1. **Find them.** Walk the idea step by step as the customer would use it: what must they notice, want, understand and do at each step? A story map (below) is one way. Add what the business and the build must make true.
2. **Write each as a behaviour.** "Regulars set up a standing order in their first week" can be tested; "customers will like standing orders" cannot.
3. **Map them** by importance (if it is false, does the idea fail?) and evidence (how much do we already know?). Torres takes this from David Bland's *Testing Business Ideas* (2019). Test first what is important and has least evidence.
4. **Test small.** Four common kinds: a one-question survey about past or current behaviour; a prototype test that puts a person in a moment and watches what they do; data mining in what the team already has (usage data, support tickets, sales notes); and a research spike, where an engineer tries the hard part.
5. **Set the pass line first.** Write what result would count as a pass, as a number, before the test runs: "at least 4 of 6 bakeries set up a standing order without help". A line set afterwards bends to the result.
6. **Compare across ideas.** Run the same test on two or three ideas where you can. Decide on the pattern across several tests, never on one result. Failed tests are normal and say what to change.

## Prototypes

The kind of prototype follows the risk being tested (Cagan, "Flavors of Prototypes", 2014; *Inspired*, 2017; "The Purpose of Prototypes", 2025):

| Kind | What it is | The risk it tests |
|---|---|---|
| Feasibility | Code an engineer writes to try the hard part: a new technology, an algorithm, performance | Feasibility |
| User | A simulation, from a clickable sketch to something that looks real, with made-up data | Usability, and early signs of value |
| Live-data | A limited working version on real data, shown to a few real customers, often as a test against the current product | Value: whether it actually changes what people do |
| Hybrid | A mix, such as a person doing by hand behind the screen what the software would later do | Value, before any automation is built |

AI prototyping tools have made working prototypes cheap: a live-data prototype that took engineers weeks can now take days, and several ideas can be tried side by side (Cagan, 2025 and 2026). Its job is still to learn. Cagan is blunt that these tools are generally not for building actual products, and that a realistic prototype makes the gap to a real product look smaller than it is.

**AI features need one more test.** When the idea includes an AI model's output, quality varies from one answer to the next, so judge its quality early with evals (real cases the output is checked against), and keep tests with customers for whether it adds value (Cagan, "Experimentation, AI and the Product Model", 2026).

## How much to trust the evidence

Itamar Gilad's confidence meter (*Evidence-Guided*, 2023) ranks evidence from weakest to strongest: your own conviction; the idea being fashionable in the industry; colleagues' and managers' opinions; estimates and plans; a handful of customers asking; market data such as surveys; customers using a prototype, or interviews; test results; data from a real launch. Opinions, however senior, add almost nothing. Use it to say plainly how sure the team is: "two bakeries asked for it" is low on the meter, whatever the bakeries' size.

## Story mapping

Jeff Patton's story map (*User Story Mapping*, 2014) lays out a person's steps from left to right, with each step's details stacked below. In discovery it helps find assumptions and slice the smallest version that still gets the whole job done.

## What changed, 2023 to 2026

- **Building got cheap.** Andrew Ng argued in January 2025 that as AI makes writing software cheaper, demand grows for people who decide what is worth building. Cagan's 2026 posts say the same from the product side: the hard part now is deciding what to build.
- **Faster output can mean faster waste.** Teams that use AI to speed up a feature roadmap ship more and see no better results. Cagan quotes Hilary Gridley: it has never been faster to build, so it has never been easier to run fast in the wrong direction ("The AI Productivity Paradox", 2026).
- **More ideas can be tested in parallel.** Cheap prototypes make it practical to try several approaches to one problem in the same week and keep the best (Cagan, "Build to Learn vs Build to Earn", 2026).
- **AI helps with research; the trio still listens.** AI can summarise interviews and scale qualitative work; hearing customers first-hand is what makes the findings believable to the team (Cagan, 2026; Torres).

## Sources

- Marty Cagan, *Inspired: How to Create Tech Products Customers Love*, 2nd edition, Wiley, 2017. Publisher listing via O'Reilly, read 2026-10-22.
- Marty Cagan, "The Inconvenient Truth About Product", SVPG, 2013. https://www.svpg.com/the-inconvenient-truth-about-product/, read 2026-10-22.
- Marty Cagan, "The Four Big Risks", SVPG, 2017. https://www.svpg.com/four-big-risks/, read 2026-10-22.
- Marty Cagan, "Flavors of Prototypes", SVPG, 2014. https://svpg.com/flavors-of-prototypes/, read 2026-10-22.
- Marty Cagan, "The Purpose of Prototypes", SVPG, 2025. https://www.svpg.com/the-purpose-of-prototypes/, read 2026-10-22.
- Marty Cagan, "Prototypes vs Products", SVPG, 2025. https://www.svpg.com/prototypes-vs-products/, read 2026-10-22.
- Chris Jones and Marty Cagan, "Stakeholders and the Product Model", SVPG, 2025. https://www.svpg.com/stakeholders-and-the-product-model/, read 2026-10-22.
- Marty Cagan, "Build to Learn vs Build to Earn", SVPG, 2026. https://www.svpg.com/build-to-learn-vs-build-to-earn/, read 2026-10-22.
- Marty Cagan, "The AI Productivity Paradox", SVPG, 2026. https://www.svpg.com/the-ai-productivity-paradox/, read 2026-10-22.
- Marty Cagan, "Experimentation, AI and the Product Model", SVPG, 2026. https://www.svpg.com/experimentation-ai-and-the-product-model/, read 2026-10-22.
- Marty Cagan, "The Product Operating Model: An Introduction", SVPG, 2023. https://svpg.com/the-product-operating-model-an-introduction, read 2026-10-22.
- Marty Cagan and Chris Jones, *Empowered*, Wiley, 2020; Marty Cagan and others, *Transformed*, Wiley, 2024. https://www.svpg.com/TRANSFORMED, read 2026-10-22.
- Teresa Torres, *Continuous Discovery Habits*, Product Talk, 2021; "Continuous Discovery" glossary entry. https://www.producttalk.org/glossary-discovery-continuous-discovery/, read 2026-10-22.
- Teresa Torres, "Opportunity Solution Trees", her guide to the tree, Product Talk, 2023. https://www.producttalk.org/opportunity-solution-trees/, read 2026-10-22.
- Teresa Torres, "Product Trio", Product Talk, 2021. https://www.producttalk.org/product-trio/, read 2026-10-22.
- Teresa Torres, "The Interview Snapshot", Product Talk, 2024. https://www.producttalk.org/interview-snapshot/, read 2026-10-22.
- Teresa Torres, "Assumption Testing" and "Five Types of Assumptions", Product Talk, 2023. https://www.producttalk.org/assumption-testing/ and https://www.producttalk.org/five-types-of-assumptions/, read 2026-10-22.
- Itamar Gilad, *Evidence-Guided*, 2023; "The Tool That Will Help You Choose Better Product Ideas" (the confidence meter), https://itamargilad.com/the-tool-that-will-help-you-choose-better-product-ideas/; "From opinion-based to evidence-guided product development", Mind the Product, 2022. Read 2026-10-22.
- Jeff Patton, *User Story Mapping*, O'Reilly, 2014. https://www.jpattonassociates.com/story-mapping/, read 2026-10-22.
- David J. Bland and Alexander Osterwalder, *Testing Business Ideas*, Wiley, 2019 (assumption mapping, as cited by Torres).
- Andrew Ng, "AI Product Managers Will Be In-Demand", The Batch, 15 January 2025. https://www.deeplearning.ai/the-batch/ai-product-managers-will-be-in-demand/, read 2026-10-22.
