# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# Render resume.html from resume.json
npx resumed render --theme jsonresume-theme-full-ext

# Validate resume.json against the JSON Resume schema
npx resumed validate
```

## Architecture

This repo contains a single-file resume managed as a JSON Resume (`resume.json`), rendered to `resume.html` via the `resumed` CLI with the `jsonresume-theme-full-ext` theme.

- **`resume.json`** — the source of truth; follows the [JSON Resume schema v1.0.0](https://raw.githubusercontent.com/jsonresume/resume-schema/v1.0.0/schema.json)
- **`resume.html`** — generated output; regenerate by running the render command above
- **`.github/workflows/gist.yml`** — on push to `main`, automatically syncs `resume.json` to a GitHub Gist (ID: `c08bff4ddd966ac26dd78070fd5b6ab8`) using the `gist_token` secret

All content edits happen in `resume.json`; `resume.html` is a build artifact.
