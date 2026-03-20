# Blueprint — Projects Page

**Live:** [tcavanahbp.github.io](https://tcavanahbp.github.io/)

A branded GitHub repository index for the Blueprint Equity Stack. Fetches repos live from the GitHub API and displays them in a clean, searchable list styled with the Blueprint brand system.

## What It Does

- Pulls all public repos for a configured GitHub username via the GitHub API
- Sorts repos with GitHub Pages sites to the top, then by most recently pushed
- Live search/filter by repo name or description
- Links out to the live GitHub Pages site if one exists, otherwise to the repo itself
- Fully static — no build step, no dependencies, just an `index.html`

## Setup

1. Clone or fork this repo
2. Open `index.html` and update the config block near the bottom of the `<script>` tag:

```js
const USERNAME     = 'your-github-username';
const DISPLAY_NAME = 'Your Display Name';   // shown in the page header
const TAGLINE      = 'Your tagline here';   // shown under the header
const HIDE_PAGES_REPO = true;               // hides the username.github.io repo from the list
```

3. Commit and push — if GitHub Pages is enabled on this repo, the page will be live at `https://your-username.github.io/`

## Deploying to GitHub Pages

1. Go to **Settings → Pages** in your repo
2. Set the source to **Deploy from a branch**
3. Select `main` (or `master`) and `/ (root)`
4. Save — your page will be live within a few minutes

## Brand

Built using the Blueprint brand system:

- **Fonts:** Montserrat Bold (headings) · Lato (body) via Google Fonts
- **Colors:** Charcoal `#3F454A` · Blueprint Blue `#3979F9` · Periwinkle `#CEDEFD` · Steel Blue `#B4C4E3`
- No build tools, preprocessors, or external UI frameworks required

## Notes

- The GitHub API allows up to 60 unauthenticated requests per hour per IP. For a personal projects page this is more than sufficient.
- To show private repos, you would need to proxy requests through a backend with a personal access token — this page intentionally keeps things simple and public-only.
