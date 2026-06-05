---
applyTo: "**"
---

Follow repository standards from `README.md`, `.github/agents/`, and `.github/skills/`.

Mandatory behavior:

- Use strict TypeScript + ESLint quality gates.
- Treat warnings as failures.
- Continue until warning-free output.
- Validate in browser and require zero JavaScript console errors.
- Verify tool availability on machine before execution (Node/npm, Playwright).
- Use `0.minor.patch` as default versioning unless otherwise specified.
- Only initialize or bump version when user explicitly requests it.
- Keep `CHANGELOG.md` present and updated for meaningful changes.
- Do not run commit/push/sync actions; user performs git operations.
- Avoid interactive scaffolding prompts; use non-interactive setup flow.
- Use OpenRouter as the default AI gateway in generated apps.
- Ask whether conversation history should be included and how much history to retain before implementing AI chat logic.
- Keep OpenRouter credentials in local `.env` and ensure `.env` is git-ignored.
- Never expose `OPENROUTER_API_KEY` in client bundles; use server/edge proxy for production static hosting.
- When output language is Danish, generated text must use proper Danish characters (`æ`, `ø`, `å`) and not transliterated forms (`ae`, `oe`, `aa`) unless explicitly requested.
- Never delete, overwrite, move, or scaffold into `.github/` or any existing top-level folder that contains `.github/`.
- Before any scaffold command, inspect target path. If it is non-empty, scaffold only into a new isolated temp folder (for example `./_scaffold_tmp`) and copy required files selectively. Never run options equivalent to "remove existing files".
- If a command becomes interactive or waits for selection input, cancel immediately and switch to a fully non-interactive path. Do not continue interactive sessions.
- If a reliable non-interactive scaffold command is not available, create a minimal raw `package.json` and required config files manually instead of using interactive generators.
- When AI creates or rewrites package.json, use latest stable dependency versions at generation time.
- Validate design output against expected visual baseline before handoff.

Implementation standards:

- React + TypeScript + Vite baseline.
- Tailwind UI with responsive-first design.
- Chart.js default for charts.
- @react-pdf/renderer default for PDF generation.
- Centralized logging with `loglevel`, enabled in localhost/dev, disabled in release.
- OpenRouter client integration uses latest stable `@openrouter/sdk` when AI writes package.json.
- PWA default unless explicitly disabled by developer decision.
- Strict cache policy and update notification pattern.
- Capture visual validation evidence (screenshots/snapshots) for changed UI.
