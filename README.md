# Alcoven skills

Skills for AI agents, kept by [Alcoven](https://alcoven.co) and free under the MIT licence. Each skill is a folder with a `SKILL.md`: a name, a description of when to use it, then the steps, sometimes with more documents in its folder. They are written in the open Agent Skills format ([agentskills.io](https://agentskills.io)), so the same folder works in Claude Code, Codex, the Claude apps, ChatGPT and other AIs that read the format.

## The skills

Each skill does the work it is asked for, and checks on the way that it is the right work: the evidence behind it, the mistakes teams commonly make at that step, and a record someone can find later. It says a concern once, with the cheapest way to check it, and the person decides. Not sure which one fits? Start with `product-coach`.

The methods come from the people who wrote them down, among them Marty Cagan, Teresa Torres, Eric Ries, April Dunford, Sean Ellis and Morgan Brown, Rob Fitzpatrick, Richard Rumelt, Andy Grove and Kim Scott. Each skill's `references/` names its sources, with the date they were read.

### Product and planning

| Skill | What it does |
|---|---|
| [product-coach](product-coach/) | Starts a broad or vague ask ("how can we make more money?", "sales are bad") with a plain-words diagnosis of where the money or the customers are lost, and checks a proposed piece of work before a team commits time: the problem, the outcome, the evidence, the riskiest assumption and the cheapest check. Then it hands over to the skill that fits. |
| [product-strategy](product-strategy/) | Writes or reviews a strategy (the diagnosis, the approach, the few actions, what you will not do), sets one to three measured outcomes and a now, next, later roadmap, and checks new work against it. |
| [product-discovery](product-discovery/) | Decides what is worth building before it is built: the problem behind a request, several ideas compared, and the riskiest assumptions tested in days. |
| [lean-experiments](lean-experiments/) | Tests the assumption that would sink a plan with the smallest test that gives a real answer and a pass line written first, then frames the call to persevere, pivot or stop. |
| [metrics](metrics/) | Picks a north star, inputs and guardrails, defines each in writing, and reads a dashboard or a change honestly before the team decides. |
| [decision-making](decision-making/) | Sizes a decision by how hard it is to undo, scales the process to it, names one decider, and writes the decision record for the team to agree to. |

### Design and research

| Skill | What it does |
|---|---|
| [ux-designer](ux-designer/) | Designs a feature's user experience before it is built: the job behind the request, how often it comes, every way in, the edge cases and states, then a spec with acceptance checks. |
| [customer-interviews](customer-interviews/) | Picks who to talk to, writes the guide for the decision at hand, checks notes for leading questions and opinions, and turns several interviews into findings with counts and dated quotes. |
| [market-watch](market-watch/) | A weekly scan of customers' words, competitors, the platforms you depend on and the rules, written as a dated brief that says what each change means for the team. |

### Marketing and sales

| Skill | What it does |
|---|---|
| [positioning](positioning/) | Works out positioning from customer evidence with April Dunford's method, writes a one-page canvas, and checks the homepage, pitch and ads against it. |
| [growth](growth/) | Checks that customers would miss the product before growing it, then sets a north star and a growth model and runs a weekly test cycle the team learns from. |
| [gtm-plan](gtm-plan/) | Writes a go-to-market plan for winning the first customers: who to sell to first, a few channels to test cheaply, founder-led sales when the product needs selling, targets with dates and a record of what each brings. |
| [gtm-review](gtm-review/) | Answers "is the plan working?" for a go-to-market plan: each target beside what the team did and the numbers, with the newest date, the gap and what couldn't be counted, every line cited. |
| [retention](retention/) | Finds why paying customers leave, from billing records and what the leavers say, picks the one fix likely to keep the most of them, and sets up a monthly look at who left and why. |
| [pricing](pricing/) | Sets prices and plans from evidence of what customers pay, tests changes on new customers first, and plans a price rise for existing customers fairly. |
| [seo](seo/) | Audits a site for search (can it be crawled, indexed and read, does each page answer what people search), plans pages from search demand and customers' words, and measures the change honestly. |
| [ai-visibility](ai-visibility/) | Asks AI engines the questions buyers ask, week after week, records who is named and which pages are cited, checks that AI crawlers can read the site, and plans how to earn a place in the answers. |
| [youtube-expert](youtube-expert/) | Picks video topics from measured evidence, shapes the title, thumbnail and first seconds, reviews scripts and cuts against a dated playbook, and reads the numbers afterwards. |

### Legal and people

| Skill | What it does |
|---|---|
| [people-manager](people-manager/) | Prepares 1:1s, writes feedback and delegation briefs, runs team meetings and retros, and spots overload in the project's record without ranking anyone. |

Each skill also has a page at `alcoven.co/skills/<name>`, with its full text and its versions.

## Use a skill in your AI

### With one command

[`npx skills`](https://github.com/vercel-labs/skills) installs a skill for coding agents such as Claude Code and Codex:

```
npx skills add alcoven/skills --skill ux-designer
```

Add `-a claude-code` or `-a codex` to install it for one agent, and `-g` to have it in every project on your computer. `npx skills check` and `npx skills update` find and install newer versions.

### Claude Code

Copy the skill's folder into `.claude/skills/` in a repository (commit it, and everyone who works there has it), or into `~/.claude/skills/` for every project on your computer. Claude Code reads each skill's description and uses the skill when a request fits it. To choose it yourself, type its name: `/ux-designer`.

### Codex

Copy the skill's folder into `.agents/skills/` in a repository, or into `~/.agents/skills/` for every project on your computer. Codex uses the skill when a request fits it. To choose it yourself, mention it: `$ux-designer`. Restart Codex if a new skill doesn't show.

### Claude (the apps)

1. Turn on code execution and file creation in Settings > Capabilities. On Team and Enterprise, an owner turns it on for the organisation.
2. Zip the skill's folder, so the zip holds `ux-designer/` with its `SKILL.md`.
3. Go to Customize > Skills, click +, then Create skill, then Upload a skill, and choose the zip.
4. Turn the skill on in your list.

Skills are on every Claude plan, Free included. On Team and Enterprise you can share a skill with colleagues who use Claude (view-only), or publish it to your organisation. Anthropic's help centre has the steps: [Use skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

### ChatGPT

OpenAI's help centre describes skills in ChatGPT: [Skills in ChatGPT](https://help.openai.com/en/articles/20001066-skills-in-chatgpt). Which plans have them, and how to add one, are on that page.

### Any other AI

Paste the skill's `SKILL.md` into the conversation, then the documents it points to when the AI asks for them.

## For a team: add it to an Alcoven project

Installed this way, a skill stays where you put it: in a folder on one computer or in one repository, or in one person's account in one AI app. Claude's Team and Enterprise plans share skills across an organisation, with colleagues who use Claude. An Alcoven project gives a skill to the AI each person on it uses: the agent in Alcoven; Claude, or ChatGPT on plans that let you add an MCP server, when they open the project there; and Claude Code or Codex in the project's folder. Change the skill once in the project, and every one of those AIs is given the new version. When Alcoven changes a skill, your project is offered the new version with what changed, and you decide what to keep where it meets your own changes.

Add one to a project from its page: [alcoven.co/skills](https://alcoven.co/skills).

## Versions

Each skill's version is in its `SKILL.md` (`metadata`, `version`) and in [`catalog.json`](catalog.json), with a line on what changed in each version. `catalog.json` also holds each skill's short title (45 characters at most, the title of its page), its one-line summary, its category, and the words and folder names that lead Alcoven to suggest it to a project, in English and Turkish.

## Problems and your own skills

To report a problem with a skill, open an issue on this repository, or use Report this skill on its page. Wrote a skill that works? Publish it from your project in Alcoven: Alcoven reads it first, then anyone can add it to a project or install it in their own AI.

## Licence

MIT: anyone may use, copy, change, share and sell these skills, as long as the copyright notice and the licence text stay with them. See [LICENSE](LICENSE).
