# Herman Legacy Group — hermanlegacygroup.com

Parent holding company. Part of the Herman Legacy Group ecosystem.

## Pages
- `about.html`
- `contact.html`
- `index.html`
- `partner.html`
- `portfolio.html`

## Forms → Supabase
Contact and submission forms write directly to the shared **herman-family-calendar**
Supabase project using the publishable key (safe to expose). Row Level Security allows
anonymous inserts only — submissions can't be read from the browser. Review them in the
Supabase dashboard or your admin tooling.

Config lives in the shared script at the bottom of each page (`SUPABASE_URL` /
`SUPABASE_KEY`). Each form posts to a specific table via its `data-table` attribute.

Run the migration once (from the repo that holds `/supabase`) to create the tables:
`supabase/migrations/20260626030000_herman_legacy_sites_form_submissions.sql`

## Deploy (GitHub Pages)
1. Create a repo and push these files to `main`.
2. Settings → Pages → Source: **GitHub Actions** (the included `.github/workflows/deploy.yml` handles it).
3. The `CNAME` file points the site at `hermanlegacygroup.com` — set that custom domain in Settings → Pages
   and add the DNS records your registrar needs (A/ALIAS to GitHub Pages, or CNAME for www).

The site is plain static HTML/CSS/JS — no build step required.
