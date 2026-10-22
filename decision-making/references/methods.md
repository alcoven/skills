# Decision methods, in more depth

The ideas behind each step, in our own words, with where each comes from. Sources at the end.

## One-way and two-way doors

In his 2015 letter to shareholders, Jeff Bezos split decisions into two types. **Type 1** decisions are consequential and impossible or nearly impossible to reverse (one-way doors); they should be made "methodically, carefully, slowly, with great deliberation and consultation". **Type 2** decisions can be changed (two-way doors) and should be made quickly by individuals or small groups with good judgement. His warning: as organisations grow, they tend to use the heavy Type 1 process for most decisions, which brings slowness, risk aversion and too few experiments.

His 2016 letter adds three points:

- **About 70% of the information you wish you had** is usually enough for most decisions; waiting for 90% is usually too slow. Being good at correcting course makes being wrong cheaper.
- **Disagree and commit.** When there is conviction but no consensus, people can say they disagree and still commit fully. It works upward too: his example is approving a show he doubted, because the team believed in it.
- **Escalate real disagreement early.** Otherwise it is settled by whoever has more stamina.

The reverse error matters for small teams: treating a signed contract, a price for existing customers or a public promise as an experiment.

## Decision quality and outcome quality

Annie Duke (*Thinking in Bets*, 2018) calls judging a decision by its outcome **resulting**. Outcomes mix the quality of the decision with luck and with what nobody could know. To review a decision, ask what was known, what could have been learned at a reasonable cost, and how the choice was made, before looking at how it turned out.

Her later tools (*How to Decide*, 2020; *Quit*, 2022):

- **Map the outcomes.** For each option, list the outcomes that could follow, how much you would like each, and roughly how likely each is. A rough tree beats none.
- **Say probabilities as numbers.** Words like "likely" mean very different things to different people; a number exposes disagreement that words hide.
- **Quarantine opinions.** Ask others for their view before sharing yours, so yours does not colour theirs.
- **Freerolls and close calls.** When the downside is small, decide fast. When two options are close in value, the choice feels hard and matters little: pick one.
- **Kill criteria.** Set in advance a state and a date that will make you stop or change course ("if fewer than 20 bakeries have signed up by 31 March, we pause the delivery feature"). This is the revisit condition in the record.

## Criteria and options

Chip and Dan Heath's *Decisive* (2013) names four traps and a remedy for each, **WRAP**:

| Trap | Remedy |
|---|---|
| Narrow framing: too few options | **Widen your options** |
| Seeking only evidence that agrees | **Reality-test your assumptions** |
| Short-term emotion | **Attain distance** before deciding |
| Overconfidence about the future | **Prepare to be wrong** |

They cite Paul Nutt's studies of organisational decisions, which found that only 29% considered more than one option. Ways to widen: the **vanishing options test** (if none of the current options were possible, what would you do?); running two options at once; a small test first ("ooching"). For distance, Suzy Welch's **10/10/10**: how will we feel about this in ten minutes, ten months, ten years? To prepare to be wrong, set **tripwires**: a date or a signal that forces a fresh look.

## Decision hygiene

Daniel Kahneman, Olivier Sibony and Cass Sunstein (*Noise*, 2021) define noise as unwanted variability in judgements that should be identical. Their **decision hygiene** works without knowing which way the error runs:

- **Independent judgements first, then combine them.** Each person forms and writes a view before hearing others.
- **Sequence information.** Give people the facts they need when they need them, so an early impression does not colour the rest.
- **Break the decision into a few separate assessments** (for a vendor: cost, reliability, fit, exit), judge each on its own facts, and only then make the overall call. With Dan Lovallo, they call this the mediating assessments protocol.
- **Use the outside view** as a shared starting point.

They note that hygiene has costs: scale it to the stakes.

## Group dynamics and roles

Andy Grove (*High Output Management*) gives a model: answer six questions first (what is the decision, by when, who decides, who must be consulted, who approves or vetoes, who must be told), then **free discussion**, a **clear decision**, and **full support** afterwards. He warns of the **peer-group syndrome**: peers hold back until they sense where the group is heading. His fix is a more senior person in the room who steps in when that happens, and reassurance that being overruled costs nothing.

Google's Project Aristotle found that consensus-driven decision making was not significantly connected with team effectiveness. Two common role schemes:

| DACI (Atlassian) | RAPID (Bain) |
|---|---|
| **Driver** runs the process to a decision by an agreed date | **Recommend**: gathers input and proposes |
| **Approver**: the one person who decides | **Agree**: must sign off, used sparingly (legal, budget) |
| **Contributors**: a voice, no vote | **Perform**: carries it out |
| **Informed**: told the outcome | **Input**: gives facts and views |
| | **Decide**: one person, who commits the organisation |

Both insist on a single decider.

## The pre-mortem

Gary Klein (*Harvard Business Review*, September 2007): before committing, the team imagines the plan has already failed and writes down why. It makes doubts safe to say, because everyone is asked for reasons it failed. It rests on "prospective hindsight": research by Deborah Mitchell, Jay Russo and Nancy Pennington (1989) found that imagining an event has already happened helps people explain it more fully. The script is in [record.md](record.md#a-pre-mortem-script).

## The outside view

Dan Lovallo and Daniel Kahneman ("Delusions of Success", *Harvard Business Review*, 2003) describe how planners focus on the case at hand, the inside view, and come out too hopeful. The remedy is the outside view: find a group of similar past cases, see how they went, place your case among them, then adjust for what is truly different. Bent Flyvbjerg developed this into reference class forecasting, and adds that some forecasts are rosy on purpose, to get a project approved.

In a team: "How long did our last three launches take?" "How many pilots like this became paying customers?" Use only real records. When there are none, say the base rate is missing.

## Decision records

Michael Nygard's **architecture decision records** (2011): a short, numbered document per decision with a title, the context (the forces at play), the decision ("We will..."), a status (proposed, accepted, superseded) and the consequences, good and bad. Old records are kept and marked superseded. His reason: without the why, people who come later can only accept a decision blindly or reverse it blindly.

A **decision journal**, advised by Daniel Kahneman and Michael Mauboussin and popularised by Farnam Street, adds what you expect to happen and how sure you are, written before the outcome is known. It protects against hindsight, which rewrites what we thought we knew.

## AI in decisions (2023 to 2026)

Teams now ask AI assistants and agents for options and analyses. The same hygiene applies. An AI's recommendation shown to the room first anchors it, so collect people's views first. Treat an AI's analysis as one input, with its sources checked. An agent never decides: the record names the person who did.

## Common mistakes in depth

| Mistake | Why it hurts | Instead |
|---|---|---|
| No clear decider | Each person thinks someone else will call it; the deadline passes | One named decider (DACI, RAPID, Grove) |
| Waiting for everyone to agree | The slowest holdout sets the pace; consensus showed no link to team effectiveness at Google | Input from all, one decider, disagree and commit (Bezos) |
| Loudest voice or the highest-paid person's opinion | Others hold back what they know (Avinash Kaushik's "HiPPO") | Independent views first; the senior voice last (*Noise*; Duke) |
| Reopening without new evidence | Time goes to old arguments; decisions lose their weight | Cite the record; reopen on named new evidence |
| Nothing written down | Later people accept or reverse it blindly (Nygard) | A short record where the team looks |
| Judging by outcome | Teams copy lucky calls and drop sound ones | Review the decision apart from the outcome (Duke) |
| Two-way door handled as one-way | Slowness and too few experiments (Bezos 2015) | Decide fast; set a date to look again |
| One-way door handled as two-way | A costly call that can't be undone | Full method, or make it reversible first |
| Only two options | Narrow framing hides better choices (Heath; Nutt) | At least three, including waiting |
| Choosing first, then reasons | Criteria bend to fit the favourite | Criteria before options |
| Anchoring the room | The first view heard pulls the rest toward it | Views collected before any recommendation |
| Waiting for complete data | The moment passes; information has a cost | About 70% for two-way doors; cheap tests for one-way doors |

## Sources

All read 2026-10-22.

- Jeff Bezos, 2015 letter to Amazon shareholders (filed with the SEC: sec.gov/Archives/edgar/data/1018724/000119312516530910/d168744dex991.htm) and 2016 letter: aboutamazon.com/news/company-news/2016-letter-to-shareholders.
- Annie Duke, *Thinking in Bets* (2018), *How to Decide* (2020), *Quit* (2022); "Practical Tools for Better Decisions", behavioralscientist.org/practical-tools-for-better-decisions-a-qa-with-annie-duke-on-how-to-decide; on kill criteria, elliotrobia.substack.com/p/kill-criteria; Lenny's Newsletter interview, lennysnewsletter.com/p/making-better-decisions-annie-duke.
- Chip Heath and Dan Heath, *Decisive* (2013); review at lesswrong.com/posts/d67EB6eRZEToAmyqW.
- Daniel Kahneman, Olivier Sibony, Cass R. Sunstein, *Noise: A Flaw in Human Judgment* (2021).
- Gary Klein, "Performing a Project Premortem", *Harvard Business Review*, September 2007: hbr.org/2007/09/performing-a-project-premortem. Mitchell, Russo and Pennington, "Back to the future: Temporal perspective in the explanation of events", *Journal of Behavioral Decision Making* (1989).
- Dan Lovallo and Daniel Kahneman, "Delusions of Success", *Harvard Business Review*, July 2003; Bent Flyvbjerg's comment (arxiv.org/abs/1305.0741).
- Andrew S. Grove, *High Output Management* (1983); summary at shortform.com/blog/managerial-decision-making.
- Atlassian Team Playbook, DACI: atlassian.com/team-playbook/plays/daci. Bain & Company on RAPID decision roles (2023): bain.com/insights/rapid-tool-to-clarify-decision-accountability.
- Michael Nygard, "Documenting Architecture Decisions" (2011): cognitect.com/blog/2011/11/15/documenting-architecture-decisions.
- Farnam Street on the decision journal (2014): fs.blog/2014/02/decision-journal; Alliance for Decision Education on keeping a decision journal: alliancefordecisioneducation.org/resources/keeping-a-decision-journal.
- Google re:Work, team effectiveness guide (Project Aristotle): rework.withgoogle.com/intl/en/guides/understand-team-effectiveness.
- Avinash Kaushik, *Web Analytics 2.0* (2009), on the HiPPO.
