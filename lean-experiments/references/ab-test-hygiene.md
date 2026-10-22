# A/B test hygiene

An A/B test splits people at random between two versions and compares one measure. It is the strongest way to show that a change caused a difference, and the easiest test to get wrong. Kohavi, Tang and Xu put it as "getting numbers is easy; getting numbers you can trust is hard" (2020). Expect flat results: in their book, about a third of ideas tested at Microsoft improved the measure they aimed at, and most big jumps, such as site redesigns, fail. Check surprising results before believing them. Sources at the end.

## Before: is an A/B test the right test?

Kohavi, Tang and Xu list what a useful controlled experiment needs:

- people (or accounts) who can be split without affecting each other;
- enough of them: they recommend thousands at least, and the more there are, the smaller the effect you can detect;
- a measure the team has agreed on, which can be counted reliably;
- a change that is easy to make and undo.

If any is missing, use a test from [assumptions-and-tests.md](assumptions-and-tests.md) instead. They also note that small software products can start early by looking only for big effects.

## Before: write the plan down

1. **One question, one change.** Two changes in one variant leave you unable to say which one worked.
2. **The primary measure:** the one number that decides (Kohavi, Tang and Xu's overall evaluation criterion). Pick it close enough to the change to move, and close enough to the business to matter.
3. **Guardrails:** measures that must not get worse, such as refunds, complaints, unsubscribes, errors, page speed and revenue. Write the line at which you stop the test for harm.
4. **The smallest effect worth acting on** (δ, in the measure's units), taken from the economics: the lift that would pay for the change.
5. **The sample size.** A rule of thumb widely used in A/B testing, from van Belle's *Statistical Rules of Thumb*: about **16σ²/δ² people per variant**, for 80% power at a 5% two-sided significance level. For a rate p, σ² is p × (1 − p). Use a proper calculator for the final number; the rule is for deciding whether the test is possible at all.
6. **The duration:** twice the sample size, divided by the eligible people a week, rounded up to whole weeks so every weekday falls in both arms. If that is longer than the team can wait, don't run it.
7. **The split:** by person (account or device), never by page view, so a person sees the same version every visit.
8. **The stopping rule:** a fixed sample, read once at the end. A sequential method built for repeated looks is fine if the tool implements it properly (Miller, 2010).
9. **A new tool or set-up:** run an A/A test first (two identical arms). It should show no difference; if it shows one, the set-up is broken.
10. **The test card** with the pass line, as in [cards-and-log.md](cards-and-log.md).

Arithmetic from the rule, for a page where 5% of people sign up today (an invented baseline):

| Smallest change worth detecting | δ | People per variant |
|---|---|---|
| 5% to 7.5% | 0.025 | 16 × 0.0475 ÷ 0.025² ≈ 1,216 |
| 5% to 6% | 0.01 | ≈ 7,600 |
| 5% to 5.5% | 0.005 | ≈ 30,400 |
| 5% to 5.25% | 0.0025 | ≈ 121,600 |

Halving the effect you want to detect multiplies the people you need by four. With 1,000 eligible people a week, the second row needs over 15 weeks: too long, so test a bigger change or use another test.

## During

- **Don't peek to decide.** In Evan Miller's example, checking significance repeatedly and stopping at the first significant reading turned a 5% false-positive rate into more than 26%. Watch the guardrails during the run, and read the primary measure once, at the end.
- **Check the split every day.** A sample ratio mismatch (SRM) is a split that differs from the one you set: for a 50/50 test, 600 against 400 people is a strong warning. Test it with a chi-squared goodness-of-fit test; Lukas Vermeer's SRM checker flags a p-value below 0.01. It is common even in mature teams: Microsoft found it in about 6% of experiments, LinkedIn in about 10% of triggered analyses (Vermeer's FAQ, citing Fabijan et al., 2019, and Chen, Liu and Xu, 2018). Causes include redirects, bots and bugs that drop people from one arm.
- **Stop early only for harm:** a guardrail crossing its line.
- **Change nothing midway:** not the split, the change, the audience or the measure. Note incidents with their dates.

## After

1. **SRM first.** If the split is off, the result can't be trusted whatever it shows. Find the cause before reading anything else.
2. **Twyman's law.** Kohavi, Tang and Xu quote it: "Any figure that looks interesting or different is usually wrong." A big win sends you looking for the bug first: logging, bots, a broken control, double counting.
3. **Read against the pass line,** with the difference and its range, not only a p-value. A significant difference too small to matter is no win. A flat result with a wide range means "not shown", and only a narrow range near zero means "no effect worth having".
4. **Guardrails:** did anything get worse?
5. **Novelty and primacy.** Plot the effect by day since each person first saw the change. A lift that fades is novelty; a dip that recovers is people adjusting to change. For big visible changes, Kohavi, Tang and Xu warn that short tests may not show the long-term effect. New and returning people can react differently.
6. **Segments are new beliefs.** A segment that won while the whole didn't is a lead for a new test: slice the data enough ways and some slice wins by chance.
7. **Write the learning card** and the log rows. One failed tactic says little about the strategy behind it; many failed tactics say a lot (Kohavi, Tang and Xu).

## With little traffic

Most early products are here. In order of preference:

1. **Test bigger changes.** Detecting a large effect takes a fraction of the people (see the table).
2. **Measure closer to the change, among those who could see it.** Kohavi, Henne and Sommerfield (2007) show that analysing only people who started checkout, for a checkout change, cuts the noise.
3. **Use a one-arm test with a pass line:** a smoke test, fake door, pre-sale or concierge service, judged against a line set from the economics, with no control group.
4. **Watch a handful of people use it** to find what blocks them.
5. **Treat before-and-after comparisons as weak evidence.** Seasons, campaigns and other changes move the numbers too, and running a small test for months lets more of them in.
6. **Decide on qualitative evidence and say so** in the decision on record, with what would reopen it.

## Sources

- Ron Kohavi, Diane Tang and Ya Xu, *Trustworthy Online Controlled Experiments: A Practical Guide to A/B Testing*, Cambridge University Press, 2020. Chapter 1 (the necessary ingredients, "thousands of experimental units", the Microsoft success rate, Twyman's law, big jumps and primacy effects) read 2026-10-22 at experimentguide.com.
- Ron Kohavi, Randal M. Henne and Dan Sommerfield, "Practical guide to controlled experiments on the web: listen to your customers not to the HiPPO", KDD 2007, read 2026-10-22.
- Ron Kohavi, Alex Deng, Roger Longbotham and Ya Xu, "Seven rules of thumb for web site experimenters", KDD 2014, exp-platform.com/rules-of-thumb, read 2026-10-22.
- Gerald van Belle, *Statistical Rules of Thumb*, 2nd edition, Wiley, 2008 (the 16σ²/δ² rule).
- Jing Zhou, Jiannan Lu and Anas Shallah, "All about sample-size calculations for A/B testing", CIKM 2023, arxiv.org/abs/2305.16459, read 2026-10-22 (the rule as "widely adopted" in industry).
- Evan Miller, "How not to run an A/B test", 18 Apr 2010, evanmiller.org/how-not-to-run-an-ab-test.html, read 2026-10-22.
- Lukas Vermeer, SRM checker FAQ, lukasvermeer.nl/srm/docs/faq, read 2026-10-22; Aleksander Fabijan and others, "Diagnosing sample ratio mismatch in online controlled experiments", KDD 2019.
