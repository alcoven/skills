# Alcoven skills

Skills for AI agents, kept by [Alcoven](https://alcoven.co) and free under the MIT licence. Each skill is a folder with a `SKILL.md`: a name, a description of when to use it, then the steps, sometimes with more documents in its folder. They are written in the open Agent Skills format ([agentskills.io](https://agentskills.io)), so the same folder works in Claude Code, Codex, the Claude apps, ChatGPT and other AIs that read the format.

## The skills

| Skill | What it does |
|---|---|
| [ux-designer](ux-designer/) | Designs a feature's user experience before it is built: the job behind the request, how often it comes, every way in, the edge cases and states, then a spec with acceptance checks. |
| [gtm-review](gtm-review/) | Answers "is the plan working?" for a go-to-market plan: each target beside what the team did and the numbers, with the newest date, the gap and what couldn't be counted, every line cited. |

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

OpenAI's help centre lists skills in ChatGPT on the Business, Enterprise, Healthcare and Edu plans (checked 30 September 2026). [Steps to add a skill: check at build against [Skills in ChatGPT](https://help.openai.com/en/articles/20001066-skills-in-chatgpt).]

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
