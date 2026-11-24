# Plan

Open work on the Daily Digest project itself: fixes and ideas for `DIGEST.md`, `sources.md`, `.mcp.json` and the cloud routine.

- This is a to-do list, not instructions. A digest run does not read, act on, or edit this file.
- Items change only when Dwight asks. Moving an item to Done means the change was made and pushed.
- Each item says what is wrong, what would fix it, and which file the fix touches.

## Open

1. **David Ondrej on GitHub cannot be reached from the cloud** (still undecided as of 2026-11-24). The fetch tool treats a 401 or 403 answer for robots.txt as "do not fetch", and github.com's robots.txt answers 403 to it. The API fallback, api.github.com, is not on the cloud environment's allowed hosts. Options: drop the source, or start the fetch server with `--ignore-robots-txt` (applies to every source) and test. Touches: `sources.md` or `.mcp.json`.
2. **"Nothing new" is listed under "Sources that failed".** The test digest lists Anthropic engineering as failed although it loaded and had no new post. Option: add a "No new items" line to the format. Touches: `DIGEST.md`.
3. **Check sitemaps for the other page sources.** Look in robots.txt for Anthropic engineering and Cloudroom, as was done for Forward Future. Touches: `sources.md`.
4. **Forward Future tools directory:** decided not to add for now. `https://forwardfuture.com/sitemaps/tools.xml` lists about 1,040 vendor-submitted tools, with 16–30 added each Monday. Option: report only new tools whose description mentions agents, MCP or coding. Touches: `sources.md`.

## Done

- 2026-11-24: Renamed to Daily Digest and kept the daily schedule. Runs now push straight to `main` (the routine prompt and `DIGEST.md` step 7 say so); the Nov 19, 21, 22 and 23 digests stranded on side branches were merged into `main` and their pull requests closed.
- 2026-11-24: David Ondrej on X dropped (robots.txt blocks it).
- 2026-11-24: YouTube now read from the channel's dated feed; the YouTube MCP tool is the fallback.
- 2026-11-24: Claude Code releases tracked by `claude_code_last_version` in the state file.
- 2026-11-24: Long feeds: `DIGEST.md` tells the run to fetch the rest with `start_index`.

- 2026-11-02: Routine fixed: repo attached, Gmail connector attached, weekly schedule set. Test run pushed and emailed the first digest.
- 2026-11-02: Forward Future now read from its two newsletter sitemaps instead of two web pages.
- 2026-11-02: Test digest removed and `state/last-run.json` reset, so the first scheduled run covers the full 7 days.
