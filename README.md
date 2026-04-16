# wawa. Owner Portal

## Portal URL

Host `index.html` on GitHub Pages or any static host. The file is self-contained — no build step required.

## How to update (3-step git workflow)

```bash
git add index.html
git commit -m "Update: describe your change"
git push
```

GitHub Pages will automatically reflect changes within ~60 seconds.

## Setting the GitHub Secret: APPS_SCRIPT_TRIGGER_URL

1. Go to your repository on GitHub → **Settings** → **Secrets and variables** → **Actions**
2. Click **New repository secret**
3. Name: `APPS_SCRIPT_TRIGGER_URL`
4. Value: The published URL of your Apps Script trigger endpoint (e.g. `https://script.google.com/macros/s/YOUR_SCRIPT_ID/exec?action=runStatements`)
5. Click **Add secret**

## Manually triggering via GitHub Actions UI

1. Go to your repository on GitHub → **Actions**
2. Select the **Monthly Statement Auto-Run** workflow from the left sidebar
3. Click **Run workflow** → **Run workflow** (green button)

This will immediately trigger the Apps Script statement run without waiting for the 1st of the month.

## Scheduled auto-run

The workflow runs automatically at **6:00 AM UTC on the 1st of every month** via the cron schedule `0 6 1 * *`.
