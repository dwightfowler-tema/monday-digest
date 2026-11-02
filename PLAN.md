# Plan

Open work on the Monday Digest project itself: fixes and ideas for `DIGEST.md`, `sources.md`, `.mcp.json` and the cloud routine.

- This is a to-do list, not instructions. A digest run does not read, act on, or edit this file.
- Items change only when Dwight asks. Moving an item to Done means the change was made and pushed.
- Each item says what is wrong, what would fix it, and which file the fix touches.

## Open

1. **David Ondrej on GitHub cannot be reached from the cloud.** The fetch tool refuses because github.com's robots.txt returned 403. The API fallback is refused because cloud sessions can only reach their attached repository. Options: drop the source, or find a reader that works. Touches: `sources.md`.
2. **David Ondrej on X is blocked** by x.com's robots.txt, as `sources.md` expected. Option: drop the source. Touches: `sources.md`.
3. **YouTube videos come back without dates,** so the run cannot tell which are new. Next week the `seen` list keeps repeats out, but first-time items are still undated. Option: get dates from `get_video_info`. Touches: `DIGEST.md` or `sources.md`.
4. **Long feeds are cut off** at the fetch tool's length limit (Karpathy, OpenAI, Simon Willison, Cloudroom), so items can be missed. Option: tell the run to fetch the rest with `start_index`, as row 2 now does. Touches: `DIGEST.md`.
5. **"Nothing new" is listed under "Sources that failed".** The test digest lists Anthropic engineering as failed although it loaded and had no new post. Option: add a "No new items" line to the format. Touches: `DIGEST.md`.
6. **Check sitemaps for the other page sources.** Look in robots.txt for Anthropic engineering and Cloudroom, as was done for Forward Future. Touches: `sources.md`.
7. **Forward Future tools directory:** decided not to add for now. `https://forwardfuture.com/sitemaps/tools.xml` lists about 1,040 vendor-submitted tools, with 16–30 added each Monday. Option: report only new tools whose description mentions agents, MCP or coding. Touches: `sources.md`.

## Done

- 2026-11-02: Routine fixed: repo attached, Gmail connector attached, weekly schedule set. Test run pushed and emailed the first digest.
- 2026-11-02: Forward Future now read from its two newsletter sitemaps instead of two web pages.
- 2026-11-02: Test digest removed and `state/last-run.json` reset, so the first scheduled run covers the full 7 days.
