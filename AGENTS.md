# Linky

Linky is the agent workflow for this static linktree homepage.

## Project

- Local folder: `/Users/baeseoyeon/Downloads/0706_link`
- GitHub remote: `https://github.com/8aeseo-ux/linktree.git`
- Branch: `main`
- Entry file: `index.html`
- Main stylesheet: `style.css`

## Editing Rules

- Keep the site static with plain HTML, CSS, and small inline JavaScript.
- Preserve Korean filenames and links unless the user explicitly asks to rename them.
- Do not commit `.DS_Store`, FTP passwords, tokens, or private deployment notes.
- For homepage changes, inspect `index.html` and `style.css` first.
- If adding links, copy the existing `a.link-card` pattern and keep labels concise.

## Git Deploy Flow

1. Check status: `rtk git status -sb`
2. Review changes: `rtk git diff`
3. Stage intended files only.
4. Commit with a short message describing the homepage update.
5. Push to GitHub: `git push -u origin main`

## FTP Deploy Flow

FTP upload should happen after GitHub push succeeds.

Required details:

- FTP host
- FTP username
- FTP password
- Remote directory

Use environment variables or an interactive prompt for secrets. Do not write the FTP password into repo files or documentation.

Default upload exclusions:

- `.git/`
- `.DS_Store`
- `AGENTS.md` unless the user wants this file public

With macOS default tools, use `curl --ftp-create-dirs -T` for each file. If `lftp` is installed, `mirror -R` is acceptable.
