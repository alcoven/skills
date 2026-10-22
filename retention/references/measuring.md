# Measuring retention plainly

How to get a rough, honest picture of who keeps paying, from records most teams already have, and how to read it. Use the person's words when you talk; the terms below are for when they will meet them elsewhere.

## The words, in plain language

Say the first column. When the term is needed, give it once with its one-line meaning.

| Say first | The term | In one line |
|---|---|---|
| customers who stop paying | churn (customer or "logo" churn) | Of the customers paying at the start of a period, the share who stopped during it. "Logo" means a customer company. |
| customers who keep paying | retention | The share still paying at the end of the period: 100% minus churn for the same period. |
| the customers who started in the same month | cohort | A group that started together, followed over time. |
| money kept from last year's customers, upgrades left out | gross revenue retention (GRR) | What last year's customers pay now, after downgrades and leavers, divided by what they paid then. At most 100%. |
| money kept from last year's customers, upgrades included | net revenue retention (NRR) | The same with upgrades and add-ons counted, and new customers left out. Above 100% means existing customers pay more in total than a year ago, even after some left. |
| customers paying more, or less | expansion, contraction | Upgrades, more seats, add-ons; or downgrades. |
| customers lost to a failed payment | involuntary churn | They did not choose to leave: a card expired or was declined, and nothing recovered it. |
| the retries and reminders after a failed payment | dunning | Trying the card again and asking the customer to update it. |
| new customers who get to the first real result | activation | The share of new customers who reach the moment that keeps them. |
| how long until that first result | time to first value | Days or hours from paying to the moment. |
| what a customer pays in all the time they stay | lifetime value (LTV) | Roughly, what they pay a month times the months they stay. |
| a score per account guessing who may leave | health score | A mix of signals that a team watches to act early. |

Definitions follow ChartMogul's metric pages (read 2026-10-22); a team may define them differently, so write the team's definition down once and keep it.

## The rough number in an hour, from billing records

Most teams with no retention number have a billing system. Its export is enough.

1. **Export payments** for the last 12 to 18 months: customer id, date, amount, plan, and whether the charge succeeded. If failed charges are a separate export, take both.
2. **Make a grid:** one row per customer, one column per month, the amount paid in that month (blank if nothing). A spreadsheet pivot table does it; above a few hundred customers, a short script. An annual payment counts as paying in each of the twelve months it covers.
3. **Count each month:**
   - paying at start: paid last month;
   - kept: paid last month and this month;
   - left: paid last month, not this month;
   - new: first payment ever this month;
   - came back: paid before, not last month, paid this month.
4. **Mark the failed ones:** for each leaver, did their last charge fail? Those are "left after a failed payment"; the rest "left by choice".
5. **Group by start month** for the cohort table below.
6. **Write the rule you used** at the top (which export, which dates, how annual plans and refunds were counted), so next month's count matches.

For a repeat-purchase business with no subscription (a shop, a refill service), there is no "cancel". Look at customers who ordered at least twice and the time between their first and second orders; take the gap within which most second orders come, and call a customer "still a customer" while their last order is within that gap. Write the gap down with how it was found.

## The month table

| Month | Paying at start | Kept | Left by choice | Left after a failed payment | New | Came back | Paying at end | Share kept |
|---|---|---|---|---|---|---|---|---|
| 2026-08 | 197 | 179 | 12 | 6 | 24 | 0 | 203 | 179 of 197 (91%) |
| 2026-09 | 203 | 183 | 17 | 3 | 21 | 0 | 204 | 183 of 203 (90%) |

Checks: paying at end = kept + new + came back; left by choice + left after a failed payment = paying at start minus kept. Write every share with its counts. When a team has annual and monthly customers, give each its own line too: ChartMogul's 2025 billing report found annual plans keep more customers at every price band, so a change in the mix moves the total with no change in either group.

As `retention/months.csv`, one row a month (`month` is the month's first day):

```
month,paying_at_start,kept,left_chose,left_payment_failed,new,came_back,share_kept
2026-09-01,203,183,17,3,21,0,90
```

And its `retention/months.source.md`:

```markdown
# Customers by month

- Service: File in the project
- File: retention/months.csv
- Days: column month
- Expect: every month
- Owner: m-4f2k9a

## Measures

- paying at start: column paying_at_start, latest
- kept: column kept, latest
- share kept: column share_kept, latest
- left by choice: column left_chose
- left after a failed payment: column left_payment_failed
- new customers: column new
```

## The cohort table

Customers grouped by the month they first paid, and how many still pay in each month after. Counts first, the share in brackets.

| Started | Customers | Month 1 | Month 2 | Month 3 | Month 4 | Month 6 |
|---|---|---|---|---|---|---|
| 2026-03 | 20 | 17 (85%) | 14 (70%) | 13 (65%) | 13 (65%) | 12 (60%) |
| 2026-04 | 21 | 18 (86%) | 15 (71%) | 13 (62%) | 13 (62%) | |
| 2026-05 | 23 | 19 (83%) | 15 (65%) | 14 (61%) | | |

Read it two ways:

- **Along a row:** where does the line stop falling? A curve that flattens says some customers found lasting value; the level where it flattens is what the product keeps. A curve still falling at month six says the leak continues (Sequoia's data science team describes the flattening curve as the sign that some users found value and keep returning).
- **Down a column:** do newer cohorts keep more at the same age? This is where a fix shows. A monthly average cannot show it, because, in Sequoia's words, total retention is the weighted average of the cohorts: one large month of sign-ups moves the total on its own.

For money, build the same table with amounts instead of counts. A row that rises above its first month means the customers who stayed are paying more.

## Money kept, and why both numbers

When customers pay very different amounts, count money as well as customers. Take the customers paying twelve months ago and what they paid then; then what the same customers pay now, without upgrades (gross) and with them (net). Show both:

- Net revenue retention can be above 100% while many small customers leave, if a few large ones upgraded. Gross shows the leak that net hides.
- Counting customers alone can hide that the one account worth twenty small ones left. Show both counts and money when sizes differ.

## A small monthly number adds up

Leaving compounds. "2% a month" sounds small; Recurly's benchmarks page notes it comes to roughly 22% of customers lost in a year. When the person thinks in years, say the year's figure too.

## Early signals: what happens before someone cancels

For the last 20 to 50 leavers, look at the 30 to 90 days before they cancelled: logins, the action that gives the value (orders placed, reminders sent, reports run), how many of their people still used it, support tickets, failed charges. Look at the same window for customers who stayed. The signals that show up often for leavers and rarely for stayers are the team's early warnings. Common ones: the core action stopped while logins went on; the main user went quiet or left; seats in use dropped; a ticket stayed unresolved; nothing after the first week.

Usage tells when and what; it rarely tells why. Pair it with what the customer said ([why-they-leave.md](why-they-leave.md)).

## Health scores and their limits

A health score is a guess until it is checked against who actually left.

- Build it from the two or three signals found above, each checked against past leavers.
- Activity is weak evidence of value: Marley Wagner (ChurnZero blog, August 2026) warns that logins and opens can look healthy while the customer gets little, and that one heavy user can make an account look healthy until that person leaves.
- Include the relationship: has the main contact changed, or gone quiet?
- Give every signal an owner and an action ("usage of the core action halves for three weeks: the account's contact calls within five days"). A score nobody acts on changes nothing.
- Check it each quarter: of accounts marked at risk, how many left; of those who left, how many were marked.

## Benchmarks, with care

A benchmark from other businesses is a weak guide: other prices, customers, markets and years. The team's own earlier cohorts are the baseline. If the person wants a comparison, give one of these with its source, date and what it measured, and say how alike the businesses are.

| Source | What it says |
|---|---|
| Lenny Rachitsky with Casey Winters, "What is good retention?", Lenny's Newsletter, 9 June 2020 | Share still active six months after starting, "good" and "great": consumer subscriptions about 40% and 70% of those who started paying; small and mid-sized business software about 60% and 80% of companies that started paying; enterprise software about 70% and 90%. Net revenue retention at twelve months: enterprise software about 110% and 130%. The post says lower retention can still be fine, for example with very cheap acquisition. |
| ChartMogul, SaaS Billing Report, 18 May 2025 (2024 data, 2,500+ companies) | At $250 to $500 a month per account, median net revenue retention 88% on annual plans against 76% on monthly. Under $25 a month, median customer retention 62% on annual plans against 41% on monthly. |
| Recurly, churn rate benchmarks page, July 2026 network data | Average churn 3.60%, of which 2.34% chose to leave and 1.25% were failed payments: about a third of leaving came from failed payments. |

Vendor figures come from the vendor's own customers, who chose that vendor; say so when you quote them.
