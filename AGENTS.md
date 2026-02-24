## Cursor Cloud specific instructions

This is a plain static HTML/CSS site with no build step, no package manager, and no runtime dependencies. See `README.md` for the project structure.

### Dev server

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000/`. All pages (`index.html`, `security.html`, `privacy.html`, `faq.html`) are served as static files.

### Linting

Use `tidy -q -e <file>.html` to check HTML validity. The SVG `fill` attribute warnings are expected and harmless (valid HTML5, older tidy version).

### Notes

- There is no JavaScript framework, test suite, or build pipeline. The only JS is a one-liner setting the footer year.
- The site is deployed via GitHub Pages with a custom domain (`swiftsieve.com`) configured in the `CNAME` file.
