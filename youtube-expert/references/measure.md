# Measuring your own videos, and learning from them

A video is judged against the channel's own videos of the same kind and age. YouTube publishes no target for click-through or retention; its own retention view compares a video with "your 10 latest videos of similar length" (YouTube Help, audience retention, checked 2026-10-22). Benchmarks from vendors and creators are rules of thumb: quote them as such, never as the bar.

## What to read, and when

All in YouTube Studio, in the video's analytics, unless said otherwise.

| Number | Where | When | What it tells you |
|---|---|---|---|
| Impressions, and impressions click-through rate | Reach | 7 and 28 days | Whether the title and thumbnail earn the click where they are shown |
| Traffic sources (search, suggested, browse, Shorts feed, external) | Reach | 7 and 28 days | Which door the viewers came through |
| **Stayed to watch** (Shorts): "the percentage of times viewers stayed to watch past the initial seconds of a Short" | The Short's analytics | 7 days | Whether the first seconds hold people in the feed |
| **Intro**: the share still watching after 30 seconds (long videos) | Engagement, key moments | 7 days | Whether the opening keeps the title's promise |
| Average view duration, average percentage viewed | Overview, Engagement | 7 and 28 days | How much of the video people watch |
| The retention curve, against typical retention | Engagement | 7 days | Where people leave, and where they rewatch |
| Engaged views | Overview | 7 and 28 days | Views by the old definition: a click, or watching past the first seconds |
| New and returning viewers | Audience | 28 days | Whether the channel brings people back |
| Test & compare result | The video's details | When it reports (up to two weeks) | Which title or thumbnail won on watch time |
| Instagram skip rate (left within three seconds) and retention chart | Instagram, the Reel's insights | 7 days | The same cut's opening, measured in another feed |
| TikTok average watch time, watched full video | TikTok analytics | 7 days | The same, on TikTok |

**Views changed on 24 August 2026:** a view now counts from the first frame, autoplay included. Click-through, view duration and retention stay based on engaged views (YouTube Blog, 2026-08-19). Use engaged views for any comparison, and never compare public views from before and after that date.

**Small numbers hide figures.** Studio may show no retention curve or stayed-to-watch figure on a video with very few views. Until a channel's videos pass that point, compare on what is shown (views from the Shorts feed or from search at seven days, average percentage viewed), and post the same cut where the skip is reported per video (Instagram's skip rate). Say which measure each comparison used.

## Reading a retention curve

YouTube's own guide (YouTube Help, audience retention, checked 2026-10-22):
- a **flat** stretch means people watched that part through;
- a **gradual decline** is normal;
- a **dip** marks a part people skipped or left;
- a **spike** marks a part watched again or shared, which can also mean it was unclear the first time;
- when the best-held moments come **late**, introduce them earlier.

## What the numbers suggest, and what to change

Reasoned from YouTube's definitions above. Each is a suggestion to test on the next video, never a rule from one reading.

| What you see | What it suggests | What to try |
|---|---|---|
| Few impressions | YouTube has not found people for this topic, or few look for it | Re-run the topic check; make the question plainer in the title, description and chapters; send viewers who already have the question |
| Impressions normal, click-through low against your own videos | The title and thumbnail do not earn the click | Test & compare two new titles or thumbnails |
| Click-through good, Intro (30 seconds) low | The opening does not match the promise | A truer title and thumbnail, or a new opening (YouTube's first two tips for a weak intro) |
| A sharp dip at one point | A part people skip | Cut it, or move it after the payoff |
| Good retention, then a cliff before the end | The ending drags, or the payoff came too late | End sooner; move the payoff into the first half |
| Shorts: low stayed to watch | The first frame and first seconds do not hold the feed | A new opening: the viewer's subject in big words, moving from frame 0, nothing that looks like an ad |
| Shorts: stayed to watch good, average percentage viewed low | It holds, then loses them | Shorter; the payoff earlier; one re-hook |
| Nearly all views from search | An evergreen answer, growing slowly | Fine; make the next video on the questions next to it |
| Few returning viewers | One-off visits | A series on one question; end screens and playlists pointing to the next video |

## How much data a comparison needs

Two versions of a Short (two openings, two looks) are compared on the share who stayed. To tell 40% from 55% at the usual 95% confidence and 80% power takes about 170 feed viewers per version: 7.84 × (0.40 × 0.60 + 0.55 × 0.45) / 0.15² ≈ 170 (the standard two-proportion formula). Telling 40% from 45% takes about 1,500 per version. Below that, a difference is noise: write "not enough yet" and keep posting. Compare pieces at the same age (seven days), on the same platform.

## Keeping the record

One table for the channel (`video/channel.csv` or a sheet), one row per video per reading:

```
date,video,kind,published,age_days,impressions,ctr,engaged_views,avg_pct_viewed,intro_30s,stayed_to_watch,returning_viewers
```

Fill a cell only from Studio, and leave it empty when Studio shows nothing. Read each video at seven and 28 days.

## Learning

- Each week, add a line to the playbook's "What our channel has learnt": the piece, the number and its age, what it suggests, and how sure (one video is a hint; the same result on three is a pattern).
- When the channel's numbers contradict a playbook entry three times, mark the entry "contradicted by our channel" and say how.
- A result that settles something the team decided (a house look, a length, a format) goes in that decision on record, with the numbers and their dates.
