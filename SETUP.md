# One-time setup

This repo is the GitHub profile README for `rakshitsoni02`. The stats card
(`dark_mode.svg` / `light_mode.svg`) is regenerated daily by
`.github/workflows/update-readme.yml` running `today.py`.

## 1. Push this repo

The old website files were moved to the `rakshitsoni02.github.io` repo, so this
repo now only holds the profile README. From this directory:

```bash
git remote add origin https://github.com/rakshitsoni02/rakshitsoni02.git
git push -f origin main
```

(`-f` is intentional: it replaces the old website-repo history. The website
lives on in `rakshitsoni02.github.io`.)

## 2. Create the ACCESS_TOKEN secret

The workflow needs a personal access token (the default `GITHUB_TOKEN` can't
read your other repos' commit history):

1. Go to <https://github.com/settings/tokens?type=beta> → *Generate new token* (fine-grained).
2. Repository access: **All repositories**.
3. Permissions — Account: `Followers (read)`, `Starring (read)`, `Watching (read)`.
   Repository: `Contents (read)`, `Metadata (read)`, `Commit statuses (read)`.
4. Copy the token, then in this repo: *Settings → Secrets and variables →
   Actions → New repository secret*, name it `ACCESS_TOKEN`.

## 3. Run it

*Actions → Update profile stats → Run workflow.* It also runs daily at 06:00 UTC.

## Tweaks

- **Career start date** (the `Uptime` line): `CAREER_START` in `today.py`.
- **Any text on the card**: edit both SVG files (keep the `id="..."` tspans —
  the script rewrites those).
- The `cache/` folder makes daily runs fast (only changed repos are re-counted).
  Commit it.
