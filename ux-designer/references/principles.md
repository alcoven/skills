# UX principles

The rules behind each step of the method. Where they disagree, the product's existing pattern decides; where it has none, write the choice down as Assumed. Sources at the end.

## Jobs, not features

- Write the moment first: who, what just happened, how much time they have, what they fear. A person late to a meeting has thirty seconds; design for the thirty seconds.
- Then the job story: "When [situation], I want to [motivation], so I can [outcome]". The situation is concrete; the motivation names no button, screen or field; the outcome is the progress the person wants.
- Cover the functional, emotional and social sides: what gets done, how they want to feel ("not anxious about the client call"), how they want to look ("not careless in front of a client", "not the one who lost a colleague's work").
- A job that only makes sense with your design in it ("I want to click Delete") is design-shaped: ask "so I can what?" until it is not.
- Measure success as outcomes: a direction, a metric and an object, with no design in it ("minimise the time to learn what changed while I was away").
- Every element in the design traces back to a job. Say what the feature is not for, so scope stays small.
- A job nobody has said out loud is a hypothesis. Mark it, and say what a person would have to say or do to confirm it.

## Test the riskiest assumption before building

- Put one outcome at the top (what should change for people), the needs and pains under it, drawn from stories people told about a specific time, and the ideas under those. To catch an idea dressed as a need, ask "is there more than one way to answer this?"
- For the need you choose, think of at least three ways to answer it before picking one.
- List what must be true for the chosen design to work, in five kinds: people want it, it pays, it can be built, people can use it, it does no harm. Write each as something a person must do ("the keeper adds a skill on the first day").
- Test first what matters most and has least evidence, with the smallest test that finishes in an hour (a walk, a prototype in front of one person, a one-question message, existing data), and set the pass line before the test.
- Talk to the people the feature is for every week, while it is designed and after it ships.

## Frequency drives the design

- Do a light task analysis: the goal, then each step with how often it happens, how long it takes and the decision in it. Then cut steps and repeated input.
- Show first what people need often; put the rest one labelled step away, two levels at most. Give frequent actions shortcuts that stay out of a newcomer's way.
- Friction follows severity and reversibility, not rarity. Easy to undo: no friction. Harder to undo: one extra step. Hard to undo or cascading: a dialog that names the consequences.
- Keep destructive actions apart from routine ones (people on autopilot click what is near): never next to the primary action, never the primary button, marked by more than colour.

## Journeys

- For one feature, draw a user flow, not a journey map: the trigger, the ways in and how people find them, each step with the product's answer, the decision points, the exits (done, cancelled, failed) and how to recover from each failure. Use a journey map for a whole experience over days, and a service blueprint when the work behind the screen (people, systems, agents) is the problem.
- Walk the flow through every door the feature has. A person in the app, the same person through their AI assistant, and a coding agent in a folder should reach the same result by the same rules.
- Design the most common path first and keep it shortest; branch rare cases off it.
- Time to value: count the steps from the trigger to the moment the person gets what they came for. Every step before that moment is a reason to leave; cut it, defer it, or do it for them.

## States and edge cases

- Design all five states of every view: ideal, empty, error, partial and loading. Empty comes three ways: first use, cleared by the person, no results. An error keeps everything the person typed.
- Empty is never blank: say how it fills up and give the action, or start it with useful content. Never show "nothing here" while data is still loading.
- Loading: nothing under 1 s; an indeterminate indicator for 1 to 3 s; progress for 3 to 10 s; beyond 10 s, progress with cancel, or run it in the background and say where the result will appear.
- A part that fails is replaced on its own; the rest stays usable, and nothing suggests data was lost.
- Two people on one record: on save, check the version; say who changed it and when, and offer to see their change. A record deleted since the page loaded says who deleted it and when, with Restore where the person may restore it, not a bare "not found".
- Long names are cut with an ellipsis and shown in full on hover and focus; titles, labels and error messages are never cut. Casing depends on the language (Turkish i → İ): never upper-case people's data yourself; compare and sort with the locale.
- Wording for zero, one and many, in every language the product speaks.

## Destructive actions

- Deleting stored data is reversible, checked or confirmed (WCAG 3.3.4); being able to restore is enough on its own.
- Match the guard to the damage. Easy to recreate: one click. Hard to recreate, or several at once: a confirmation. Irreversible or cascading: a dialog that lists the consequences; typing the name only for a permanent purge.
- A confirmation names the thing ("Delete the project Kiln launch?"), says what goes with it ("its 12 documents and 4 tasks") and how to get it back. Buttons say what happens ("Delete project" / "Cancel"), never Yes/No and never "Are you sure?". Focus starts on Cancel.
- Prefer undo to warning. An undo in a notice only when the same undo exists elsewhere (a Restore in a deleted list); keep such a notice at least 10 s.
- A deleted list is a real view; restore and permanent delete are separate actions. Record who deleted and who restored, and when.

## Messages and focus

- Errors are specific, plain and blameless, and say how to fix it; they sit next to the field and repeat its label's words. No "invalid", "oops", "please" or "sorry".
- Validate when the person leaves a field, clear the error as soon as it is fixed, validate again on submit.
- Inline for one field or row; a banner for the page (one, above the heading); a short notice for news that is not essential. Announce every result, including success, to screen readers (`role="status"`; `role="alert"` for errors).
- After an item is removed, focus moves to the next item, or to the list's heading when the list is empty.

## Accessibility (WCAG 2.2 AA)

- Dialogs: focus moves in and stays in, Escape closes, focus returns to what opened it (or the next sensible place if that is gone), labelled by its title.
- Targets at least 24 px with space around them; 44 px on touch.
- Focus is never hidden behind a sticky header, a notice or a drawer (2.4.11); whatever drags also works with one click (2.5.7); nothing asks again for what was already entered (3.3.7).
- Never colour alone; reflow at 320 px without sideways scrolling (tables excepted); mark each language part with `lang`; honour reduced motion.

## Permissions and tables

- Hide what this person can never use; disable, with one sentence why ("Only managers can remove people."), what they could get by asking. Never disable a form's submit button.
- The same rules through every door: what a person can't see in the app, their AI can't read either, and the agent's error says why in the same words.
- In tables the first column names the row; active filters and hidden columns show. Bulk actions: checkboxes with an all/none/some header box, a bar with the selected count, and the spec says whether "select all" means the page or every match.
- Consistency over novelty: reuse the product's components and words for the same thing.

## Self-review

Nielsen's ten heuristics:

1. People always see what is happening.
2. The people's words, not ours.
3. A clear way out and back.
4. One word and one pattern for one thing.
5. Errors prevented before they are confirmed.
6. Options visible, nothing to remember.
7. Shortcuts for frequent work.
8. Nothing on screen that is rarely needed.
9. Errors say what happened and the fix.
10. No help needed, or help close by.

Then the checks this skill adds:

11. Each element traces to a job; the spec says what the feature is not for.
12. The most frequent path is the shortest, and the time to value is counted.
13. Every door reaches the same result by the same rules; the agent's answers and errors name the next step.
14. Anything the product's AI suggests or does says why, can be dismissed or corrected in one step, and never acts alone where the person expects to decide (see [ai-and-agents.md](ai-and-agents.md)).
15. Every row of the edge-case checklist that applies has an answer.

## Sources

Teresa Torres on opportunity solution trees, assumption testing and the five kinds of assumptions (producttalk.org/opportunity-solution-trees, producttalk.org/assumption-testing, producttalk.org/five-types-of-assumptions); NN/g on cognitive walkthroughs, testing with five users, and user flows vs journey maps (nngroup.com/articles/cognitive-walkthroughs, /why-you-only-need-to-test-with-5-users, /user-journeys-vs-user-flows, /ux-mapping-cheat-sheet); Intercom on job stories (intercom.com/blog/using-job-stories-design-features-ui-ux); Christensen Institute (christenseninstitute.org/jobs-to-be-done); Strategyn outcome statements (strategyn.com/jobs-to-be-done/customer-needs); NN/g on progressive disclosure, task analysis, user flows, journey maps and service blueprints, empty states, response times, confirmation dialogs, error messages, data tables and the ten heuristics (nngroup.com/articles); GitLab Pajamas destructive actions (design.gitlab.com/patterns/destructive-actions); Cloudscape delete patterns and disabled states (cloudscape.design/patterns); Carbon modal accessibility, overflow content and data tables (carbondesignsystem.com); Primer loading and degraded experiences (primer.style/product/ui-patterns); Polaris toast (polaris.shopify.com); GOV.UK error messages, notification banners and design principles (design-system.service.gov.uk); Hurff's UI stack (scotthurff.com); Raskin, "Never use a warning when you mean undo" (alistapart.com/article/neveruseawarning); Smashing Magazine on dangerous actions and hidden vs disabled (smashingmagazine.com); Inclusive Components (inclusive-components.design); W3C WCAG 2.2 Understanding pages and the APG dialog pattern (w3.org/WAI).
