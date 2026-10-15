# RC Beam Lab — educational website

A static interactive class companion connecting **Mechanics of Materials I (2025–2026)** and **Reinforced Concrete Design — ASD Method, Part 1 (2026–2027)**. It preserves the lecture-style working-stress method and includes additional exploratory modules, which are clearly marked when they are not covered by the supplied RC Part 1 notes.

## Open locally
1. Download and extract the ZIP.
2. Open `index.html` in a modern browser.
3. The 3D visualization loads Three.js from a CDN and therefore needs internet access; the rest of the page is static HTML/JavaScript.

## Publish with GitHub Pages
1. Sign in to https://github.com/ and create a repository.
2. Upload `index.html` to the repository root.
3. Open **Settings → Pages**. Choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Open the URL shown by GitHub Pages after deployment completes.

## Publish with Netlify
1. Sign in at https://www.netlify.com/.
2. Create a site using the manual deploy / drag-and-drop option.
3. Upload the extracted folder containing `index.html`.
4. Test the deployed site on desktop and mobile.

## Engineering verification status
**Educational use only—not a certified engineering program.** The main RC ASD example was checked against the uploaded lecture's worked example (printed pages 26–28). The elementary beam cases were checked against standard closed-form values. Several supplementary modules have not been comprehensively validated against a specific code edition or your later lectures. See `ENGINEERING_REVIEW.md` for details and limitations.

## Files
- `index.html` — the website.
- `ENGINEERING_REVIEW.md` — lecture alignment, targeted checks, and remaining limitations.
- `TEST_RESULTS.md` — benchmark values and narrow regression checks.
- `README.md` — setup and publishing instructions.
