# Ahmed Abdelnabi — Portfolio

A single-page portfolio site built from scratch with plain HTML, CSS, and JavaScript — no framework, no build step. Design concept: an "operations dashboard" for a backend/DevOps engineer, with the skills section laid out as an actual stack diagram (infrastructure at the base, languages on top).

## What's inside

```
.
├── index.html              # all page content
├── css/style.css           # design tokens + styles
├── js/script.js            # mobile nav, scroll-reveal, footer year
├── assets/
│   └── Ahmed_Abdelnabi_Resume.pdf   # linked from the "Download résumé" button
└── README.md
```

## Run it locally

No build step needed. Either:

- Open `index.html` directly in a browser, or
- Serve it locally so relative paths behave exactly like they will on GitHub Pages:
  ```bash
  python3 -m http.server 8000
  # then visit http://localhost:8000
  ```

## Deploy to GitHub Pages

1. Create a new repository on GitHub (for a user/organization site name it `<your-username>.github.io`; for a project site, any name works).
2. Push these files to the repository root:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. On GitHub, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Under **Branch**, choose `main` and `/ (root)`, then **Save**.
6. GitHub Pages will publish the site at `https://<your-username>.github.io/<repo-name>/` (or `https://<your-username>.github.io/` if the repo is named that way) within a minute or two.

## Customizing

- **Colors, type, spacing** — all defined once as CSS custom properties at the top of `css/style.css` under `:root`. Change a value there and it updates everywhere.
- **Content** — everything is plain text in `index.html`; section order matches the `<nav>` links, so relabeling a section heading and its nav link keeps them in sync.
- **Résumé file** — replace `assets/Ahmed_Abdelnabi_Resume.pdf` with an updated version, keeping the same filename (or update the `href` in the "Download résumé" button in `index.html` if you rename it).
- **Project links** — two of the three project cards don't currently link out to a repo (no public repo was available for those at the time this was built). Add a `<a class="project-link" href="...">View on GitHub ↗</a>` under the tech pills, matching the StudyMentor card, once those repos are public.

## Notes

- Fonts (Space Grotesk, Inter, JetBrains Mono) load from Google Fonts via CDN — no local font files to manage.
- The mobile menu, scroll-reveal animations, and footer year are the only JavaScript on the page; everything degrades gracefully if JS is blocked (content stays fully visible and readable, just without the reveal animation).
