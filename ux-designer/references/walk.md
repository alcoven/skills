# Walking a journey

A walk checks a design, or the built feature, the way a person in the job's moment meets it. Do it before building (on the spec, step by step, against the product as it is) to find what the design forgot, and after building (in the running product) to check what shipped. It is a cognitive walkthrough with a score, cheap enough to run on every feature.

## How

1. **Give the job a person.** A role, the moment from the spec (what just happened, how much time they have), and the door they use: the app, a phone, their AI assistant, a coding agent, an email link. Walk each door the feature has as its own run.
2. **Walk it as them.** Do only what that person would do, knowing only what they would know. At each step ask the four walkthrough questions:
   - Will they try to do the right thing here (do they know this step is needed)?
   - Will they notice the control, command or tool that does it?
   - Will they connect it with what they want to do (the words match theirs)?
   - After it, will they see that it worked and what comes next?
   A "no" is a finding. For an agent, the questions are the same: will the agent know to call this, will it find the tool among the others, will the name and description match the request, and does the answer tell it what happened and what to do next?
3. **Count and score.**
   - **Steps:** each action by the person or their AI (a click, a field, a command, a tool call), from the trigger to the moment they have what they came for.
   - **Ease,** 1 to 5: 1 stuck, 3 needed thought or a second try, 5 nothing to think about.
   - **Match,** 1 to 5: how close the result came to the job's outcome. A journey can be easy and still not do the job.
4. **Write what held it back,** in one line per finding, with where it happened (the screen, the tool's answer, the file and line when it is code).

## The scorecard

| # | Person and job | Door | Steps | Ease | Match | What held it back |
|---|---|---|---|---|---|---|

Then each journey's steps, numbered, with the findings under it, and a short list of the worst findings across the walk, each with the smallest fix.

## Rules

- Use a test project or test data; never send invitations, emails or messages to real people during a walk, and never change real records.
- Walk what is there. Mark anything you inferred from the code instead of seeing it run.
- A walk finds what the design forgot; people find what the walk can't. When real people are within reach, test in rounds of five (five find about 85% of the problems; three rounds of five beat one of fifteen; three or four per distinct kind of person), and put what they say above what the walk says.
- For an agent door, the walk is a task evaluation: realistic tasks with a checkable result, run several times, transcripts read ([ai-and-agents.md](ai-and-agents.md), "Check the agent's journey").
