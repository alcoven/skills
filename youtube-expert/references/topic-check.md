# Checking a topic, and the weekly scout

The question: do people watch this topic, told this way, now? Answer it with measurements before a script exists. The measure that matters is the **multiple**: a video's views divided by the median views of its channel's recent uploads of the same kind (long videos with long videos, Shorts with Shorts). "8x" means eight times that channel's usual, so the topic and its telling drew people beyond the channel's regulars, and a big channel's ordinary video does not pass for a hit.

## 1. Phrase it the way viewers type it

- Three to six phrasings, in the viewer's words, with the thing they search for first: "sourdough starter not rising", "sourdough schedule full time job".
- Check what YouTube completes them to. A phrase YouTube suggests is one people type. With a shell:

```bash
curl -s -A "Mozilla/5.0" "https://suggestqueries.google.com/complete/search?client=firefox&ds=yt&q=sourdough%20starter"
```

It returns `["sourdough starter", ["sourdough starter recipe", "sourdough starter feeding", ...]]`. Add a letter after the seed (`sourdough%20starter%20w`) to see more. This is the autocomplete YouTube's search box uses, with `ds=yt` for YouTube; it is undocumented, may change, and may refuse fast repeated calls (it worked on 2026-10-22). Without a shell, type the seed into YouTube's search box and read the suggestions, or ask the person to.

## 2. Measure, with a shell and yt-dlp

[yt-dlp](https://github.com/yt-dlp/yt-dlp) reads YouTube's public pages; with these flags it signs in to nothing and downloads no video. Install with `pip install yt-dlp` or `brew install yt-dlp`. Every command below was run with yt-dlp 2026.08.19 on 2026-10-22.

**The top results for a phrasing,** with views, length in seconds, channel and title:

```bash
yt-dlp --flat-playlist --print "%(view_count)s | %(duration)s | %(channel)s | %(channel_id)s | %(url)s | %(title)s" "ytsearch15:sourdough schedule full time job"
```

A result whose address contains `/shorts/` is a Short.

**Its upload date and the channel's subscribers** (search results carry no date):

```bash
yt-dlp --skip-download --print "%(upload_date)s | %(channel_follower_count)s | %(view_count)s" "https://www.youtube.com/watch?v=VIDEO_ID"
```

**The channel's usual:** the median views of its last 30 uploads of the same kind (`/videos` or `/shorts`):

```bash
yt-dlp --flat-playlist --playlist-end 30 --print "%(view_count)s" "https://www.youtube.com/channel/CHANNEL_ID/videos" | grep -E '^[0-9]+$' | sort -n | awk '{a[NR]=$1} END {print NR " uploads, median " (NR%2 ? a[(NR+1)/2] : (a[NR/2]+a[NR/2+1])/2)}'
```

Uploads with no count yet (a premiere, a live stream) are skipped. Views on a channel's tab are rounded to two or three figures, which is fine for a median. With fewer than five uploads there is no usual, so no multiple.

**The multiple:** the result's views divided by that median, to one decimal place.

**Breakouts on a watchlist channel:** its recent uploads with approximate dates, to keep those from the last 14 days at 3x its median or more:

```bash
yt-dlp --flat-playlist --playlist-end 30 --extractor-args "youtubetab:approximate_date" --print "%(upload_date)s | %(view_count)s | %(id)s | %(title)s" "https://www.youtube.com/@HANDLE/videos"
```

For more than a few channels, write a short script that loops over the watchlist and prints one table, and keep it beside the watchlist. YouTube answers too many requests at once with "HTTP Error 429": run a few at a time, or add `--sleep-requests 2`.

If the channel's YouTube Studio shows the Research view (in test since August 2026), it lists outliers among videos the channel's audience watches. Use it as a second reading, and still read the titles.

## 3. Without a shell

Web search or a browser can find the videos, but proves less.

- Search YouTube (or the web, `site:youtube.com "<phrasing>"`) for each phrasing and note each top result's views, date and channel as shown.
- If you can open YouTube pages, open each channel's Videos tab sorted by latest, read the views of its last 15 to 30 uploads, and take the median by hand. That gives a real multiple.
- **What it can't prove:** without channel medians there is no multiple, so a big number may be a big channel's ordinary day; search snippets show rounded or old counts; results differ by country and account; autocomplete is not visible. The most a web search alone supports is "seen but unmeasured": call the topic Thin at most, and say so in the brief.
- Or ask the person to paste their search results page, or their Studio's Research view.

## 4. Read it

| Verdict | What the numbers show | What you check |
|---|---|---|
| **Proven** | Two or more channels at 2x their usual or more and 20,000 views or more, at least one under a year old | Are those hits on this angle, or generic videos that share the words? |
| **Open** | No result in the top ten over 10,000 views, and autocomplete shows people typing it | Can the team answer it well? If autocomplete shows nothing either, call it empty and drop it. |
| **Thin** | One such hit | Is it a fluke: a famous guest, a news day, a channel's one viral video? |
| **Weak** | Results exist, none beat their channel's usual | Reframe, or drop. |

The floors (20,000 and 10,000 views) suit a broad niche. In a small one, lower them and say so.

**Pitfalls:**
- **Tiny channels inflate multiples.** 50x on a channel that usually gets 200 views is 10,000 views. Keep the floor.
- **A platform's or brand's own videos** get launch traffic and promotion. They show interest in the product, and say nothing about whether a creator's video on the angle works.
- **Generic videos match narrow phrasings.** Read every title and drop off-angle hits before giving the verdict.
- **Age.** A two-day-old video at 4x is still climbing; a two-year-old one at 4x may come from another era of the topic.
- **The first frame counts as a view since 24 August 2026.** Compare channels measured on the same day, and never with readings from before that date.

## 5. Name the reference videos

Two to five videos that prove the angle, each with views, multiple and age, linked. For each: the title's shape, what the first ten seconds promise (watch them, or read the transcript), the length. They go in the brief's evidence table.

## 6. Decide

- **Proven:** make it, in the proven shape, with the team's honest difference.
- **Open:** make it if people type it and the team has the answer; package it as the question they type.
- **Thin or weak:** search two or three reframings of the same facts toward the nearest proven shape, and recommend one, or drop the topic. Never make a weak topic as it is.

The brief's worked example ([brief.md](brief.md)) shows a weak topic reframed.

## The watchlist

Twenty to fifty channels, kept as a table in the project (`video/watchlist.md`): handle, group, and why it is there. Useful groups:

| Group | Why |
|---|---|
| Same audience | What wins with the viewers the team wants |
| Same format or look | What wins in the way the team makes videos |
| Next door | Adjacent topics the audience also watches |
| The platforms and tools the audience uses | Releases worth a quick video |
| Another language | What is moving in a market the team also serves |

Fix a handle that reads nothing with `yt-dlp --flat-playlist --print "%(channel_url)s" "ytsearch1:<channel name>"`. Once a quarter, drop channels that stopped uploading.

## The scout report's shape

```markdown
# Scout, YYYY-MM-DD

## Releases to answer within 48 hours
<what shipped, where it was announced, the phrasing people will type>

## Breaking out
| x | Views | Age | Kind | Channel | Title |
|---|---|---|---|---|---|
The pattern: <topics, title shapes, formats, lengths>.

## What people type
<new or rising autocomplete phrases, per seed>

## YouTube's changes
<what changed in ranking, measurement or features, with the official source and date>

## Five topic candidates
For each: the verdict, two or three reference videos with multiples, the angle.

## Playbook edits
<entries added, corrected, re-dated or marked stale, and why>
```
