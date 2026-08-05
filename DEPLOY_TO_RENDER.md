# Deploy Month-End Hub to Render (one-time)

**Live URL when done:** https://supercat-month-end.onrender.com/

**GitHub repo:** https://github.com/angelasupercat/supercat-month-end

Same pattern as commissions — push updates Render.

## One-time setup (do this once in the browser)

1. Open https://dashboard.render.com/ and sign in with GitHub (`angelasupercat`).
2. **New +** → **Static Site**.
3. Connect repo: **angelasupercat/supercat-month-end**.
4. Settings:
   - **Name:** `supercat-month-end`
   - **Branch:** `main`
   - **Build Command:** leave blank (or `true`)
   - **Publish Directory:** `.`
5. Create Static Site → wait until **Live**.
6. Open the URL and confirm Jul 2026 tab loads. If Render assigned a different subdomain, send it back so we lock it in Notion/docs.

Optional: **New +** → **Blueprint** → select this repo (`render.yaml`).

## Every month after Phase 2

From `supercat-code` (Cursor or Claude Code):

```bash
node scripts/publish_month_end_hub.js \
  --period YYYY-MM \
  --label "Mon YYYY" \
  --html path/to/report.html \
  --notion-url "https://www.notion.so/..." \
  --live-push
```

Full Phase 2 `publish_fpa_report.js` for month-end already includes `--live-push`.

## Share with others

Send the Render URL. No Desktop file needed.
