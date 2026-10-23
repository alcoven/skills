# Plans, units and packaging

How to choose what the bill grows with, what goes in each plan, how to present them, and what AI costs change. A worked example ends the page. Sources are listed at the end of [changing-prices.md](changing-prices.md).

## Choosing the unit

The unit (the value metric) is what the bill grows with. Patrick Campbell calls it the most important pricing choice: "If you get everything else wrong, but your value metric is right, you'll be okay" (as reported by Peak XV, 2021).

| Model | Charges for | Fits when | Watch for |
|---|---|---|---|
| Flat | One price for the product | Value is similar across customers, or there is little usage history yet | A large customer pays what a small one pays |
| Per seat | Each person with access | Each person gets their own value from it | Shared logins and capped seats; Campbell advises dropping seats when an added seat brings no value of its own (2020) |
| Per use | A count of what the product does: visits, messages, contacts, calls | Value and cost both follow volume | Bills customers cannot predict; needs alerts and caps |
| Per outcome | A result, such as a resolved conversation | The outcome passes the CAMP test below | Disputes over what counts; Intercom charges $0.99 per "outcome" for its Fin agent and publishes what counts as one (read 2026-10-22) |
| Hybrid | A base subscription plus usage | Most products with AI or heavy usage | Two things to explain; keep the base simple |
| Credits | A pool bought ahead, spent on actions of different cost | Many actions with very different costs | Credits hide the real price; publish what each action costs |

**The market, dated.** In Kyle Poyar's survey of 230 software and AI companies (May 2026), hybrid pricing was the most common model (37%), early-stage companies leaned to flat fees, 29% used AI credits, and 33% planned to add them within a year. In his 2025 survey, 5% said outcome-based pricing was their main model. These figures show what companies chose, and say nothing of what worked for them.

**The CAMP test for outcome pricing** (Poyar, 2025). Charge per outcome only when all four hold: **consistency** (customers value the same outcome), **attribution** (customers credit the product with it), **measurability** (both sides can count it), **predictability** (the customer can budget it).

**How to choose.** List three to five candidates and score each: does it grow with the value; can the customer predict and budget it; can the team count it reliably; does it fit the smallest and the largest customer; does it follow the team's costs? Ask customers which one feels fair (the interview questions in [willingness-to-pay.md](willingness-to-pay.md)); when the true unit is hard to count, use a proxy that moves with it (Campbell, 2020). A warning sign: in 2018 Campbell suggested that a company earning less than 15% of its revenue from existing customers buying more is probably on the wrong unit.

## Leaders, fillers and killers

From *Monetizing Innovation* (Ramanujam and Tacke, 2016), sorted per segment:

- **Leaders:** what the segment buys the product for, with high willingness to pay. Build each plan around one or two.
- **Fillers:** pleasant extras. They round out a plan; never price on them.
- **Killers:** features some customers would refuse to pay for, which can sink a deal when bundled in. Take them out, or sell them as an add-on to those who want them.

Find them from the feature questions in interviews, a most-and-least survey, and usage data (what paying heavy customers use every week).

## Good, better, best

- One plan per segment, named for who it is for. Two or three plans plus add-ons; each extra plan makes the choice harder.
- The same unit across plans; plans differ by leaders and allowances.
- Mark one plan as recommended: the one most new customers should take.
- Each step up adds leaders worth more to its segment than the price gap. Check against that segment's evidence.
- Fences that make sense to the customer: a limit on the unit, a feature only that segment needs, support terms. A limit that only annoys breeds resentment.
- A "talk to us" plan only where a conversation adds value (security reviews, contracts, many locations). Show a "from" price when possible.

## Anchoring, the middle option and decoys, honestly

- **Anchoring:** the first number seen pulls later judgements towards it (Tversky and Kahneman, 1974). On a pricing page, the plans shown and their order set the frame.
- **The middle option:** offered three, people lean towards the middle one (Simonson, 1989). Ramanujam and Tacke list this compromise effect among their behavioural tactics.
- **Decoys:** adding a plan that is plainly worse than another makes that other look better (Huber, Payne and Puto, 1982). Frederick, Lee and Baskin (2014) found the effect often vanishes when options are experienced or shown as people meet them, rather than as tables of numbers. A much-cited pricing story, Dan Ariely's magazine subscription example (*Predictably Irrational*, 2008), was a classroom exercise.

The rule: every plan on the page is real and right for someone. Never add a plan only to push another, and never show a reference price nobody pays. Expect small effects, and test.

## Free plan, free trial or reverse trial

| Option | How it works | Fits when | Risks |
|---|---|---|---|
| Free plan | Free with limits, for as long as people like | Value comes fast, a free customer costs little, and free customers bring others | Many never pay; AI costs make free customers expensive |
| Free trial | The full product for a set time, then pay or stop | Value needs some setting up but shows within the trial | Too short to reach the value; asking for a card up front means fewer start |
| Reverse trial | Paid features for a set time, then the free plan (Elena Verna, 2022) | People should feel the paid plan, and those not ready can stay | More to explain; the free plan must still be useful |
| Paid pilot | A short paid start; Ramanujam advises framing it as building the customer's business case (Lenny's Podcast, July 2025) | Large deals with setup work | Slow |

Choose by three facts: how long until a new customer gets the first value, what a free customer costs a month, and whether free customers bring others. A free plan's limit sits just past the first value, on the unit, and never on a leader the paying segment needs.

## Annual prepay and discounts

- **Annual prepay:** cash up front and fewer moments to cancel, in exchange for a standard discount that is the same for everyone and shown on the page. Keep monthly billing for those who need it.
- **Discounts are a trade:** something in return (a longer term, prepay, volume, a case study, a reference), within written bands, each band with an approver, expiring at signature, recorded in the deals table.
- **The evidence:** in ProfitWell's data (2018, over 6,000 companies), discounted customers cancelled at just over twice the rate of others. Willingness to pay at annual renewal dropped sharply above a 30% discount. Yet most practitioners surveyed thought discounts over 25% were fine. A correlation, and a strong warning.
- **Before cutting a price,** Ramanujam and Tacke ask for three actions that are not about price (the message, the segment, the sales approach).

## AI and other costs that grow with use

1. **Cost per use:** model calls (input and output, at the provider's price), storage and retrieval, any human review, payment fees. Take it from the bill: last month's cost divided by the uses.
2. **Typical and heavy customers:** the cost a month at the plan's allowance and beyond it.
3. **A margin target:** the team's own. In Poyar's 2026 survey, costs and margins were the top factor in pricing AI (54%), the median target gross margin on AI was about 50%, and 12% aimed for 80% or more.
4. **Allowances and limits:** an allowance in each plan, credits or usage above it, and a fair-use limit in plain words saying what happens at it (slows, asks to buy more, stops).
5. **No surprise bills:** alerts before a limit and a spend cap the customer sets. When Cursor changed its usage terms in June 2025 and explained them unclearly, it apologised and refunded unexpected charges in July.
6. **Recheck** when model prices or usage patterns change.

## The pricing page

- Prices shown wherever customers can buy on their own: 61% of 632 business buyers in Gartner's 2025 survey preferred buying without a salesperson, and in Poyar's 2025 survey companies selling self-serve or below $5,000 a year usually published prices.
- One line per plan on who it is for; the recommended plan marked.
- The unit in plain words, what counts as one, and what happens at the limit.
- Monthly and annual prices, with the saving stated truthfully.
- For consumers, the total with tax and every mandatory fee; business prices may show tax apart.
- No struck-through price nobody paid, no countdown that resets, no fee revealed at checkout. How to cancel, stated.
- Answers to the three questions people ask: what if I go over, can I change plans, how do I cancel.

## Currencies, regions and tax

Price the main markets in their own currency, as round local prices, and review when exchange rates move far. Willingness to pay differs by country; a regional price needs a fair fence, such as the billing address. EU VAT on digital services sold to consumers is charged at the customer's country rate and can be declared in one return through the One-Stop Shop, since 1 July 2021; sellers based in the EU below €10,000 of such cross-border sales a year may charge their home VAT (European Commission, VAT One Stop Shop portal). Business customers with a VAT number are usually reverse-charged. US sales tax follows each state's rules. A merchant of record (a reseller that sells in its own name and handles the tax) or a tax tool handles much of this; an accountant confirms it.

## A worked example (invented)

Pinewell sells software to small veterinary clinics: appointment reminders and, since spring, AI visit notes that turn a recorded consultation into the written record. Its one plan, €49 per vet a month, was copied from a competitor at launch two years ago. The founder asks: "Our AI bill keeps growing. Should we raise prices?"

**Step 1, the lever.** The billing export: 180 paying clinics; 6 of the 60 clinics that started between January and June have cancelled. Nobody pushed back on price in the last 30 deals. The model bill divided by September's notes gives €0.06 a note. A busy two-vet clinic writes 1,800 notes a month: €108 of AI against €98 paid. Price is a lever, and the unit is wrong.

**Step 2, the unit.** Candidates: per vet, per clinic, per visit, per note. Part-time vets share logins; value and cost follow visits; clinics budget by the month. Chosen: plans by clinic size, each with an allowance of notes, and packs above it.

**Step 3, the evidence.** Twelve calls (six one-vet clinics, six larger) and the 30 deals. Five of the six larger clinics pay a typist or lose 30 to 45 minutes a day to notes; their acceptable prices ran from €150 to €250 a month. One-vet clinics named €60 to €80. Two clinics said they would never pay for the inventory module: a killer.

**Step 4, the plans.**

| Plan | For | A month, billed monthly | A month, billed yearly | Includes |
|---|---|---|---|---|
| Solo | One-vet clinics | €79 | €69 | Reminders, 300 notes |
| Clinic (recommended) | Two to five vets | €209 | €189 | Reminders, 1,500 notes, two-way texts |
| Group | Several locations | quoted | from €450 | 5,000 notes, location reports, priority support |

Extra notes: €45 for 500 (cost €30). Inventory becomes an add-on. A 14-day trial with every feature, and no free plan, since each free clinic costs real AI money.

**Step 5, the page.** Three plans side by side, monthly and yearly prices, "per clinic, per month", Clinic marked as recommended. Under the table: what counts as a note (the written record of one visit), what happens at the allowance (an offer of a pack; a note is never stopped mid-consultation), and how to cancel.

**Step 6, the test.** From 3 November, new clinics see the new plans. Pass line, read on 16 January with at least 600 pricing-page visitors: revenue per pricing-page visitor at least 30% above September and October's. Guardrails: trial-to-paid no lower than 25% (31% before), and no rise in refunds.

**Step 7, existing clinics.** Only if the test passes on 16 January. The founder decides; the head of support must agree. The ten largest clinics get a call in late January, and every clinic a letter on 1 February. Each keeps its old price for six months (Campbell's legacy discount): monthly clinics move on 1 August and stay on monthly billing, annual ones move at their first renewal after that. The letter is in [changing-prices.md](changing-prices.md).

**Step 8, the review.** The next look is set for November 2027, as a task for the founder, or sooner if the cost of a note moves by a quarter either way.
