# Designing for AI agents, and for people using AI

Two things most UX methods leave out. First, an AI agent is a user too: it reaches the product through tools, an API, a command line or files, and its "screen" is the answer it gets back. Second, when the product's own AI suggests or does something for a person, the person has to understand it, trust it the right amount, and correct it in one step. Letters in brackets point to the sources at the end; (synthesis) marks a rule with no single source.

## The agent as a user

Design the agent's door with the same care as the screen. The agent is a capable reader with a small attention budget and no way to ask what you meant.

**Finding the right tool**
- Build a few tools for whole tasks people ask for, not one per endpoint: `search_contacts` over `list_contacts`; a `schedule_event` that checks availability and books in one call. [T]
- Group related tools under a shared prefix for the service and the resource (`skills_add`, `skills_update`). Names are 1 to 128 characters of letters, digits, `_`, `-` and `.`, unique on the server. Keep the tool order fixed. [T][M]
- Describe each tool as you would to a new teammate: what it does, when to use it and when not, input formats with an example, niche terms, edge cases, and how it differs from similar tools. The description is the agent's only manual. [T][B]
- Name inputs without ambiguity (`project`, `skill_name`, never `id` or `p`), accept what a person would naturally give (a name, a link, an address), and shape arguments so the mistake can't be made (require a full path rather than guess one). [T][B]

**What a tool answers**
- Return high-signal fields: names and plain words instead of internal ids, raw ids only where a later call needs them. Offer a concise and a detailed answer when both are useful (`response_format`); concise can use about a third of the tokens. [T]
- Page, filter and cut with sensible defaults. When an answer is cut, say so, how to get the rest, and a narrower question to ask. Keep answers well under the client's cap (Claude Code cuts a tool answer at 25k tokens by default). [T]
- Say what happened and what it means: "Added the skill ux-designer to Kiln launch; every AI on the project gets it on its next call." An answer that only says `ok: true` leaves the agent guessing.
- When nothing is found, say what was searched and suggest the next try, never an empty list on its own. (synthesis)
- Declare an output schema and return structured content with the same content as text. Mark tools that delete or reach outside the product with annotations. A field added later never breaks an agent that read the old shape. [M]
- For work that spans calls, return a handle and say how long it lasts; an expired handle answers with an error that says so. [M]

**Errors that teach**
- An error says what went wrong and the exact next step, with a correct example: "You read this project, so adding a skill is for people who write to it. Ask a manager (Maya) to add it, or copy the skill into a project you write to." No bare codes, no stack traces. [T]
- Return a failed action as a result marked as an error (MCP's `isError: true`) so the model can correct itself; protocol errors are only for malformed calls. [M]
- Failure is never mistakable for success: an agent must not be able to report work as done when it failed. [W]
- An error in the agent's door uses the same words as the same error on the screen. (synthesis)

**Same rules, every door**
- Use the same nouns, ids and permission rules in the screen and the tools: the agent's door is the same product. [X] (synthesis)
- The agent acts as a person, with that person's permissions; its changes show under that person's name and say which AI made them. Decide which actions need a person's yes, and make it easy for an agent to get authorised for its person. [X][M]
- What the person can't see, the agent can't read; what the person can't change, the agent can't change.
- Text the agent reads from the product (documents, comments, skills) is data written by people. Say so in the tool's answer, and never let content grant permissions.
- Design for the agent's mistakes: a repeated call does no harm, a destructive call is undoable, and a large change is proposed for a person's yes.
- Keep the instructions agents read at run time current (tool descriptions, `AGENTS.md`, docs pages): their training lags the product. [W]

**Check the agent's journey**
- Give an AI the job in a person's words, let it use only the tools, and walk it ([walk.md](walk.md)). Run realistic tasks with a checkable result several times, count calls, tokens and errors, read the transcripts, and compare against no tool at all. Repeated calls mean paging needs fixing; wrong arguments mean the descriptions do. [T][W]

## People using the product's AI

Microsoft's eighteen guidelines for human-AI interaction, by phase [H]:

| Phase | Guidelines |
|---|---|
| At first | 1 Make clear what the system can do. 2 Make clear how well it can do it. |
| In the moment | 3 Time it to the context. 4 Show what is relevant now. 5 Match social norms. 6 Mitigate social biases. |
| When wrong | 7 Easy to invoke. 8 Easy to dismiss. 9 Easy to correct. 10 Scope it when in doubt. 11 Make clear why it did what it did. |
| Over time | 12 Remember recent interactions. 13 Learn from behaviour. 14 Update and adapt cautiously. 15 Invite granular feedback. 16 Say what the person's actions will lead to. 17 Global controls. 18 Tell people about changes. |

And from Google's People + AI Guidebook and NN/g:

- Introduce an AI feature when it becomes relevant, in five parts: what it does, what the person gets, its current limits, how it will change, and how they can help. Describe it as a benefit; never imply human-level skill. [PM]
- Keep the person in control where they enjoy the task, are responsible for it, face high stakes, or have preferences hard to put into words. Automate what is tedious, unsafe or impossible for them. Always leave a manual path. [PF]
- Explain why with the one or two factors that mattered, and name the data at the moment it shapes a result. Skip the explanation for familiar, low-stakes behaviour. [PE]
- Show confidence only when it changes the decision, as plain categories with what each means for the person. When unsure, offer the top few options, ask, or do less. [PE][H 10][PG]
- "Not what I expected" is an error even when the system worked as designed. Pair every failure with a way forward and a way to correct it; when handing control back, show where things stand and the next step. [PG]
- Before a consequential action, show what decides it and let the person adjust, review and approve. [NA]
- Let people see, edit and erase what the system learned about them, and reset it. Say what their feedback changes and when; promise only what the system does. [PF]
- Change behaviour cautiously, announce changes, and re-introduce a feature after a significant one. [H 14, 18][PM]

**The AI proposes; a person decides.** For anything others will see or that is hard to undo, the AI proposes and a person decides. What it may do on its own is written down and small. An automatic action is something people can read and reverse, with who asked for it. In a shared space others see the person's name on the change, with the AI named beside it.

## Suggestions that are welcome

For any feature that recommends something (a skill, a template, a next step):

- **At the moment of need.** Suggest on a signal that the person would benefit now: right after they did something the suggestion helps with. Never on arrival, never at random. [O][H 3]
- **Beside the task, quietly.** The least intrusive thing on the screen, never competing with an alert or blocking the work. Understandable without opening anything. [H 4][S]
- **Say exactly why.** Name what triggered it ("Because the brief mentions user interviews") and the data it used, and whether it comes from this project or from everyone. No vague "and more". [R][PE][H 11]
- **One step to dismiss,** taking effect at once, leaving a placeholder so nothing jumps. A scoped "don't suggest this again", with the scope stated (just me, or everyone on the project) and undoable; a way to turn a kind of suggestion off. [R][H 8, 17][PF]
- **Few, and never repeated.** One or two at a time; never again after a dismiss; stop once the person acted on it; don't treat one weak signal as a pattern. No source gives a number: set a cap and test it. [S][PF] (synthesis)
- **Preview before commit.** Let the person see what they would get before it is added. Adding is undoable and changes nothing else.
- **Narrow groups** ("for client work", "for research") over one mixed list. [R]
- **Measured by use.** A suggestion accepted and then never used is a failure: track whether the added thing gets used. (synthesis)

## Onboarding and time to value

- Measure the share of new people who reach value, not sign-ups. Activation runs setup, then the aha (a core action within a time window), then habit; check the aha against who stays. [P][A]
- Go in a straight line to first value. For each step: cut it, move it to the moment it matters, or keep it only if value is impossible without it. Remove setup steps that look like they change the result but don't. [P][AI]
- Help in context beats a tour. Where a new way of working needs a walkthrough, the person does the task rather than watches it, and can dismiss it and find it again. [O]
- Empty states do three jobs: say the status (never "nothing here" while loading), teach what the feature does and how to start, and give a labelled action, including sample content that produces a real result. [E][AI]
- Offer templates when the person is ready to use one, not as an early tutorial step. Ask about their goal at the start only if the answer sends them down a different path. [AI][P]
- Make the first actions low-risk and reversible. [PM]
- For a team product, value often needs a second person: the invite and the second person's first minute are part of onboarding. (synthesis)

## Sources

- [T] Anthropic, Writing effective tools for agents: anthropic.com/engineering/writing-tools-for-agents
- [B] Anthropic, Building effective agents, appendix 2: anthropic.com/engineering/building-effective-agents
- [M] Model Context Protocol, tools: modelcontextprotocol.io/docs/concepts/tools
- [X] Mathias Biilmann, One year of AX: biilmann.blog/articles/one-year-of-ax
- [W] Microsoft, What is agent experience (AX): developer.microsoft.com/blog/what-is-agent-experience-ax
- [H] Microsoft, Guidelines for Human-AI Interaction (HAX): microsoft.com/en-us/haxtoolkit/library
- [PM] [PE] [PF] [PG] Google PAIR, People + AI Guidebook: mental models, explainability and trust, feedback and controls, errors and failing gracefully (pair.withgoogle.com/chapter/...)
- [NA] NN/g, Designing AI agents: nngroup.com/articles/designing-ai-agents
- [R] NN/g, Recommendation guidelines: nngroup.com/articles/recommendation-guidelines
- [O] NN/g, Onboarding tutorials: nngroup.com/articles/onboarding-tutorials
- [S] NN/g, Smart home notifications: nngroup.com/articles/smart-home-notifications
- [E] NN/g, Empty states: nngroup.com/articles/empty-state-interface-design
- [AI] NN/g, Onboarding new AI users: nngroup.com/articles/new-AI-users-onboarding
- [P] ProductLed, the product-led growth engine: productled.com/product-led-growth-engine
- [A] Amplitude community, the four stages of activation (secondary): community.amplitude.com/discussion/12791
