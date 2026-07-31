# sidv.co

Personal site. One page, above the fold only. No build step, no dependencies.

- `index.html` — the entire site (HTML + inline CSS, self-contained)
- `portrait.jpg` — the illustrated portrait, resized to 540x720 and 175 KB
- `CNAME` — tells GitHub Pages to serve the site at `sidv.co`

## Deploy (GitHub Pages, free account)

1. Create a **public** repo on GitHub named `sidvarma.github.io` (swap in your own
   username). A repo with that exact name is served at the root of the domain.
2. Upload `index.html` and `CNAME` to the root of that repo, or push them:

   ```
   git init
   git add .
   git commit -m "Personal site"
   git branch -M main
   git remote add origin https://github.com/<username>/<username>.github.io.git
   git push -u origin main
   ```

3. In the repo: **Settings → Pages**. Source = "Deploy from a branch", branch = `main`,
   folder = `/ (root)`.
4. Same page, **Custom domain** = `sidv.co`. Save.
5. At your DNS provider, add these records for the apex domain `sidv.co`:

   | Type | Name | Value |
   |------|------|-------|
   | A    | @    | 185.199.108.153 |
   | A    | @    | 185.199.109.153 |
   | A    | @    | 185.199.110.153 |
   | A    | @    | 185.199.111.153 |
   | CNAME | www | `<username>.github.io.` |

6. Wait for DNS to propagate (minutes to a few hours), then tick **Enforce HTTPS**
   in Settings → Pages.

## Editing

Everything lives in `index.html`. Copy is in the `<main>` block near the bottom;
colors are the CSS variables at the top (`:root` for light, the
`prefers-color-scheme: dark` block for dark).
