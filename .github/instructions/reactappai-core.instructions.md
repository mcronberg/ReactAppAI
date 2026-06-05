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

Implementation standards:

- React + TypeScript + Vite baseline.
- Tailwind UI with responsive-first design.
- Chart.js default for charts.
- @react-pdf/renderer default for PDF generation.
- Centralized logging with `loglevel`, enabled in localhost/dev, disabled in release.
- PWA default unless explicitly disabled by developer decision.
- Strict cache policy and update notification pattern.
