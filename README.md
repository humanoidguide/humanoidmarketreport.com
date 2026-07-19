# humanoidmarketreport.com

Official humanoid.guide microsite for the **2026 Humanoid Robot Market Report**.
Static site served by GitHub Pages at https://humanoidmarketreport.com.

## Files

| File | Purpose |
|---|---|
| `index.html` | The microsite (editorial design, all CSS/JS inline) |
| `archive.html` | The Briefing archive — renders every item in `news.json`, grouped by month |
| `news.json` | All news items. The front page shows the 3 newest; the archive shows everything |
| `SOURCES.md` | Trusted-source allowlist + publishing rules for the scheduled news publisher |
| `CNAME` | Custom domain for GitHub Pages |

## How news updates work

A scheduled task (the *publisher*) runs twice a day: it searches for humanoid-market news
(funding, manufacturers, deployments, IPOs), verifies sources against `SOURCES.md`, writes a
headline + 1–2 sentence summary in humanoid.guide style, prepends the item to `news.json`
and commits. GitHub Pages redeploys automatically. A second scheduled task (the *auditor*)
checks published items daily (dead links, duplicates, valid JSON) and fixes or flags issues.

New items go at the **top** of `items` in `news.json` with an ISO date (`iso`), display date
(`date`), `chip` category, `source`, `url`, and either an approved `image` + `credit` or a
branded card (`art`: `yellow` | `dark` | `green`, plus `artTitle`).

## Rollback

Everything is git — `git revert` any commit to undo a bad update.

Maintained with Claude. Buy the report: https://humanoid.guide/humanoid-robot-market-report/
