# Monday Digest: run instructions

Follow these steps exactly whenever you are asked to "run my digest", whether by the weekly cloud schedule, in chat, or by `claude -p "run my digest"`.

Reader: Dwight. Goal: one short weekly digest of what changed in the sources in `sources.md`, sorted into two piles, so he can stop finding AI news by scrolling YouTube.

## Steps

1. **Read the state.** Open `state/last-run.json`. `last_run` is the date of the last successful run. `seen` lists item links already reported. If the file is missing or `last_run` is null, use 7 days ago as the start date.
2. **Fetch each source** in `sources.md`, using the method listed there.
   - Feeds and pages: use the `fetch` MCP tool. Fall back to WebFetch or `curl` only if the MCP tool is unavailable, and note that in the digest's run notes.
   - YouTube: use the `youtube` MCP tool `get_channel_videos` with `channel="@DavidOndrej"`, `sort="date"`, `limit=10`.
   - Keep only items published after `last_run` and not in `seen`. For pages without dates, compare against `seen`.
   - If a source fails (error, timeout, blocked, empty), do not retry more than once. Record it under "Sources that failed" with the reason, and move on.
3. **Write one line per item.** Say in plain English what changed, then link to the primary source page you actually opened. Never state a fact from memory. If unsure, say so.
4. **Sort each item into one of two piles.**
   - **Changes how Dwight works:** only if it changes a tool he uses (GitHub Copilot at work, Claude Code at home), gives a technique he could apply this week, or a capability that moves where his own judgment is needed.
   - **Noise:** everything else. When unsure, put it here and give the reason in one short phrase.
5. **Write the digest** to `digests/YYYY-MM-DD.md` (today's date, America/New_York). Use the format below.
6. **Update the state.** Set `last_run` to now (ISO 8601 with time zone), add every reported item's link to `seen`, and keep only links from the last 60 days.
7. **Commit and push** `digests/` and `state/` to `main` with the message `digest: YYYY-MM-DD`. If the push fails, say so in the email and in your final reply.
8. **Email the digest** with the Gmail tool to dwight.fowler@gmail.com, subject `Monday Digest — YYYY-MM-DD`, body = the digest's Markdown. If the Gmail tool is not available, say so plainly in your final reply. Do not pretend it was sent.
9. **Reply** with a short summary: item counts per pile, failed sources, and whether the push and email worked.

## Writing rules

- Plain English. Define any technical term in the same line, after the plain explanation, e.g. "a list of recent posts a program can read (an RSS feed)".
- Every factual claim links to a primary source you opened.
- Short: the first pile first, then noise as one line per item.

## Digest format

```markdown
# Monday Digest — YYYY-MM-DD
Covers: <last_run date> to <today>

## Changes how you work
- **<Source>:** <one plain-English line>. [link](<url>)

## Noise
- <Source>: <one line> — <why it's noise>. [link](<url>)

## Sources that failed
- <Source>: <reason>

## Run notes
- <anything unusual, e.g. a fallback fetch method was used>
```

If a pile is empty, write "Nothing this week."
