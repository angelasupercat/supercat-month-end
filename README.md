# SuperCat — Month-End Financial Commentary (live)

**Public clickable hub** (one tab per closed month).  
Internal leadership only — share the URL, not a Desktop file.

| | |
|--|--|
| **Live URL** | https://supercat-month-end.onrender.com/ *(after first Render deploy)* |
| **GitHub** | https://github.com/angelasupercat/supercat-month-end |
| **Notion operator** | [Month End Ninja](https://www.notion.so/397231dbcd70813b8650e1d4dd654e9e) |
| **Standard (repo)** | `supercat-code/doc/fpa/MONTH_END_REPORT_STANDARD.md` |

This folder lives **outside** `supercat-code` and **outside** Desktop so Cursor / Claude Code and the live site stay clean.

---

## How a new month gets onto the site

From `supercat-code` after Phase 2 HTML is approved:

```bash
node scripts/publish_month_end_hub.js \
  --period 2026-08 \
  --label "Aug 2026" \
  --html path/to/report.html \
  --notion-url "https://www.notion.so/..." \
  --live-push
```

That updates the hub, mirrors into this repo, commits, and pushes → Render auto-deploys.

---

## Manual deploy (first time / recovery)

1. Push this repo to `main`.
2. Render Dashboard → **New** → **Static Site** → connect `angelasupercat/supercat-month-end`.
3. Publish directory: `.` · Build command: empty (or `true`).
4. Or use Blueprint: this repo’s `render.yaml`.

---

## Contents

```
index.html          ← tabbed hub
months.json         ← registry
months/YYYY-MM/report.html
render.yaml
README.md
```
