# The brief and the watchlist

Two documents carry the watch: the dated brief (one per scan, never edited afterwards) and the watchlist (one living document). Each has its title as the first heading. The example uses an invented company.

## The weekly brief

Every item uses the same five lines, so a reader can scan twenty briefs in a minute.

```markdown
# Market brief, [date]

Window: [last brief's date] to [today]. Time spent: [time]. Sources checked: [n of the list]. Last brief: [address].

## Touches our strategy, positioning or roadmap
- [The one or two items that do, with a link to the item below.] | Nothing this week.

## Items

### [Short title in plain words]
- What happened: [the fact], on [date it happened] ([primary source], read [date]).
- Why it matters to us: [the signal test it passed, and how, in one or two sentences].
- We will: Act: [the proposal, and who decides] | Watch: [what would make it matter; look again on (date)] | Note.
- Confidence: [confirmed at the primary source | unconfirmed], [high / medium / low], because [...].

## What customers said
- [New words, alternatives named, repeated complaints, with where and when.]

## Checked, nothing new
- [Sources looked at that had no change.]

## Could not check
- [Sources you could not open, and why.]

## Proposed changes
Suggestions only; nothing changes without the owner's yes.
1. Consider [a change to a named document], because [the item above]. For [the person who looks after it].
```

Rules for the brief:

- Lead with what touches strategy, positioning or the roadmap. If nothing does, say so; a quiet week is useful news.
- Two dates on every fact. "Read today" never stands in for when it happened.
- Customers before competitors, in reading and in weight.
- Proposals go to the person who looks after the document, as suggestions with their evidence.
- A brief is kept as it was written. Corrections go in the next brief, with the reason.

## The watchlist

```markdown
# Market watchlist

Updated [date]. It serves these questions:
1. [Who our customers are and the job they need done.]
2. [What they use instead of us.]
3. [What our product depends on.]
4. [Which rules apply to us.]

| Item | Why it is here (question) | Sources | Status | Last checked | Retire when |
|---|---|---|---|---|---|
| [A rival, a platform, a rule, a trend] | [Question n: one line] | [Primary pages] | Watch / Act / Note | [date] | [the rule] |

## Retired

| Item | Retired on | Why |
|---|---|---|
| [...] | [date] | [quiet for n scans / no longer touches a question / replaced by ...] |
```

**Statuses.**

| Status | Means | Moves when |
|---|---|---|
| Watch | Could matter; we know what would make it matter | That thing happens (to Act), or it stays quiet past its rule (to Retired) |
| Act | A change is proposed or agreed | The owner decides; then Note or Retired |
| Note | Context worth one line | Something new about it passes a signal test |
| Retired | Off the list, with the reason | A new reason to watch it appears |

**Retire rules.** Give each item one when it is added: "quiet for three months", "after the rule's start date", "once we decide on pricing". At the monthly look back, apply them. Keep the retired list, so an item does not come back without a new reason. Thoughtworks drops radar items that have not moved for about a year (Neal Ford, 2016); a small team's watchlist can be stricter.

## The monthly look back

```markdown
# Market look back, [month]

Briefs read: [addresses]. Deals reviewed: [won n, lost n], if any.

## Came up more than once
- [Item]: [briefs it appeared in], [what it adds up to].

## What we expected, and what happened
- [Item]: we expected [...] on [date]; [what happened].

## Why we won and lost
- [Reason, in buyers' words]: [n buyers], quotes with dates.

## Sources
- Keep: [sources that gave signals]. Drop: [sources that gave only noise].

## For whoever owns the strategy
[One paragraph: what the month means for the strategy, as suggestions.]
```

## Worked example (invented)

Crumb makes an ordering app for small bakeries. Its marketing lead looks after positioning and pricing; its product lead looks after the product and its suppliers. Their watchlist serves four questions: bakeries' order taking, their alternatives (two rival apps, Doughline and Fernbake, plus paper and spreadsheets), what Crumb depends on (a payments provider and an AI model that reads orders from messages), and food-business rules. The marketing lead asks: "What changed this week?"

```markdown
# Market brief, 2026-10-19

Window: 2026-10-12 to 2026-10-19. Time spent: one hour. Sources checked: 11 of 12. Last brief: market/briefs/2026-10-12.md.

## Touches our strategy, positioning or roadmap
- Doughline's free plan (pricing).
- Our order-reading model is being retired (roadmap).

## Items

### Doughline launched a free plan for small bakeries
- What happened: a free plan for up to 50 orders a month, launched 14 Oct (Doughline's pricing page and changelog, read 19 Oct).
- Why it matters to us: it changes the alternatives for our smallest customers, who pay our lowest plan.
- We will: Act: propose that the marketing lead reviews the lowest plan against it; ask this week's two new sign-ups whether they compared.
- Confidence: confirmed at the primary source, high.

### The AI model we use to read orders will be retired
- What happened: the vendor's deprecation page lists the model for retirement on 15 Jan 2027, posted 10 Oct (vendor's deprecation page, read 19 Oct).
- Why it matters to us: it changes what we depend on; reading orders from messages stops working without a change.
- We will: Act: propose that the product lead tests the named replacement on last month's messages before 1 Dec.
- Confidence: confirmed at the primary source, high.

### "Bakeries are moving to subscription bread boxes"
- What happened: a newsletter, 15 Oct, citing a survey by a bread-box company. The survey's page gives no sample or method (read 19 Oct).
- Why it matters to us: it might change how bakeries take orders; it passes no test yet.
- We will: Watch: ask about subscriptions in the next three customer interviews; look again on 16 Nov.
- Confidence: unconfirmed, low.

### Fernbake is hiring account executives for chains
- What happened: two job posts for "multi-site bakery chains", posted 16 Oct (Fernbake's careers page, read 19 Oct).
- Why it matters to us: it may mean Fernbake moves toward chains and away from our customers; no product change yet.
- We will: Watch: check their homepage and changelog for chain features at the November look back.
- Confidence: confirmed that the posts exist; what they mean is a guess, low.

## What customers said
- Three tickets this week about orders that arrive by text and never reach Crumb (support, 13 to 17 Oct). This repeats finding F1 of the October interviews.

## Checked, nothing new
- Fernbake's pricing page; the payments provider's notices; the food standards agency's news page.

## Could not check
- A bakers' forum that needs a member login; nobody on the team is a member.

## Proposed changes
Suggestions only; nothing changes without the owner's yes.
1. Consider reviewing the lowest plan against Doughline's free plan, because of the first item. For the marketing lead (pricing).
2. Consider adding the model replacement to this quarter's roadmap, because of the second item. For the product lead (roadmap).
```

Afterwards the AI updates the watchlist (Doughline to Act, the model to Act, subscriptions added as Watch with "retire if no interview mentions it by 16 Nov"), leaves a note for the marketing lead on the pricing document and one for the product lead on the roadmap, and books the next scan for 26 Oct.
