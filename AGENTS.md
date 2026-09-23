# Repository Guidelines

## Project Structure & Module Organization

This is a static, Russian-language browser prototype for turning handwritten planner entries into Google Calendar events. `index.html` contains the interface, `style.css` contains layout and responsive styles, and `app.js` handles state, OCR, commands, and Calendar API calls. `README.md` documents setup, privacy, and current limitations. There are no separate asset or test directories; keep new files at the repository root unless a clear module boundary warrants a directory.

## Build, Test, and Development Commands

- `python3 -m http.server 8765`: serve the site locally at `http://localhost:8765`. Use this origin when testing Google OAuth.
- `node --check app.js`: check JavaScript syntax without running browser code.

There is no package manager, build step, or automated test command. Opening `index.html` directly is enough for basic interface work, but Google OAuth requires an authorized HTTP or HTTPS origin.

## Coding Style & Naming Conventions

Use plain HTML, CSS, and browser JavaScript; avoid adding a framework for small changes. Follow existing two-space HTML indentation and the current semicolon-free JavaScript style. Use `camelCase` for variables and functions, descriptive IDs in HTML, and lowercase CSS class names. Keep user-facing text in Russian. Escape event text before inserting it into HTML; `app.js` provides `esc()` for this purpose. No formatter or linter is configured.

## Testing Guidelines

Run `node --check app.js` after JavaScript edits. Manually check week navigation, draft creation and editing, confirmation dialogs, and narrow-screen layout in a browser. When changing Google or OCR behavior, test with a real OAuth Client ID or representative photo and record what could not be verified. No coverage target or test naming convention exists yet; if adding automated tests, document their command and use behavior-based names.

## Commit & Pull Request Guidelines

The only existing commit is `Initial paper calendar prototype`, so there is no established message format. Use short, imperative commit subjects that describe the change. In pull requests, summarize behavior, list manual checks, link any relevant issue, and include screenshots for visual changes. Note any Google OAuth, Calendar API, or OCR checks that require external setup.

## Security & Configuration

Never commit OAuth client secrets, access tokens, personal photos, or calendar data. The browser stores drafts and the public OAuth Client ID in `localStorage`; access tokens remain in memory. Review changes to data storage or external requests against the privacy notes in `README.md`.
