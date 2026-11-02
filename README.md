# 🚀 github-publish

Publish any project to GitHub with a polished, SEO-optimized README — without rewriting the same checklist every session.

This OpenCode skill automates the repetitive "now publish it on GitHub" routine:

- 📸 **UI-only screenshots** (via `readme-screenshots`) — no desktop/background noise
- 🎨 **Fake/demo background** — placeholder hero image or GIF when you have no real demo
- 🔍 **SEO-friendly README** — keyword-rich title, pitch, badges, features, install/usage, license
- 🏷️ **GitHub topics/tags** — 5–10 discovery tags so your repo shows up in search
- 📦 **Git push & release** — commit, push to `main`, optional tag/release via `gh` CLI

---

## 📦 Prerequisites

Before using this skill, install these:

| Tool / Skill | Why |
|-------------|-----|
| `readme-screenshots` | Takes the UI-only screenshots for your README (Step 1) |
| `git` | Commits and pushes your code |
| `gh` (GitHub CLI) | Optional — creates the repo, adds topics, and makes a release automatically |

> If you don't have `readme-screenshots`, the skill falls back to manual screenshots.  
> If you don't have `gh`, you can create the repo manually on GitHub.com and push via git.

---

## 🛠️ Installation

Add this skill to your OpenCode skills folder:

```
~/.agents/skills/github-publish/
└── SKILL.md
```

Or clone this repo directly into your skills directory:

```bash
git clone https://github.com/Ryuki0x1/github-publish.git ~/.agents/skills/github-publish
```

---

## ▶️ How to use

When you're ready to publish a project, just say:

> "publish it on github do the necessary with readme screenshots and tags"

The skill will:

1. **Screenshot the UI only** — delegates to `readme-screenshots`, saves to `docs/screenshots/`
2. **Add a demo background** — creates a placeholder hero banner or GIF (`docs/demo.gif`)
3. **Write an SEO README** — title, one-line pitch (≤60 chars), keywords, badges, features, install, usage, license
4. **Add GitHub metadata** — repository description + 5–10 topics/tags for discovery
5. **Push to GitHub** — `git init`, `add`, `commit`, `push`, plus optional `gh` repo/topic/release steps

---

## 📋 Output checklist

Before you finish, confirm:

- [ ] UI-only screenshots saved (no background noise)
- [ ] Fake/demo background visual present
- [ ] README follows the SEO structure (title, pitch, keywords, badges, features, install, usage, license)
- [ ] Repository description set on GitHub
- [ ] Topics/tags added (5–10)
- [ ] Code committed and pushed to `main`
- [ ] Release/tag created (optional)

---

## 🧩 Example README the skill generates

```markdown
# My Project

A keyword-rich one-line pitch under 60 characters.

Short description with discovery keywords.

![Demo](./docs/demo.gif)

## Badges

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## Features

- Feature 1
- Feature 2

## Installation

```bash
git clone https://github.com/user/repo.git
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

---

## 🔖 Topics on this repo

`opencode-skill` `github-publish` `readme-screenshots` `seo` `readme` `agent-skill` `publish-to-github` `opencode`

---

## 📄 License

MIT

---

## 🤝 Contributing

PRs welcome! Open an issue to suggest improvements to the README template, topic list, or publish steps.
