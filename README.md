# rotharsteig

Static **deelnemerssite** voor de Rothaarsteig-hike (maart 2026): home, route/kaart, accommodaties, eten, praktisch (kosten, auto’s, Splitser).

- **Splitser:** lijst staat in `praktisch.html` (`app.splitser.com`).
- **Open Graph:** `og-image.png` + meta-tags in elke HTML-pagina. De absolute URL’s staan op `https://lennartdeknikker.github.io/rotharsteig/` — bij een **eigen domein** of andere repo-naam overal in de `<head>` dezelfde basis-URL vervangen (`canonical`, `og:url`, `og:image`, `twitter:image`).
- **Privé / geen indexering:** `robots.txt` blokkeert crawlers (`Disallow: /`), en elke pagina heeft `<meta name="robots" content="noindex, nofollow">`. Dit is geen wachtwoord: de site blijft openbaar bereikbaar met de URL; voor echte afscherming gebruik je een private repo + Pages met auth, of een wachtwoord voor de site.

De embedded kaart: [Google My Maps](https://www.google.com/maps/d/embed?mid=1tMYhOov-lUdzFzvPdeNLQQ5P7MlCr9I&ehbc=2E312F).

## Deploy on GitHub Pages

1. Create a repository on GitHub (e.g. `rotharsteig`) and push this branch:

   ```bash
   git remote add origin https://github.com/<you>/rotharsteig.git
   git push -u origin main
   ```

2. In the repo on GitHub: **Settings → Pages**.

3. Under **Build and deployment → Source**, choose **GitHub Actions** (not “Deploy from a branch”). The included workflow (`.github/workflows/pages.yml`) runs on every push to `main` and publishes the site.

4. After the first workflow run finishes, the site is available at:

   `https://<you>.github.io/rotharsteig/`

   (Use your GitHub username and repo name; the URL is also shown on the successful workflow run and under **Settings → Pages**.)

### Alternative: deploy from the `main` branch (no Actions)

If you prefer not to use Actions: set **Source** to **Deploy from a branch**, branch **main**, folder **/** (root). GitHub will serve `index.html` from the repo root. You can delete `.github/workflows/pages.yml` if you use this.