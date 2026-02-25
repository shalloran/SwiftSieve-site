# SwiftSieve Site

A small, static marketing site for SwiftSieve, a lightweight iOS app for system-wide DNS filtering using Apple’s DNS Proxy API.

This site is designed to be served as plain static files (no build step) from GitHub Pages for the custom domain: `swiftsieve.com`.

## project struct

- `index.html` – landing page with hero, how-it-works, key features, and links to the GitHub repo and the Building guide (SwiftSieve is not on the App Store due to DNS proxy API limitations).
- `building.html` – step-by-step guide to building and installing SwiftSieve from source in Xcode.
- `security.html` – explains the security model and what SwiftSieve does (and does not) do.
- `privacy.html` – human-readable privacy summary with a link to the authoritative `privacy.md` in the app repo.
- `faq.html` – common questions and answers, with links back to the security, privacy, and building pages.
- `styles.css` – shared dark-theme styling used by all pages.

There is no JavaScript framework. The only JavaScript present is a one-liner to keep the footer year up to date.

## local testing

You can open `index.html` directly in a browser, or run a tiny static server if you prefer:

```bash
cd /path/to/SwiftSieve-site
python3 -m http.server 8000
```

Then visit `http://localhost:8000/` in your browser.

## reach out

Reach out to [support@swiftsieve.com](mailto:support@swiftsieve.com) if you have any questions or want to collaborate!