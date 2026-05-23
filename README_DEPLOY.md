# TAME PulseHalo Legal Site Deploy

Date: 2026-05-23

This folder is the GitHub Pages-ready legal/support site for `TAME PulseHalo`.

## Target Repository

Recommended repository:

`pengpengemail-prog/tame-pulsehalo-app-info`

Recommended public URLs after Pages is enabled:

- Home / Marketing URL: `https://pengpengemail-prog.github.io/tame-pulsehalo-app-info/`
- Privacy Policy URL: `https://pengpengemail-prog.github.io/tame-pulsehalo-app-info/privacy-policy.html`
- Support URL: `https://pengpengemail-prog.github.io/tame-pulsehalo-app-info/support.html`
- Terms URL: `https://pengpengemail-prog.github.io/tame-pulsehalo-app-info/terms-of-use.html`

## Files To Publish

- `index.html`
- `support.html`
- `privacy-policy.html`
- `terms-of-use.html`
- `style.css`
- `.nojekyll`

The `.md` files are included as source copies, but the App Store URLs should point to the `.html` pages.

## One-Time GitHub Publish Flow

Preferred local wrapper:

```bash
/Users/pengpeng/Desktop/codex工作区/PulseHalo/LegalWeb/publish_pages.sh
```

The wrapper checks GitHub CLI login, creates or uses `pengpengemail-prog/tame-pulsehalo-app-info`, pushes this site folder, enables Pages, and verifies the four public URLs.

Run after GitHub CLI login is available:

```bash
cd /Users/pengpeng/Desktop/codex工作区/PulseHalo/LegalWeb/site
gh repo create pengpengemail-prog/tame-pulsehalo-app-info --public --source=. --remote=origin --push
gh api -X POST /repos/pengpengemail-prog/tame-pulsehalo-app-info/pages -f source='{"branch":"main","path":"/"}'
```

If the repository already exists:

```bash
cd /Users/pengpeng/Desktop/codex工作区/PulseHalo/LegalWeb/site
git init
git branch -M main
git remote add origin git@github.com:pengpengemail-prog/tame-pulsehalo-app-info.git
git add .
git commit -m "Publish TAME PulseHalo app info site"
git push -u origin main
```

Then enable GitHub Pages in repository settings if the API command was not used:

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/`

## App Store Connect Fields

Replace current GitHub blob URLs with:

- Privacy Policy URL: `https://pengpengemail-prog.github.io/tame-pulsehalo-app-info/privacy-policy.html`
- Support URL: `https://pengpengemail-prog.github.io/tame-pulsehalo-app-info/support.html`
- Marketing URL: `https://pengpengemail-prog.github.io/tame-pulsehalo-app-info/`

After publishing, verify each URL returns HTTP `200` before using it in App Store Connect.
