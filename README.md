# eongerra.com

One-page site for Eongerra Tech. Static HTML — no build step, no dependencies.

```
index.html      # landing page
privacy.html    # privacy policy (used as the Play Store privacy URL)
```

## Deploy

Any static host works. Two easy options:

**GitHub Pages**
1. Push this folder to a GitHub repo.
2. Repo → Settings → Pages → deploy from branch (root).
3. Add a custom domain `eongerra.com` (Settings → Pages → Custom domain);
   GitHub writes a `CNAME` file and tells you the DNS records to add.

**Netlify / Cloudflare Pages** — drag-drop this folder, then point the
`eongerra.com` domain at the site in the dashboard.

Once live, your URLs are:
- Site: `https://eongerra.com`
- Privacy hub: `https://eongerra.com/privacy.html`
- **AI Doomsday privacy (paste into Play Console for AI Doomsday):**
  `https://eongerra.com/privacy/ai-doomsday.html`
- Invois privacy (later): `https://eongerra.com/privacy/invois.html`

Each app points Play Console at its OWN policy URL — the apps handle data
differently, so they can't share one "collects nothing" policy.

## Verify the domain for Google Play (org account)

Play's "Verify your organisation's website" is a **domain-ownership check via
Google Search Console** — it does NOT inspect the page content. Steps:

1. Go to **search.google.com/search-console**, signed in with the SAME Google
   account as your Play Console (`sy.erikchow@eongerra.com`).
2. Add a **Domain** property for `eongerra.com`.
3. Search Console gives you a **DNS TXT record** (`google-site-verification=…`).
   Add it at your domain's DNS host (Cloudflare / GoDaddy / Namecheap / wherever
   the nameservers are). Wait until Search Console shows **"Ownership verified"**.
4. Back in Play Console → the website task → **Send verification request**.
   Because it's the same Google account, it auto-approves (often instantly).

Notes:
- Domain (DNS) verification needs NO live page and NO HTTPS — but you're
  deploying a real site anyway for the privacy URL + credibility.
- The website domain does not need to match your contact email domain (yours
  happen to both be eongerra.com, which is convenient).

## Edit

Plain HTML + inline CSS. Colors and fonts are CSS variables at the top of each
file (`--signal` is the single accent). Fonts load from Google Fonts.
