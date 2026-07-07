---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
engine:
  id: copilot
  model: gpt-4.1
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: '[mona] '
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use these sources:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot Workflows: https://awesome-copilot.github.com/workflows/

Before drafting updates, web fetch https://awesome-copilot.github.com/workflows/ and use it as a source.

Update `site/content/github-info.md` with concise, practical updates for readers.
Include source context when the content comes from the GitHub Blog or GitHub Changelog.

Open a pull request for Mona to review. Use a pull request title that mentions Mona or GitHub Info.
Do not write directly to `main`; rely on `safe-outputs` with `create-pull-request`.
