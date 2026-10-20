# The spec's shape

Plain words, short sentences, tables over prose. The title is the first heading. Name project people the way the project does (by member id where it uses them) and users by role. Keep every section as short as the feature allows.

```markdown
# UX: <feature>

- Status: draft | decided | built
- Asked: <the request, in the person's words>
- For: <who asked> · Spec by: ux-designer · <YYYY-MM-DD>
- Read: <the documents and code paths this rests on>

## The job
<per kind of person or agent: the moment (who, what just happened, how much time, what they fear),
then "When …, I want to …, so I can …"; hypothesis or heard, and from whom; what it is not for>

## Who and how often
| Who | How often | Situation | What matters most |
Frequency verdict: <one or two lines>. Place in the jobs map: <section, if the project keeps one>.

## Today
<what people do now and their words for it; what the product already has to reuse, with paths>

## Journeys
### Main: <name>
Trigger: <the job's "When">
1. <person or agent does> → <product answers>
...
Done when: <what they see>. Steps to value: <n>.
### Other ways in
<each door: the screen, phone, the person's AI, a coding agent, an API, an email link>
### The way back
<undo, restore, correcting a mistake>
### What others see
<teammates, their AIs, notifications, history, lists>

## The experience
<placement and why; components; copy table (where | text); confirmation or undo; feedback; focus;
permissions; for each agent door: the tool's name, input, answer, errors and empty answer;
for each AI suggestion or action: why it shows, dismiss and correct, what it never does alone;
other screens and answers that change; a text wireframe if placement is not obvious>

## Edge cases and states
| Case | What the person or agent sees | Rule |

## Decisions
| | Decision | Options (recommended first) | Consequence | Decided by |
<rows marked Open, Assumed or Settled>

## Acceptance checks
1. Given … when … then …

## Size and later
<small / medium / large; the smallest first version; what is left for later>
```

## What a helper returns

When a helper agent writes the spec for the main session, its last message says:

- the spec's path;
- five lines: the job, the frequency verdict, the main journey in one line, the two or three edge cases that shaped the design, the size;
- the open decisions, each as a question with its options (recommended first) and one line on the consequence of each, ready to ask;
- anything it could not check, and any fact about the code it is unsure of.
