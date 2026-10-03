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

## The portfolio assistant (chat button, bottom right)
A helper that answers visitors' questions about you, your projects, Klyvero ERP and your services, and walks them through a short project inquiry.

**How it works**
- It is rule-based, not a generative AI. Every answer is built from the information already in this page (your `SITE` settings and the knowledge base at the top of the assistant code), so it cannot invent facts. When it doesn't know something, it says so and points to your contact options.
- It needs no server, no API key, and costs nothing. Nothing a visitor types is stored or sent anywhere.
- The project inquiry cannot be sent by the website itself. At the end the visitor chooses WhatsApp or email; their phone or email app opens with the details already filled in, and **they** press send. The assistant says this plainly, and never claims anything was sent.
- It uses your contact details from `SITE` (`email`, `whatsapp`, `links`). Change them there and the assistant follows.

**Keeping it accurate**
- Project answers come from `SITE.projects`, so editing a project updates what the assistant says about it.
- Wording about services, the process, the technology list and Klyvero is in the knowledge base (`const KB`) and in the `A = {` answers inside the assistant code (search for `PORTFOLIO ASSISTANT`). If you add a service or a Klyvero module, update it there too.

**Optional: AI answers for open-ended questions (not enabled)**
Set `SITE.assistant.endpoint` to a backend you control. When a visitor asks something the built-in knowledge can't answer, the page sends `POST {"message": "...", "history": [{"role": "user"|"assistant", "text": "..."}]}` and expects `{"reply": "..."}` (max 1,500 characters; shown as plain text). If the service is down, slow (8 seconds), returns an error, or returns anything else, the visitor simply gets the built-in answer, with a short note.
- Keep your AI provider's key on that backend only (an environment variable). Never put it in this page.
- Give the model the same facts as the knowledge base and tell it to answer only from them, and add rate limiting on the backend.
- Inquiry answers (name, phone, project details) are never sent to the endpoint.
- This hook was tested against a mock server only. No AI provider is connected.

## Files
- `index.html`: the whole site, including the assistant
- `assets/`: screenshots and the social share image (`og-image.jpg`, 1200 × 630)
- `robots.txt`, `sitemap.xml`: search engine files
