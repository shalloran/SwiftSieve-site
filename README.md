# SwiftSieve Site

A small, static marketing site for SwiftSieve, a lightweight iOS app for system-wide DNS filtering using Apple’s DNS Proxy API.

This site is designed to be served as plain static files (no build step) from GitHub Pages, Vercel, or similar, and mapped to `swiftsieve.com`.

## Structure

- `index.html` – landing page with hero, how-it-works, key features, and links to the GitHub repo and a placeholder App Store button.
- `security.html` – explains the security model and what SwiftSieve does (and does not) do.
- `privacy.html` – human-readable privacy summary with a link to the authoritative `privacy.md` in the app repo.
- `faq.html` – common questions and answers, with links back to the security and privacy pages.
- `styles.css` – shared dark-theme styling used by all pages.

There is no JavaScript framework; the only JavaScript present is a one-liner to keep the footer year up to date.

## Local testing

You can open `index.html` directly in a browser, or run a tiny static server if you prefer:

```bash
cd /path/to/SwiftSieve-site
python3 -m http.server 8000
```

Then visit `http://localhost:8000/` in your browser.

## GitHub Pages deployment

1. Create (or use) a GitHub repository for this site and push these files to it.
2. In the repository’s **Settings → Pages**:
   - Set **Source** to the `main` branch.
   - Use the root (`/`) as the site folder.
3. After GitHub builds the site, you will get a `https://<user>.github.io/<repo>/` URL.
4. To use `swiftsieve.com`:
   - In GitHub Pages settings, set the **Custom domain** to `swiftsieve.com`.
   - In your DNS provider, create an `A` or `CNAME` record as instructed by GitHub Pages for the custom domain.

GitHub will issue and manage TLS for the custom domain once DNS is set up correctly.

## Vercel deployment

1. Create a new Vercel project and connect it to the GitHub repository containing this site.
2. Use the default framework preset of **“Other”** / static site.
3. Leave the build command and output directory empty so Vercel serves the repository root as static assets.
4. After the first deployment, you will get a `https://<project>.vercel.app/` URL.
5. In the project’s **Domains** settings, add `swiftsieve.com` and follow Vercel’s DNS instructions (usually a CNAME or A record).

Vercel will handle TLS certificates for `swiftsieve.com` once DNS is pointed correctly.

## Updating the App Store link

The landing page currently shows an “App Store coming soon” badge with a placeholder link.

When the App Store listing is live:

1. Open `index.html`.
2. Search for the note:
   - `when the app store link is live, replace this button’s URL with your listing.`
3. Replace the `href="#"` on the App Store button with the real App Store URL.

Commit and redeploy, and the landing page will now link directly to the live App Store entry.***
