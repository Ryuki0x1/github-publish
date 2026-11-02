---
name: github-publish
description: Publish current project to GitHub with UI-only screenshots, SEO README, and discovery tags
---

# /github-publish

Publish the current project to GitHub using the **github-publish** skill.

This command runs the full publish routine:

1. 📸 Captures **UI-only** screenshots (via `readme-screenshots`)
2. 🎨 Adds a fake/demo background visual
3. 🔍 Writes an SEO-optimized README (title, pitch, badges, features, install, usage, license)
4. 🏷️ Adds GitHub topics/tags + repository description for discovery
5. 📦 Commits, pushes to `main`, and optionally creates a tag/release

## Usage

Type `/github-publish` in any project folder you want to ship to GitHub.

## Prerequisites

- `readme-screenshots` skill installed (for automated UI screenshots)
- `git` installed
- `gh` (GitHub CLI) optional — auto-creates the repo, adds topics, and makes a release

> If `readme-screenshots` isn't installed, the skill falls back to manual screenshots.<br>
> If `gh` isn't installed, create the repo manually on GitHub.com and push via git.

## What to expect

The agent will walk through each step and report back the repo URL, topics/tags, and README location when done.
