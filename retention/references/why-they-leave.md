# Why customers leave, and how to learn it

Customers leave for a handful of reasons, and each needs a different fix. The work is to put every leaver under one reason, with evidence, and count. This page has the reasons, the evidence and its limits, the questions for calls, the exit survey, and the leaver table.

## The reasons

One code per leaver: the main reason, the one that started it (their first doubt). Others go in the quote.

| Code | In plain words | Evidence that supports it | What usually helps |
|---|---|---|---|
| `no-first-value` | They never got the result they paid for. | Use stops after setup or never starts; "we never got it working"; setup tickets. | Onboarding to first value. |
| `faded` | They got value, then use slowly faded with no clear event. | The core action declined over weeks; "we just stopped using it". | Becoming part of a moment that comes back each week; a check-in when use drops. |
| `need-ended` | The job went away: the business closed, the project ended, the season is over. | They say so; the company closed; nothing replaced it. | A pause or a smaller plan; a win-back when the need returns. |
| `champion-left` | The person who chose it and drove it left or moved on. | Their email bounces or a new contact appears; use dropped after that date. | More than one person set up early; a check-in when a contact changes. |
| `price-value` | The price felt too high for what they got, though they did get something. | They used it, and still name the price; they compared prices. | A plan that fits their use; a cheaper or annual plan (the pricing skill). |
| `switched` | They moved to something that fits them better. | They name the alternative; they exported their data before cancelling. | Learning what the alternative does for them; a product gap, or a clearer "who this is for". |
| `product-gap` | Something failed them: a bug, a missing piece, slow support. | Tickets; a capability they name. | Fix it, or say plainly whom the product is for. |
| `failed-payment` | A charge failed and nothing recovered it. They never chose to leave. | Billing: the last charge failed, and there was no cancel action. | Retries, card updates, emails ([fixes.md](fixes.md)). |
| `unknown` | Not enough evidence yet. | | A call, if they can still be reached. |

Two kinds of leaver need keeping apart: **early** (paid three months or fewer) and **settled** (paid longer). Expect different reasons in each: early leavers tend not to have reached the first value, while settled leavers more often lost a champion, saw their need end, or switched. Count each group on its own and check this in the team's own table.

The growth skill's must-have check asks whether people would miss the product at all. If most leavers are `no-first-value` and stayers are few, the deeper problem may be that few would miss the product: say so and point to that check.

## The evidence, and what each source can carry

| Source | Good for | Limits |
|---|---|---|
| Billing records | Failed payments, when they left, how long they paid. | Nothing about why. |
| Usage before cancelling | Never started, faded, a champion who went quiet. | Shows when and what, rarely why. |
| Support tickets and emails | Reasons in their words; product gaps. | Only from those who write; the angriest are loudest. |
| Exit survey | Many answers for little effort. | Few answer; answers are polite; one tick hides several reasons. |
| Calls | The why, in order, with the moment it turned. | Few; memory fades within weeks; must be soon. |
| Account notes by the team | Context on bigger accounts. | Second hand; the writer's view. |

Code a reason from the strongest source available, and write that source in the row. When sources disagree, the behaviour wins over the tick: a customer who ticked "too expensive" but never used the core action is coded `no-first-value`, with their words kept as the quote ("too expensive for something we never got working").

## Calls with people who left, and people who stay

The customer-interviews skill has the method (consent, recording, notes the same day, reviewing for leading questions). What follows is specific to leaving.

**Who.** Customers who cancelled in the last two to four weeks, a mix of early and settled; and, for comparison, customers who started around the same time and stay. Skip anyone who asked not to be contacted.

**When.** Within days of the cancellation. Weeks later, people remember less and tell a tidier story.

**The ask.** A short note from a real person on the team: "You cancelled last week. Could I ask you about it for fifteen minutes? I want to understand what we got wrong. I won't try to change your mind." Keep that promise: the call is for learning. If they ask to come back, note it and handle it after the call.

**Questions for people who left.** They follow the switch timeline that Bob Moesta and Chris Spiek developed for buying decisions, run in the other direction: the first doubt, the event that made them act, what they compared, the decision, and what they do now.

1. Take me back to when you started. What were you hoping it would do for you?
2. What happened in the first weeks? When, if ever, did it first do that?
3. When did you first think it might not be working out? What was going on then?
4. What did you do after that? Did you try another way or look at anything else?
5. What happened that made you cancel then, and not a month earlier or later?
6. Who else was part of the decision?
7. What do you do now instead?
8. What would have had to be different for you to stay?
9. How did cancelling itself go?

Follow every answer with "tell me more", "when was that?", "what did that cost you?". Listen for the result they wanted and whether they ever got it (Lincoln Murphy's desired outcome: the result, reached in a way that suits them). A feature wish in answer 8 is their guess at a fix: ask what it would have let them do.

**Questions for people who stay.**

1. What were you hoping it would do when you started?
2. When did it first do that? What were you doing that day?
3. What does a normal week with it look like now? When in the week do you use it?
4. Was there a time you nearly stopped? What kept you?
5. If it disappeared tomorrow, what would you do instead?
6. Who else on your team uses it?

Answers 2 and 3 from stayers, set beside answers 2 and 3 from leavers, usually show the moment that keeps people.

## The exit survey

Cheap and useful as one source among several.

- **Optional and out of the way:** one question, shown with or after the confirmation that the cancellation went through, never as a step before it. Laws that require cancelling to be simple ([fixes.md](fixes.md)) count extra steps against the business.
- **Options in customers' words, each mapped to a code:** "We never got it set up" (`no-first-value`); "We stopped needing it" (`need-ended`); "Too expensive for what we got" (`price-value`); "We moved to another tool", with "which one?" (`switched`); "Something didn't work" (`product-gap`); "The person who used it left" (`champion-left`); "Something else".
- **One free-text box:** "Anything you'd want us to know?"
- **Read each answer beside usage** before coding it, and report the response rate: answers from a few stand for a few.

## The leaver table

One row per customer who left, added the week they leave, kept as `retention/leavers.csv`:

| Column | What goes in |
|---|---|
| `date` | The day they cancelled, or the day the last failed charge gave up. YYYY-MM-DD. |
| `customer` | An account id. Never a person's name or email: the table is shared. |
| `months_paid` | Whole months they paid. |
| `stage` | `early` (three months or fewer) or `settled`. |
| `reason` | One code from the table above. |
| `quote` | Their words, exactly, with no name; empty if there are none. |
| `source` | Where the reason came from: `call`, `survey`, `ticket`, `usage`, `billing`, `account-notes`. |

```
date,customer,months_paid,stage,reason,quote,source
2026-09-04,acct-1182,2,early,no-first-value,"We couldn't get the diary to sync, so reminders never went out",call
2026-09-11,acct-0937,14,settled,champion-left,,usage
2026-09-19,acct-1204,1,early,failed-payment,,billing
```

Rules: a field with a comma goes in double quotes; one row per customer even if they wrote ten times; a customer who comes back and leaves again gets a new row; `unknown` stays `unknown` until there is evidence.

Its `retention/leavers.source.md`, so the table becomes numbers:

```markdown
# Customers who left

- Service: File in the project
- File: retention/leavers.csv
- Days: column date
- Expect: every month
- Owner: m-4f2k9a

## Measures

- leavers: rows
- failed payments: rows where reason is failed-payment
- never got started: rows where reason is no-first-value
- reason: by column reason
- stage: by column stage
```

## Reading the table

Each month, and for any fix, count:

- leavers by reason, early and settled apart, with counts ("14 of 38 never got started");
- by money too, when accounts differ in size;
- what is new against last month (a reason rising, a new alternative named);
- two or three quotes per main reason, with their dates.

One customer counts once, however loud. A reason with two leavers is a note for next month; a reason with a third of the leavers is a candidate for the fix.
