# The plan, its records, an example, and the sources

The plan is short enough to read in five minutes and run every week. It has the shape the gtm-review skill reads: engines, each with a target number and a date, and a record kept as a table with a date on every row. Keep it as `gtm/readme.md` unless the project has another place for it.

## The template

```markdown
# Go-to-market plan, [first day] to [last day]

- Owner: [member id]. Agreed by [who], [date].
- Goal: [new customers or revenue] by [date] ([where the goal comes from]).
- Reviews: first on [date], then [every week | every 2 weeks | every month].

## Who we sell to first

[The segment in one line, the reason they buy, how we reach them.]
Signs: [the ICP as signs anyone can check].
Not now: [who waits, and when we look again].
Evidence: [the customer count and the calls, with dates and grades].

## How we sell

[The motion now and later; the price; who signs at the customer.]

## Engine: [its name, in the team's words]

- Target: [n] [what is counted] by [date].
- Target: [n] [the result it should bring] by [date].
- Weekly: [the actions, with how many], by [member id].
- Record: [path to the table], one row per [thing that happened], with its date; new rows every week; kept by [member id].
- Test: [pass line, set on date], read on [date]; then focus or drop.

[A widget line for each target]

## Not this period

[Channels, segments and pushes the team chose not to do now, and why.]

## Assumed

[Each line that rests on a guess, and what would confirm it.]
```

Rules for the plan:

- **Every target is a number and a date.** "Grow outreach" is a wish; "60 first messages by 2026-12-31" can be reviewed. A target with no date gets one, or the review says "the plan sets no date".
- **Two kinds of target per engine where possible:** what the team does (messages sent, talks given), which it controls, and what that should bring (calls, customers), which it doesn't. When results lag, the review can see whether the work happened.
- **Every engine has one record,** a table with one row per thing that happened, with the day it happened. A target nothing counts is a hope.
- **Every engine and every weekly action has one owner,** by member id.
- **Three engines at most** for a small team, including the tests.
- **"Not this period" is part of the plan.** It is where the ads, the second segment and the big launch wait, with a reason, so they aren't re-argued every week.

## Setting the targets

Work back from the goal through the team's own rates. If September's records show 20 first messages, 5 replies, 3 calls and 1 customer, those are the team's rates for now, from few rows: say so. The goal divided through them gives the work each engine needs, and the hours it takes. When the hours aren't there, split the goal across engines or move the date; never quietly lower the work and keep the goal.

With no records yet, set the activity targets the team can keep (as many messages a week as the founder can write well), mark the result targets as first guesses, and reset them at the first review with the real rates. Never use another company's or an industry's rates as the team's own.

## The records and the widgets

The outreach log from [founder-led-sales.md](founder-led-sales.md) (`date,organisation,contact,channel,what,by,note`) becomes numbers with a source file beside it, `gtm/outreach.source.md`:

```markdown
# Outreach to sports clinics

- Service: File in the project
- File: gtm/outreach.csv
- Days: column date
- Expect: every week
- Owner: m-3d8f1a

## Measures

- first messages: rows where what is first message
- replies: rows where what is reply
- calls: rows where what is call
- clinics won: rows where what is won
- channel: by column channel
```

Each `rows where` line counts one column holding one value. When an engine needs a count across two columns, give it its own table. Other engines keep the same shape: one row per thing, a date, a `what` column (a talk's table might hold `talk given`, `sign-up`, `call`; an introductions table `asked`, `introduced`, `call`, `won`).

A widget per target, `gtm/first-messages.widget.md`:

```markdown
# First messages to sports clinics

- Show: line
- Measure: first messages
- From: gtm/outreach.source.md
- By: week
- Since: 2026-10-26
- Compare: target 60 by 2026-12-31

Why it's here: the outreach engine's activity target (gtm/readme.md, "Engine: outreach to sports clinics").
```

In the plan, a widget line is a link on a line of its own, `[First messages to sports clinics](first-messages.widget.md)`, under its engine. Alcoven draws it there, and an AI reading the plan gets the reading in its place: the count, the gap, the days left and the newest row's date. A project's home holds four widgets; give the goal and the engine most at risk `- On home: yes`.

## A worked example (invented)

Tallyroom sends physiotherapy patients their home exercises and shows the clinic who did them. Two founders: one (m-3d8f1a), a former physio, sells; the other (m-7k2p4c) builds. On 22 October 2026 they have 14 paying clinics at $60 a month each, and say "we need more customers".

**The count** (from first emails and the memory of the founder who sells, 21 Oct; three calls, 14 to 17 Oct):

| First heard | Clinics | Best fit |
|---|---|---|
| Former colleagues of the founder who sells | 7 | 2 |
| A talk at a regional physio association evening | 3 | 2 |
| A post in a sports physio group | 2 | 1 |
| Messages from the founder who sells in September (20 sent) | 1 | 1 |
| Search | 1 | 0 |

All six best-fit clinics are sports physiotherapy clinics with three to eight physios; the two clinics that cancelled were solo practitioners. Ten used paper sheets or a PDF by email before. On the calls, owners said they started looking after a patient lost the sheet, and that owners compare tools at association evenings and in one group.

**Segment:** sports physiotherapy clinics with three to eight physios, where the owner still treats patients. Not now: solo practitioners and hospital departments; look again in January. Evidence: strong (the count and three calls), on 14 clinics.

**Motion:** founder-led now; a self-serve trial later, once setup needs no call. Channel-model check: September's outreach took the founder who sells about 9 hours per clinic won (one clinic, from few rows). At the $50 an hour the founders set for their time, that is $450 against $720 a year from a clinic: earned back within the year. How long clinics stay is unknown (nine months of data).

**Working back:** 11 new clinics by 31 December. At September's rate (one clinic from 20 messages) outreach alone would need about 220 messages, near 100 hours the founder who sells doesn't have, so the goal is split across three engines.

**Bullseye:** an idea for each of the 19 channels; three kept: personal outreach (sales), talks at association evenings (speaking engagements), and introductions from customers. Later: a page on home exercise programmes (seo), a listing in a physio software directory. Not this period: ads, a launch on a launch site.

The plan, in short:

```markdown
# Go-to-market plan, 26 Oct to 31 Dec 2026

- Owner: m-3d8f1a. Agreed by m-3d8f1a and m-7k2p4c, 23 Oct 2026.
- Goal: 11 new paying clinics by 2026-12-31, reaching 25 (the founders, 21 Oct).
- Reviews: first on 2026-11-05, then every 2 weeks.

## Engine: outreach to sports clinics

- Target: 60 first messages by 2026-12-31.
- Target: 12 calls held by 2026-12-31 (a first guess from September's 20 messages).
- Weekly: 6 first messages on Mondays and the sales hour on Thursdays, by m-3d8f1a.
- Record: gtm/outreach.csv, one row per message, reply or call; new rows every week; kept by m-3d8f1a.
- Test: at least 3 calls from the first 20 messages, read on 2026-11-16; then focus or drop.

[First messages to sports clinics](first-messages.widget.md)
[Calls held](calls.widget.md)

## Engine: talks at association evenings

- Target: 3 talks given by 2026-12-31.
- Target: 6 clinics starting a trial after a talk by 2026-12-31 (a first guess from one evening).
- Weekly: m-7k2p4c has the demo clinic ready by 2026-11-05; m-3d8f1a writes to two association organisers a week until three talks are booked.
- Record: gtm/talks.csv; kept by m-3d8f1a.

## Engine: introductions from customers

- Target: all 14 clinics asked for one introduction by 2026-11-15.
- Target: 5 introductions by 2026-12-31.
- Weekly: 3 customers asked at their check-in call, by m-7k2p4c.
- Record: gtm/introductions.csv; kept by m-7k2p4c.

## Not this period

Ads, a launch on a launch site, solo practitioners, the self-serve trial.

## Assumed

The rates come from 20 messages and one evening; the first review resets the result targets.
```

In Alcoven, the founders hand each engine's section to its owner to agree, add a task per weekly action, add rows to the tables as things happen, and put "New paying clinics" (the goal, counted from `gtm/customers.csv`, one row per clinic that starts, with `- Compare: target 11 by 2026-12-31`) and "First messages" on the home. On 5 November the gtm-review skill reads the plan, the tables and the widgets.

## Sources

All read 2026-10-22.

- Geoffrey A. Moore, *Crossing the Chasm*, 3rd edition, HarperBusiness, 2014 (first edition 1991); book notes at grahammann.net/book-notes/crossing-the-chasm-geoffrey-moore; Moore's 2009 NDIA slides, "Building a Chasm-Crossing Plan", ndia.dtic.mil/wp-content/uploads/2009/groundrobot/GMooreEveningSpeech.pdf.
- Gabriel Weinberg and Justin Mares, *Traction: How Any Startup Can Achieve Explosive Customer Growth*, Portfolio, 2015; summaries at growthmethod.com/traction-channels, rickkettner.com/traction-book-summary and dansilvestre.com/summaries/traction-book-summary.
- Brian Balfour, "Why Product Market Fit Isn't Enough", 28 June 2017, brianbalfour.com/essays/product-market-fit-isnt-enough; "Channel Model Fit", 18 July 2017, brianbalfour.com/essays/channel-model-fit-for-user-acquisition; "Product Channel Fit Will Make or Break Your Growth Strategy", brianbalfour.com/essays/product-channel-fit-for-growth.
- Christoph Janz, "Five ways to build a $100 million business", 27 October 2014, writing.pointnine.com/p/five-ways-to-build-a-100-million.
- David Skok, "SaaS Metrics 2.0", forentrepreneurs.com/saas-metrics-2.
- Paul Graham, "Do Things That Don't Scale", July 2013, paulgraham.com/ds.html.
- Lenny Rachitsky, "How today's fastest growing B2B businesses found their first ten customers", 7 July 2020, lennysnewsletter.com/p/how-todays-fastest-growing-b2b-businesses.
- Pete Kazanjy, *Founding Sales*, 2020, foundingsales.com.
- Bob Moesta with Greg Engle, *Demand-Side Sales 101: Stop Selling and Help Your Customers Make Progress*, 2020; notes at blog.jim-nielsen.com/2020/book-notes-demand-side-sales; the four forces at jobstobedone.org/the-four-forces.
- Matthew Dixon and Ted McKenna, *The JOLT Effect: How High Performers Overcome Customer Indecision*, Portfolio, 2022; Dixon interviewed in CustomerThink, "The problem of customer indecision and how to get over it", customerthink.com.
- April Dunford, *Obviously Awesome*, 2019, second edition 2026 (the positioning skill's method).
- US Federal Trade Commission, "CAN-SPAM Act: A Compliance Guide for Business", ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business.
- UK Information Commissioner's Office, "Electronic mail marketing", guide to PECR, ico.org.uk.
- CNIL, "Besoin d'aide" answer on email prospecting of professionals, cnil.fr/fr/cnil-direct/question/2002 (as quoted in search results).
- Germany's UWG § 7 on advertising email, as summarised by WBS Legal (wbs.legal) and others; not read in the statute itself.
- GDPR Article 14, Article 21 and Recital 47, gdpr-info.eu.
- Google, "Email sender guidelines", support.google.com/a/answer/81126; Spam Resource, "Google warns: Sender requirements enforcement ramping up", November 2025, spamresource.com/2025/11/google-warns-sender-requirements.html.
- Yahoo Sender Hub, "Sender Best Practices", senders.yahooinc.com/best-practices.
- Microsoft Outlook team, requirements for high-volume senders, Microsoft Tech Community, 2 April 2025, techcommunity.microsoft.com/blog/outlook/strengthening-email-security-outlook-new-requirements-for-high-volume-senders/4399730.
- G2, "In the Answer Economy, Don't Win the Click, Win the Answer", 15 April 2026, company.g2.com/news/g2-research-the-answer-economy.
