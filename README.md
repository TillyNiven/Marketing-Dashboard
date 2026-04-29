# Marketing Dashboard

A shareable, interactive marketing dashboard built in HTML. No server needed — deploy for free on GitHub Pages.

## Live sections
- **Executive summary** — top-line KPIs across all channels
- **LinkedIn organic** — follower growth, impressions, engagement
- **LinkedIn paid** — campaign breakdown, ad creatives, leads
- **SEO traffic** — monthly sessions with month-on-month comparison
- **Google Ads** — campaign performance, spend, conversions
- **Partnerships & BD** — partner stats and monthly narrative

---

## How to deploy (one-time setup, ~5 minutes)

1. Go to [github.com](https://github.com) and create a free account if you don't have one
2. Click **New repository**
3. Name it `marketing-dashboard`
4. Set to **Public** (required for free GitHub Pages)
5. Click **Create repository**
6. Upload both files: `index.html` and `data.js`
7. Go to **Settings → Pages**
8. Under "Source", select **Deploy from a branch → main → / (root)**
9. Click **Save**
10. Your dashboard will be live at: `https://YOUR-USERNAME.github.io/marketing-dashboard`

Share that link with stakeholders — no login required to view.

---

## How to update each month (~15 minutes)

All data lives in **`data.js`**. You only ever edit this one file.

### Steps:
1. Open `data.js` in GitHub (click the file → click the pencil icon to edit)
2. Add a new row to each relevant section (see examples below)
3. Scroll down and click **Commit changes**
4. Dashboard updates immediately

### Example — adding a new month to SEO:
```js
seo: [
  { month: "Mar 2026", sessions: 22150 },
  { month: "Apr 2026", sessions: 24810 },
  { month: "May 2026", sessions: 26400 }, // ← add new row here
],
```

### Example — updating LinkedIn paid campaigns:
Replace the `campaigns` array with the current month's numbers:
```js
campaigns: [
  { name: "Brand awareness", impressions: 51000, clicks: 1020, leads: 25, spend: 1300 },
  ...
],
```

### Adding ad creative images:
1. Upload your ad image to the GitHub repo (drag and drop into the file list)
2. In `data.js`, find the `ads` section and add the filename:
```js
ads: [
  { campaign: "Brand awareness", imageUrl: "ad-brand-may.png", leads: 25, impressions: 51000 },
],
```

---

## Monthly data checklist

| Source | Where to download | What to update in data.js |
|---|---|---|
| LinkedIn organic followers | LinkedIn Analytics → Followers → Export | `linkedinOrganic.followers` — add new month row |
| LinkedIn organic content | LinkedIn Analytics → Content → Export | `linkedinOrganic.content` — add new month row |
| LinkedIn paid | Campaign Manager → Export performance | `linkedinPaid.campaigns` — replace with current month |
| SEO | Google Analytics → Traffic acquisition → Export | `seo` — add new month row |
| Google Ads | Google Ads → Reports → Download | `googleAds.campaigns` — replace with current month |
| Partnerships | Manual | `partnerships` — update numbers + `monthlySummary` bullets |

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The dashboard — don't edit this unless changing layout |
| `data.js` | All your data — edit this every month |
| `README.md` | These instructions |
