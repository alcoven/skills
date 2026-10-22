# Willingness to pay: the evidence and how to gather it

How to find out what customers would pay, from the rough count anyone can make in an hour to surveys and tests. Willingness to pay is the most a customer would pay before choosing the alternative, or nothing. It differs by segment, so every finding names the segment it came from. Sources are listed at the end of [changing-prices.md](changing-prices.md).

## The evidence ladder

Rank every piece of evidence before using it. Higher rungs outweigh lower ones; a decision that is hard to undo needs the upper rungs.

| Rung | What it is | Where it comes from | What it can't show |
|---|---|---|---|
| 1. Paid | What customers paid, kept paying, or stopped paying | Billing records, renewals, cancellations, upgrades | What they would have paid if asked for more |
| 2. Did when offered | What people did when shown a real price | A price test on new customers, quotes in live deals, won and lost deals | Why they did it, without asking |
| 3. Committed | A pre-order, a paid pilot, a signed letter of intent at a stated price | Sales, early access | Whether they renew |
| 4. Said about the past | What they pay today for the alternative, what they compared, who signed off | Interviews | The future |
| 5. Said about the future | "I'd pay 20 a month", a survey answer | Interviews, surveys | Much: people predict kindly and wrongly |

Rob Fitzpatrick's *The Mom Test* (2013) gives the rule for rungs 4 and 5: ask what people did last time, treat predictions of what they would do as weak, and count commitments (money, time, reputation) as the strongest signal.

## The rough count in an hour

For a team with nothing written down.

1. **Export billing.** From the payment provider or the invoices: every charge for the last 12 months with the customer, the plan and the amount.
2. **Count by month** in a spreadsheet, one row per month:

   | month | paying customers | new | cancelled | upgraded | downgraded | revenue | average paid |
   |---|---|---|---|---|---|---|---|

   Average paid is revenue divided by paying customers. Write how each column was counted (for example, "cancelled = last charge in that month and none since").
3. **The last ten deals or sign-ups:** list price, price paid, discount, the plan, and any words about price, from email, chat or sales notes.
4. **Three calls this week,** 15 minutes each, with the questions below: a recent buyer, a lost deal or a customer who cancelled, a long-time customer.

What this shows: whether customers stay, whether discounts are routine, whether larger customers pay more, and the first words customers use about price. What it can't show: a price that would maximise anything. Say both.

## Interviews about price

Talk about willingness to pay early, before the product or the feature is built (Ramanujam and Tacke, *Monetizing Innovation*, 2016). Their order: the problem, the product, its value, and only then price, asking "why?" after each answer. For recruiting, note-taking and synthesis, use the customer-interviews skill if the project has it.

**Who to ask:** recent buyers, lost deals, customers who cancelled, and heavy and light customers. Sort them into segments as you go, and never mix segments in one finding.

**The past and the alternative**
- "Walk me through how you chose [the product or the alternative]. Who was involved? What else did you look at?"
- "What do you spend today on the way you handle this, in money and hours?"
- "Who signs off on a purchase like this? Up to what amount can you buy without asking anyone?"
- "What nearly stopped you buying?" (For a lost deal: "What made the other option win?")

**Value**
- "What would you lose if it went away tomorrow?"
- "What has changed since you started? Do you track it?"

**The unit**
- "When you use it more, what grows: people, visits, documents, locations?"
- "How would you prefer to be billed? What would make a bill hard to budget?"

**Features** (leaders, fillers and killers)
- "Of these, which would you be most unhappy to lose? Which do you never use? Which would you refuse to pay extra for?"

**Price, last** (Ramanujam's three questions, each followed by "Why?")
- "What would be an acceptable price for this?"
- "What would be expensive, though you'd still consider it?"
- "What price would be so expensive you wouldn't consider it?"

**Commitment**
- Where it fits, ask for a step that costs them something: a paid pilot at the proposed price, a pre-order, an introduction to whoever signs.

Write down quotes word for word with the date and the segment. A pitch during the interview spoils the answers that follow it.

## Won and lost deals

A table with one row per deal, won or lost, kept from now on (`pricing/deals.csv`). Use a company name or a code, never a person's name or email.

| Column | What goes in |
|---|---|
| date | The day the deal closed or was lost, YYYY-MM-DD |
| deal | A company name or a code |
| segment | The segment it belongs to |
| plan | The plan quoted or bought |
| list_price | The price before any discount, per month |
| price_paid | What they agreed to pay, per month; empty on a lost deal |
| discount_pct | The discount given, 0 if none |
| outcome | `won` or `lost` |
| reason | One word for the main reason: `price`, `fit`, `timing`, `trust`, `competitor`, `no decision` |
| price_note | What they said about price, in their words |
| owner | The member id of who ran the deal |

The header line: `date,deal,segment,plan,list_price,price_paid,discount_pct,outcome,reason,price_note,owner`. Put a field in double quotes when it holds a comma.

A `.source.md` beside it (`pricing/deals.source.md`) turns it into numbers:

```markdown
# Deals and price notes

- Service: File in the project
- File: pricing/deals.csv
- Days: column date
- Expect: every week
- Owner: m-4f2k9a

## Measures

- won: rows where outcome is won
- lost: rows where outcome is lost
- lost on price: rows where reason is price
- revenue won: column price_paid
- segment: by column segment
- plan: by column plan
```

**Reading it:** the share lost on price by segment (a segment that never loses on price may be underpriced; Patrick Campbell advises pricing research when there is never any pushback, *Yes, and Marketing*, 2021); discounts by deal size and by who ran the deal; the price notes, read in full. "Price" is often the reason given when the value was never clear, so read the note before believing the reason.

## Surveys

Surveys sit on rung 5: they record what people say. Use them for a range and for comparing segments; the exact price needs a test. Say so wherever a number from one is quoted.

### Van Westendorp's price sensitivity meter

Peter van Westendorp presented it at the ESOMAR congress in 1976. Show a clear description of the product and its unit, then ask four questions, each answered with a price:

1. At what price would it be so cheap you'd doubt its quality?
2. At what price would it be a bargain, a good buy?
3. At what price would it start to feel expensive, though you'd still consider it?
4. At what price would it be too expensive to consider?

Plot, for each price, the share of answers calling it too cheap, cheap, expensive and too expensive. The crossings of the curves bound a range of acceptable prices (between the points of marginal cheapness and marginal expensiveness), with two named points inside it. The extension by Newton, Miller and Smith (1993) adds a purchase-likelihood question at the "cheap" and "expensive" prices, which estimates how many would buy and the revenue at each price.

Its limits: it records stated views, and people spend nothing in a survey; it shows no alternatives, though real buyers compare; answers shift with wording and question order; it says nothing of volume or margin. Use it early, one segment at a time, with people who buy this kind of product.

### Gabor-Granger

From André Gabor and Clive Granger's price research in the 1960s. Show one price at a time from a set list and ask whether they would buy at it; move up or down until the answer changes. The share saying yes at each price is a demand curve; price times that share is a revenue curve. Its limits: stated answers, the product shown alone, and the first price shown anchors the rest (randomise where people start).

### Trade-off surveys

Conjoint analysis shows people bundles of features at different prices and infers what each feature is worth from their choices. It handles alternatives better than the two above and needs a specialist tool and a larger sample. A lighter cousin, the most-and-least question ("of these four, which matters most and which least?"), sorts features into leaders, fillers and killers.

## Segments by willingness to pay

Group customers by what they would pay and why: how much they use it, how urgent the need, what they compare it with, how large they are. A segment counts when its members want different things, would pay different amounts, and can be offered a different plan. Each plan needs a fence: something that keeps a segment willing to pay more from buying the cheaper plan (a limit on the unit, a feature only it needs, support, terms). A fence that only annoys (a missing export, a hidden setting) breeds resentment.

## Deciding with little

- **Say the evidence's size:** "4 of 6 clinics with two or more vets named a price above today's (calls, 14 to 20 Oct)". Never round a handful into a percentage.
- **Choose the reversible option:** a change for new customers only, with a date to look again.
- **Set the pass line before,** so the reading cannot be bent after.
- **Start higher when torn,** for new customers: lowering a price is easier than raising one (Ramanujam and Tacke).
- **Price the wait:** if a month of research would not change the decision, decide now and test.
- **Write what would change the decision** ("if more than [n] of the next ten prospects push back on price"), and look again on the date.
