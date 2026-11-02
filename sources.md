# Sources

The fixed list the Monday Digest checks. Source of truth for addresses: this file.
Spec: "Claude Code Handoff: Weekly AI Pulse Digest" (pinned Claude Doc).

Addresses checked on 2026-11-02. "Feed" means an RSS or Atom feed, a machine-readable list of recent posts with dates.

| # | Source | What to look for | How to fetch | Address |
|---|---|---|---|---|
| 1 | Andrej Karpathy's blog | New posts | Feed | https://karpathy.bearblog.dev/feed/ |
| 2 | Forward Future newsletter | New issues and model reviews | Page (no feed exists) | https://forwardfuture.com/ and https://forwardfuture.com/newsletter/daily |
| 3 | Anthropic engineering blog | New posts | Page (no feed exists) | https://www.anthropic.com/engineering |
| 4 | OpenAI news | New engineering and product posts | Feed, then keep only engineering, research and developer items | https://openai.com/news/rss.xml |
| 5 | GitHub Copilot changelog | New entries | Feed | https://github.blog/changelog/label/copilot/feed/ |
| 6 | Claude Code changelog | New releases | Raw file; each `## x.y.z` heading is a release | https://raw.githubusercontent.com/anthropics/claude-code/main/CHANGELOG.md |
| 7 | Simon Willison's blog | New posts | Feed | https://simonwillison.net/atom/everything/ |
| 8 | David Ondrej on GitHub | New commits and releases, including his public agent skills repo | Feed; fallback is the public API | https://github.com/davidondrej.atom, fallback https://api.github.com/users/davidondrej/events/public |
| 9 | Cloudroom | New releases or posts | Page | https://www.cloudroom.dev/ |
| 10 | David Ondrej on X | Recent posts, if reachable | Page; X usually blocks automated reading | https://x.com/DavidOndrej1 |
| 11 | David Ondrej on YouTube | New videos | YouTube MCP server, `get_channel_videos` | channel `@DavidOndrej` (ID UCPGrgwfbkjTIgPoOh2q1BAg) |

## Notes

- **David Ondrej** founded Cloudroom, a vendor product. Treat his promotion of it accordingly.
- **OpenAI**'s engineering-only page refuses automated requests (HTTP 403), so the general news feed is used and filtered.
- **LinkedIn** is excluded by decision. Sources that need a login are out of scope.
