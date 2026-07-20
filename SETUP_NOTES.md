# Setup notes

This is a Minimal Mistakes Jekyll site scaffold, set up to run on GitHub Pages
via `remote_theme` (no local Ruby install needed for GitHub to build it).

## To deploy

1. Copy all these files into your `cnmillar.github.io` repo, replacing the
   existing boilerplate (`_layouts/`, `assets/css/`, old `README.md`,
   `index.md.html`, and the dinky-theme `_config.yml` can all be deleted).
2. Commit and push to `main`.
3. In the repo's Settings → Pages, confirm the source is set to the `main`
   branch, root folder. GitHub will build it automatically — first build can
   take a few minutes.
4. Visit `https://cnmillar.github.io` to confirm it's live.

## Still needs your input

- **`_config.yml`**: replace `YOUR-LINKEDIN-HANDLE` (appears 3 times) with your
  actual LinkedIn URL slug.
- **Avatar**: drop a headshot into `assets/images/avatar.jpg` (referenced in
  `_config.yml` under `author.avatar`). Site will work without it, just no
  photo in the sidebar.
- **Case studies**: both files in `_case_studies/` are drafts with placeholder
  sections. Replace with the real write-ups once drafted, and run each past
  Erin if it touches Indiegraf-specific business framing (the data strategy
  one especially).
- **Custom domain (optional)**: if you decide to point `caitlinhavlak.com` at
  this site later, add a `CNAME` file to the repo root containing just the
  domain, and update the `url` field in `_config.yml` to match.

## Structure

- `index.md` — home page / positioning statement
- `_pages/about.md` — bio page
- `_pages/case-studies.md` — auto-generated list of case studies
- `_case_studies/*.md` — the two case study drafts
- `_data/navigation.yml` — top nav bar links
