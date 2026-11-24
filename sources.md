# Sources

The fixed list the Daily Digest checks. Source of truth for addresses: this file.
Spec: "Claude Code Handoff: Weekly AI Pulse Digest" (pinned Claude Doc).

Addresses checked on 2026-11-02. "Feed" means an RSS or Atom feed, a machine-readable list of recent posts with dates.

| # | Source | What to look for | How to fetch | Address |
|---|---|---|---|---|
| 1 | Andrej Karpathy's blog | New posts | Feed | https://karpathy.bearblog.dev/feed/ |
| 2 | Forward Future newsletter | New daily issues, and new essays and model reviews ("originals") | Sitemap (no feed exists): a machine-readable list of the site's pages. Keep entries whose `<lastmod>` is after `last_run`, skip `/page/` and `/topic/` links, then open each kept link for its title and summary. Newest entries are near the top; if the fetched text ends before reaching an entry dated before `last_run`, fetch the rest (`start_index`) | https://forwardfuture.com/sitemaps/newsletter-daily.xml and https://forwardfuture.com/sitemaps/newsletter-originals.xml |
| 3 | Anthropic engineering blog | New posts | Page (no feed exists) | https://www.anthropic.com/engineering |
| 4 | OpenAI news | New engineering and product posts | Feed, then keep only engineering, research and developer items | https://openai.com/news/rss.xml |
| 5 | GitHub Copilot changelog | New entries | Feed | https://github.blog/changelog/label/copilot/feed/ |
| 6 | Claude Code changelog | New releases newer than `claude_code_last_version` in `state/last-run.json` | Raw file; each `## x.y.z` heading is a release | https://raw.githubusercontent.com/anthropics/claude-code/main/CHANGELOG.md |
| 7 | Simon Willison's blog | New posts | Feed | https://simonwillison.net/atom/everything/ |
| 8 | Cloudroom | New releases or posts | Page | https://www.cloudroom.dev/ |

## Notes

- **David Ondrej** founded Cloudroom, a vendor product. Treat his promotion of it accordingly.
- **OpenAI**'s engineering-only page refuses automated requests (HTTP 403), so the general news feed is used and filtered.
- **David Ondrej on X** was dropped on 2026-11-24: x.com's robots.txt forbids automated reading, so every run failed.
- **David Ondrej on GitHub** was dropped on 2026-11-24: the fetch tool was refused on every run (github.com's robots.txt answers 403, and api.github.com is not an allowed host).
- **David Ondrej on YouTube** was dropped on 2026-11-24: YouTube's robots.txt blocks the channel feed, and the YouTube tool could not read publish dates.
- **LinkedIn** is excluded by decision. Sources that need a login are out of scope.
