---
name: github-publish
description: Publish a project to GitHub with a polished, SEO-optimized README. Use this whenever the user wants to ship a repo to GitHub — especially phrases like "publish it on github", "push this to github", "put it on github with a readme", or "do the necessary with readme screenshots and tags". The skill captures the full routine: UI-only screenshots (via readme-screenshots), a fake/demo background visual, an SEO-friendly README (title, one-line pitch, keywords, badges, features, install, usage, license), GitHub topics/tags for discovery, and the git push/release steps. Prefer this skill over ad-hoc publishing because it standardizes the README structure, screenshot scope, and tagging every time.
compatibility: Requires git and (optionally) the `gh` CLI. Works best when a UI/demo exists to screenshot.

## Prerequisite skills (install these first)

This skill delegates to other skills. Before using `github-publish`, make sure these are installed:

- **`readme-screenshots`** — used in Step 1 to capture UI-only screenshots. Install it first if you want automated screenshots.
- If `readme-screenshots` is not available, the skill falls back to manual screenshots (see Step 1).

No other skills are required. The git/push steps use your system's `git` and optionally the `gh` CLI.
---

# Skill: github-publish

Publish a project to GitHub with a repeatable, SEO-friendly routine. This skill turns your "now publish it on GitHub" request into a standardized set of steps so you never have to restate the screenshot/screenshot-background/tags/SEO checklist again.

## When to trigger

Use this skill when the user asks to publish/push/ship a project to GitHub and wants:
- README screenshots of the UI only (no background noise)
- A fake/demo background visual (placeholder/hero)
- SEO keywords for discovery
- GitHub topics/tags
- Commit, push, and (optionally) a release/tag

Trigger phrases include: "publish it on github", "push this to github", "put it on github with readme", "do the necessary with readme screenshots and tags", "ship this repo", "make it discoverable on github".

## What this skill does, in order

1. **Capture UI-only screenshots** — delegate to the `readme-screenshots` skill to take screenshots of the UI only. Do not include background/desktop noise; crop tightly to the application window.
2. **Add a fake/demo background** — create a placeholder demo visual (hero image or short animated GIF placeholder) to use as the README background/header when no real demo video exists.
3. **Write an SEO-optimized README** — include:
   - Clear project title
   - One-line pitch (keyword-rich, under ~60 chars)
   - Short description with discovery keywords
   - Badges (license, version, stars, etc.)
   - Features list
   - Installation & usage
   - License
4. **Add GitHub discovery metadata** — repository description, topics/tags, and README keywords so the repo surfaces in search.
5. **Publish** — `git init`, `git add`, `git commit`, `git push`; create the GitHub repo (via `gh` CLI if available), add topics/tags, and create a release/tag.

## Step-by-step instructions

### 1. Screenshots (UI only)

Run the `readme-screenshots` skill and instruct it to capture **only the UI**. Save the outputs to a folder such as `docs/screenshots/` or `assets/screenshots/`. Name them descriptively (e.g., `dashboard.png`, `settings-modal.png`).

If `readme-screenshots` is not available, take manual screenshots and crop tightly to the app window.

### 2. Fake/demo background

When there is no real demo video, create a placeholder:

- **Option A (quick):** a solid-color hero banner with the project name and a one-line tagline (1200 × 400 px).
- **Option B (animated):** a short looping GIF placeholder showing mock UI states.

Save to `docs/demo.gif` or `assets/hero.png`. Reference it at the top of the README.

### 3. SEO-optimized README

Use this exact structure. Replace bracketed placeholders.

```markdown
# [Project Name]

[One-line pitch, keyword-rich, ≤60 characters]

[Short 1–2 sentence description with discovery keywords]

![Demo or UI screenshot](./docs/demo.gif)

## Badges

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](#)
[![Stars](https://img.shields.io/github/stars/[user]/[repo]?style=social)](https://github.com/[user]/[repo])

## Features

- [Feature 1]
- [Feature 2]
- [Feature 3]

## Installation

```bash
git clone https://github.com/[user]/[repo].git
cd [repo]
# install steps here
```

## Usage

```bash
# usage example
```

## Screenshots

![UI screenshot](./docs/screenshots/dashboard.png)

## License

[MIT](LICENSE)
```

SEO rules:
- Put the primary keyword in the title and first paragraph.
- Use alt text on every image (`![Dashboard UI](./docs/screenshots/dashboard.png)`).
- Include synonyms and related terms naturally in the description and features.
- Keep the one-line pitch under 60 characters for search-result previews.

### 4. GitHub discovery metadata

- **Repository description:** one sentence, keyword-rich.
- **Topics/tags:** 5–10 relevant tags (e.g., `javascript`, `react`, `ui-kit`, `demo`, `template`, `opensource`).
- **README keywords:** sprinkle 3–6 discovery keywords in the body (not stuffed).

### 5. Publish to GitHub

```bash
git init
git add .
git commit -m "feat: initial release with README and UI screenshots"
git branch -M main
git remote add origin https://github.com/[user]/[repo].git
git push -u origin main
```

If `gh` is available:

```bash
gh repo create [user]/[repo] --public --source=. --remote=origin
gh repo edit [user]/[repo] --description "[one-line pitch]" --add-topic tag1 --add-topic tag2 --add-topic tag3
gh release create v1.0.0 --title "v1.0.0" --notes "Initial release"
```

If `gh` is not available, create the repo manually on GitHub.com, add topics/tags in repo settings, and push via the remote URL above.

## Output checklist

Before finishing, confirm:
- [ ] UI-only screenshots saved (no background noise)
- [ ] Fake/demo background visual present
- [ ] README follows the SEO structure above
- [ ] Repository description set
- [ ] Topics/tags added (5–10)
- [ ] Code committed and pushed to `main`
- [ ] Release/tag created (optional)

## Example invocation

User: "publish it on github do the necessary with skills like readme-screenshots taking only screenshots of the ui and fake demo for background, and putting tags and good seo for discovery"

Agent response: follow Steps 1–5 above, then report the repo URL, topics, and README location.
