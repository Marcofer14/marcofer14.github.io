# Marco Fernández — Portfolio

Personal portfolio site. A single static page: plain HTML, CSS and a little JavaScript. No build step and no dependencies.

**Live:** https://marcofer14.github.io

## Structure

```
portfolio/
├── index.html      # the whole site: markup, styles and scripts
├── photos/         # images for the "Wanna know more about me?" button (resized, metadata stripped)
├── cv.pdf          # public CV shown by the "View CV" viewer (no phone number)
├── .nojekyll       # tells GitHub Pages to serve files as-is
└── README.md
```

## Run locally

Any static server works. With Python:

```bash
python -m http.server 5173
```

Then open http://localhost:5173.

## Editing content

Everything lives in `index.html`:

| What | Where |
|---|---|
| Bio, links | `<!-- ═════════ Hero ═════════ -->` section |
| Projects | `<!-- ─── Projects ─── -->` section, one `<article class="proj">` per project |
| Tech stack and skill levels | `STACK` array in the script (`3` = daily / production, `2` = proficient, `1` = working knowledge) |
| Photos and captions | `PHOTOS` array in the script; image files go in `photos/` |
| CV | `cv.pdf` (public copy without phone number). If it's missing, the viewer shows a "coming soon" note |

## Deploy (GitHub Pages)

1. Create a **public** repo on GitHub named `marcofer14.github.io`. Don't add a README, license or .gitignore.
2. Push this folder:

   ```bash
   git remote add origin https://github.com/Marcofer14/marcofer14.github.io.git
   git push -u origin main
   ```

3. On GitHub, go to **Settings → Pages → Build and deployment** and set:
   - Source: **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)**
4. After a minute the site is live at https://marcofer14.github.io. Every push to `main` redeploys it.

Alternatives: drag the folder into Netlify Drop, or import the repo in Vercel or Cloudflare Pages. No build settings are needed; the output directory is the repo root.

## Analytics

[GoatCounter](https://www.goatcounter.com) counts visits without cookies: pages, referrers (LinkedIn, GitHub…), countries, browsers and screen sizes. It does not identify individual visitors.

1. Create a free account at goatcounter.com with the code `marcofer14`. If you choose another code, update the `data-goatcounter` URL at the end of `index.html`.
2. The dashboard lives at https://marcofer14.goatcounter.com.
3. The portfolio link in the CV PDFs points to `https://marcofer14.github.io/?ref=cv`, so visits coming from the CV show up with `cv` as the referrer.

Visits from `localhost` are not counted.
