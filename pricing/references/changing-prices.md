# Changing prices: tests, rises and the rules

How to test a new price on new customers, how to raise prices for existing customers, the laws and fair dealing that apply, the templates, and the sources for the whole skill.

## Testing a price on new customers

Existing customers keep their price while a test runs. Choose the fairest design the numbers allow.

| Design | How it works | Good for | Weakness |
|---|---|---|---|
| Before and after | New sign-ups from a set date see the new price; compare with the same weeks before | Self-serve products with steady sign-ups | Seasons, campaigns and releases blur it: note each one |
| A new plan beside the old | Add a plan or an add-on at the new price | A new tier, a new unit | Splits the choice; not a pure price reading |
| The next ten prospects | Sales quotes the new price to the next qualified prospects | Business sales with few deals | Small numbers: read deal by deal, with the notes |
| A new market or segment | Launch the new price where the product is new | A new country or customer type | The markets differ in more than price |
| A split test at the same time | Visitors are shown different prices at random | Large traffic, and only with care | People compare. Amazon's random DVD price test (2000) ended in an apology and refunds, and Amazon said any future test would give every buyer the lowest test price. Do the same |
| A fake door | Show a new plan, count the clicks, and say plainly it isn't available yet | Interest in a plan before building it | Clicks aren't payments; never take money for what won't come |

**The main measure:** revenue per visitor (self-serve) or per qualified prospect (sales). It counts price and conversion together, so a higher price that loses too many buyers shows up as a loss. **Guardrails:** trial-to-paid conversion, cancellations in the first 60 days, refunds, discount requests, support tickets about price. Set the pass line, the least number of people and the reading date before the start, and never move them after seeing the data. For reading a result honestly (seasons, small numbers, what else changed), use the metrics skill if the project has it.

### The test card

```markdown
# Price test: [the change in a few words]

- Status: planned
- Owner: [member id]
- Who sees it: [new sign-ups from date | the next ten qualified prospects | ...]
- The change: [old plan and price] to [new plan and price]
- Main measure: [revenue per visitor or per qualified prospect]; baseline [value, period, source]
- Pass line: [the result that counts as a win], with at least [n] [trials | prospects], read on [date]
- Guardrails: [conversion no lower than x; early cancellations; refunds]
- Stop early if: [a guardrail broken, by how much]
- If it passes: [what we do]. If it fails: [what we do]
- Stands on: [§ addresses or files, with their dates]

## Result (written on the reading date)

- The reading against the pass line, with the counts
- What else happened in the period: campaigns, releases, holidays, outages
- Decision: keep, change or roll back; who decided, on what date
```

## Raising prices for existing customers

### Decide first

A rise for existing customers is a one-way door: it can be reversed only at a cost to trust. Name the decider (whoever owns revenue), who must agree (finance, the sales lead, the support lead who will answer the replies), and who must know (everyone who talks to customers). Record the decision with the decision-making skill if the project has it: the reason, the evidence, who moves when, and what would make the team look again.

### Prepare

- **Contracts and terms:** can the price change mid-term, and with what notice? Annual contracts usually change at renewal.
- **The law** where customers live (below), and the app stores' own rules for raising subscription prices.
- **The billing system:** can it hold a customer's old price for a set time and schedule the change?
- **Who moves when:** a legacy period on the old price for everyone, longer for long-standing customers if the team chooses. Campbell's default is a set legacy period (six months in his example), and he argues against keeping old prices indefinitely (Peak XV, 2021). Keeping old prices forever avoids a hard conversation now, but leaves the oldest customers on prices the team cannot sustain.
- **Calls before letters** for the largest accounts and for anyone facing a large rise; Campbell suggests a call for rises above 50% (Peak XV, 2021).
- **A way down:** a smaller plan for customers who can't pay more, so they can stay.
- **Support:** a reply script, answers to the likely questions, and a written rule for who may grant an exception.

### Notice

At least what the contract and the law require. In business sales, leave enough time for the customer's budget cycle; for annual customers, tell them before their renewal decision. Campbell advises letting a clearly labelled invoice mark the day the new price starts (*Yes, and Marketing*, 2021). Follow the law where it asks for a reminder, and send one anyway when the change is large.

### The message

Campbell's five parts (*Yes, and Marketing*, 2021): the value delivered, in the customer's own numbers; what they asked for that has shipped; the rise tied to what it pays for; the legacy period; and a closing offer of help for anyone it would hurt. An example in the Pinewell case from [plans-and-packaging.md](plans-and-packaging.md), addressed to the customer:

```text
Subject: Your Pinewell plan from 1 August

Hi [first name],

Since [Harbour Vets] joined in [March 2025], Pinewell has sent
[14,200] appointment reminders and written [6,300] visit notes for
your team. Two things you asked for are now live: two-way texts and
notes in Spanish.

Our plans are changing. From 1 August, [Harbour Vets] moves to Clinic:
EUR 209 a month, billed monthly as today (EUR 189 a month if you
switch to yearly), with 1,500 visit notes a month. You pay [EUR 147]
a month today, and nothing changes until 1 August.

Why: every visit note costs us to write, and clinics now use notes far
more than we planned. The new plans let us keep improving them.

Your options:
- Do nothing: you move to Clinic on 1 August, still billed monthly.
- Switch to Solo (EUR 79 a month, 300 notes) if it fits you better.
- Cancel at any time in Settings, or reply to this email.

If the new price is hard for the clinic right now, reply and tell us.
Our head of support reads every reply.

[the founder's name]
Founder, Pinewell
```

### After the letter

Answer every reply the same working day. For 90 days, watch cancellations, downgrades, replies and price tickets by segment, against the same months before, and what existing customers now pay in total against before. Campbell observes that some customers cancel after any price change, and that cancellations can later fall below their earlier level once those already on the fence have gone (*Yes, and Marketing*, 2021): one practitioner's observation, to check against the team's own numbers. Write the result into the decision record.

## The law and fair dealing

As read on 22 October 2026. This names rules that may apply and is not legal advice; a lawyer should check terms and notices.

- **United States.** The FTC's Rule on Unfair or Deceptive Fees (16 CFR Part 464, in force since 12 May 2025) requires the total price up front, mandatory fees included. It covers live-event tickets and short-term lodging only. Misleading prices elsewhere still fall under Section 5 of the FTC Act. The FTC's 2024 "click to cancel" rule was struck down by the Eighth Circuit on 8 July 2025, before it took effect. The FTC restarted the rulemaking with an advance notice published on 13 March 2026, with no draft rule yet (Covington, March 2026). The Restore Online Shoppers' Confidence Act and state automatic-renewal laws still apply. California's, as amended by AB 2863 for contracts from 1 July 2025, requires clear notice of material changes, price included. It also covers free trials.
- **European Union.** An announced price reduction must show the prior price, the lowest charged in at least the 30 days before it (Article 6a of the Price Indication Directive, added by Directive (EU) 2019/2161), and the Court of Justice held in case C-330/23 (26 September 2024) that the percentage itself must be measured from that prior price. Consumers must be shown the total price with taxes, and any extra payment needs their express consent: a pre-ticked box does not count (Consumer Rights Directive 2011/83/EU, Article 22). A Digital Fairness Act covering dark patterns, unfair pricing and unfair personalisation is announced for the last quarter of 2026 and was not yet proposed on 20 September 2026 (European Parliament's Legislative Train).
- **United Kingdom.** The Digital Markets, Competition and Consumers Act 2024 has governed unfair practices since April 2025. The CMA's price transparency guidance (18 November 2025) treats drip pricing (mandatory charges added as the purchase goes on) and partitioned pricing (parts with no total) as prohibited under section 230. The Act's subscription rules are not yet in force (read 22 October 2026).

**Fair dealing, wherever the law stands:** no cost revealed only at checkout; no "was" price nobody paid; no countdown that resets; no pre-ticked extras; no trial that turns paid without a clear reminder; cancelling as easy as buying; no guilt-laden "No, I don't want to save money" buttons; no price set on personal data the customer doesn't know is used.

## The pricing document

```markdown
# Pricing

- Owner: [member id]
- Decided by: [member id], [date]; decision record: [link]
- Next review: [date]

## What customers get
[Per segment, in their words, with sources and dates.]

## The unit
[The unit and why it beat the others.]

## Plans
| Plan | For | Price | Includes | Limits |
|---|---|---|---|---|

## Evidence
[Willingness to pay per segment: the range, the rung of evidence, the source, the date.]

## Costs
[Cost per use for typical and heavy customers; the margin target; read on what date.]

## Rules
- Discounts: [bands, approvers, what is asked in return]
- Annual prepay: [the discount]
- Exceptions: [who may grant what]

## Changes
| Date | What changed | Why | Decided by |
|---|---|---|---|
```

## Sources

All read on 2026-10-22.

- Madhavan Ramanujam and Georg Tacke, *Monetizing Innovation: How Smart Companies Design the Product around the Price*, Wiley, 2016; chapter notes at grahammann.net/book-notes/monetizing-innovation-georg-tacke-madhavan-ramanujam and ybrikman.com/blog/2023/04/01/monetizing-innovation
- Madhavan Ramanujam and Eddie Hartman, *Scaling Innovation: How Smart Companies Architect Profitable Growth*, Wiley, 2025.
- Lenny Rachitsky with Madhavan Ramanujam, "Pricing your AI product: lessons from 400+ companies and 50 unicorns", Lenny's Podcast, 27 July 2025. lennysnewsletter.com/p/pricing-and-scaling-your-ai-product-madhavan-ramanujam
- Patrick Campbell, "How to Price a SaaS Offer" (value metrics) and "How Discounts Impact Retention", ProfitWell Report, both 4 April 2018, now at paddle.com/studios/shows/profitwell-report (read from archived copies).
- Patrick Campbell, guest post on SaaS pricing strategy, Lenny's Newsletter, 27 October 2020. lennysnewsletter.com/p/saas-pricing-strategy
- Peak XV, "Setting the right price, then changing it, is the path to revenue growth" (Campbell at Surge), 5 October 2021. peakxv.com
- Verblio, summary of *Yes, and Marketing* episode 81 with Patrick Campbell, 3 November 2021. verblio.com/blog/patrick-campbell-episode-summary
- Kyle Poyar, "2025 State of B2B Monetization", Growth Unhinged, 4 June 2025. growthunhinged.com/p/2025-state-of-b2b-monetization
- Kyle Poyar, "The state of B2B monetization in 2026", Growth Unhinged, 13 May 2026. growthunhinged.com/p/the-state-of-b2b-monetization-in-2026
- Peter van Westendorp, "NSS Price Sensitivity Meter: a new approach to study consumer perception of prices", Proceedings of the 29th ESOMAR Congress, 1976; and D. Newton, J. Miller and P. Smith, "A market acceptance extension to traditional price sensitivity measurement", AMA Advanced Research Techniques Forum, 1993; both as cited by the pricesensitivitymeter package, cran.r-project.org/package=pricesensitivitymeter
- André Gabor and Clive Granger, "On the price consciousness of consumers", Journal of the Royal Statistical Society Series C, 1961, and their later price studies.
- Rob Fitzpatrick, *The Mom Test*, 2013.
- Amos Tversky and Daniel Kahneman, "Judgment under uncertainty: heuristics and biases", Science, 1974.
- Joel Huber, John Payne and Christopher Puto, "Adding asymmetrically dominated alternatives", Journal of Consumer Research, 1982.
- Itamar Simonson, "Choice based on reasons: the case of attraction and compromise effects", Journal of Consumer Research, 1989.
- Shane Frederick, Leonard Lee and Ernest Baskin, "The limits of attraction", Journal of Marketing Research, August 2014. marketing.wharton.upenn.edu/wp-content/uploads/2016/10/The-Limits-of-Attraction.pdf
- Dan Ariely, *Predictably Irrational*, HarperCollins, 2008.
- Elena Verna, "Reverse trial", Amplitude blog, 7 September 2022. amplitude.com/blog/reverse-trial
- Gartner, "Gartner Sales Survey Finds 61% of B2B Buyers Prefer a Rep-Free Buying Experience", 25 June 2025. gartner.com/en/newsroom
- Intercom, pricing page (Fin AI agent). intercom.com/pricing
- Cursor, "Clarifying our pricing", 4 July 2025 (cursor.com/blog); TechCrunch, "Cursor apologizes for unclear pricing changes that upset users", 7 July 2025.
- Amazon.com, "Amazon.com issues statement regarding random price testing", 27 September 2000. press.aboutamazon.com
- US Federal Trade Commission, Rule on Unfair or Deceptive Fees (16 CFR Part 464) and its FAQ. ftc.gov
- Latham & Watkins, "Eighth Circuit vacates FTC click-to-cancel rule days before compliance deadline", July 2025. lw.com
- Covington, "FTC launches new rulemaking on the negative option rule", March 2026. cov.com
- Kilpatrick Townsend, "California's latest automatic renewal law amendments take effect in July 2025", October 2024. ktslaw.com
- Directive 98/6/EC, Article 6a (added by Directive (EU) 2019/2161); Court of Justice, case C-330/23, 26 September 2024 (summary by Baker McKenzie, October 2024).
- Directive 2011/83/EU (Consumer Rights Directive), Article 22.
- European Commission, VAT One Stop Shop portal. vat-one-stop-shop.ec.europa.eu
- European Parliament, Legislative Train, "Digital Fairness Act", updated 20 September 2026. europarl.europa.eu/legislative-train
- UK Competition and Markets Authority, guidance on the price transparency provisions of the DMCC Act 2024, 18 November 2025 (summary by Osborne Clarke).
