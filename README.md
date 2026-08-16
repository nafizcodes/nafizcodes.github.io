# Nafiz Imtiaz — Portfolio

Single-file portfolio site. Everything (HTML, CSS, JS) lives in `index.html` — no build step, no dependencies.

```
index.html                 the whole site
Nafiz_Imtiaz_Resume.pdf    linked from the Résumé button
```

## Publish on GitHub Pages

1. Create a repo named **`nafizcodes.github.io`** (using your exact GitHub username makes the URL `https://nafizcodes.github.io` with no subpath).
2. Upload `index.html` and `Nafiz_Imtiaz_Resume.pdf` to the root of that repo — either drag-and-drop in the browser, or:

   ```bash
   git init
   git add .
   git commit -m "portfolio"
   git branch -M main
   git remote add origin https://github.com/nafizcodes/nafizcodes.github.io.git
   git push -u origin main
   ```

3. Repo → **Settings → Pages** → Source: *Deploy from a branch*, Branch: `main` / `root` → Save.
4. Live in ~1 minute at `https://nafizcodes.github.io`.

If you name the repo something else (e.g. `portfolio`), the URL becomes `https://nafizcodes.github.io/portfolio/` — the site still works, since all links are relative.

### Custom domain (optional)

Buy a domain, add a file named `CNAME` containing just the domain (e.g. `nafizimtiaz.dev`), then point DNS at GitHub:

- `A` records for `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- `CNAME` record for `www` → `nafizcodes.github.io`

Then set the domain under Settings → Pages and enable *Enforce HTTPS*.

## Editing

- **Copy** — plain text in the HTML body, edit in place.
- **Colors** — the `:root` block at the top of the `<style>` tag. `--accent` is the green; `html[data-theme="dark"]` holds the dark palette.
- **Add a project** — copy an `<article class="card reveal">` block and change the contents.
- **Add a section** — add a `<section id="name">`, then add a matching `<li><a class="link" href="#name">` to the nav. Scroll-spy and reveal animations pick it up automatically.

## Notes

- Fonts load from Google Fonts (Newsreader for headings, Inter for body, JetBrains Mono for dates/tags). If you'd rather not depend on that, delete the two `<link>` tags — the system-font fallbacks still look reasonable.
- Dark mode follows the OS setting on first visit and remembers the toggle afterwards.
- Preview locally by opening `index.html` in a browser, or run `python3 -m http.server` in this folder.
