# Muhammad Talha — Portfolio

A fast, static portfolio site. No build step, no dependencies, no server needed.

## Open it
Double-click `index.html`. It works straight from your computer.

## Put it online (free): GitHub Pages
1. Create a GitHub repository. Naming it `talha-dotdev.github.io` gives you the address https://talha-dotdev.github.io/
2. Upload everything in this folder (keep the `assets` folder next to `index.html`).
3. In the repository: Settings → Pages → Deploy from branch → `main` → Save.

## One step to finish before sharing (SEO and link previews)
Replace `YOUR-DOMAIN.com` with your real address in these files, using Find & Replace:
- `index.html` (4 places: canonical, og:url, og:image, twitter:image)
- `robots.txt`
- `sitemap.xml`

Example: if the site will live at https://talha-dotdev.github.io, replace `https://YOUR-DOMAIN.com` with `https://talha-dotdev.github.io`.
Until you do this, search engines and LinkedIn/WhatsApp link previews will not pick up the page correctly.

## Edit your details
Open `index.html` and search for `const SITE = {` (near the top of the script). Everything you will want to change is there:
- `email`, `whatsapp` (digits only, with country code), and `links` (GitHub, LinkedIn, Fiverr, Upwork). Empty entries are hidden automatically.
- `klyvero.url`: add the live Klyvero website address to show a "View Klyvero ERP" link to it.
- `projects`: name, description, goal, what you built, technologies, live link and GitHub link for each website.
- To change a screenshot, replace the file in `assets/` with a new `.webp` of the same name (recommended 1440 × 900).

## Files
- `index.html`: the whole site
- `assets/`: screenshots and the social share image (`og-image.jpg`, 1200 × 630)
- `robots.txt`, `sitemap.xml`: search engine files
