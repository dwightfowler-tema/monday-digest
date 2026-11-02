# Monday Digest

## Build a weekly digest of news and blogs regarding the most usefull AI trends and technologies of the last week

## How it works

- **Where it runs:** a Claude Code cloud task (a "Routine") in the `env-monday-digest` environment. It does not need your computer.
- **What it does:** follows `DIGEST.md`, checks the sources in `sources.md`, writes `digests/YYYY-MM-DD.md`, updates `state/last-run.json`, pushes to `main`, and emails you the digest.
- **Getting the results:** check your Gmail, or run `git pull` here and open `digests/`.
- **Running it by hand:** open Claude Code in this folder and say "run my digest", or run `claude -p "run my digest"`.

| File | Purpose |
|---|---|
| `DIGEST.md` | Step-by-step instructions for each run |
| `sources.md` | Sources and their feed or page addresses |
| `.mcp.json` | The two MCP servers: `fetch` for feeds and pages, `youtube` for YouTube |
| `state/last-run.json` | When the last run happened and what was already reported |
| `digests/` | One dated digest per week |
| `CLAUDE.md` | Points Claude at `DIGEST.md` |
| `PLAN.md` | To-do list for changes to the project itself (not read during runs) |
