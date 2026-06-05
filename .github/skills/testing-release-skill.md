# Testing and Release Skill

When preparing a release:

- Keep build command strict (`tsc -b && vite build`).
- Run lint, unit tests, and Playwright integration tests before release.
- Prefer unit tests for domain utilities and logic-heavy functions.
- Add end-to-end tests only for critical journeys.
- Make version and build metadata visible in artifacts when useful.
- Treat all warnings as blocking failures.
- Keep fixing until build/lint output has zero warnings.
- Validate main routes in browser and require zero JavaScript console errors.
- Use Playwright as required browser validation baseline.
- Use Chrome DevTools MCP only when deeper browser diagnostics are needed.
- Check required tool availability on the machine before running validation.
- Treat missing or failing unit/integration tests as a release blocker.
- Require tests to be run as part of the build/release gate.
- For AI-enabled apps, verify OpenRouter integration behavior (success/error path) with tests.
- For AI-enabled apps, verify agreed conversation history retention behavior in tests.
- For AI-enabled apps, verify secrets are deployment-scoped (GitHub Secrets/Variables) and not committed in `.env`.

## Checklist

- Does strict TypeScript build pass?
- Does lint pass with no unused imports?
- Are core logic paths covered by tests?
- Are both unit and Playwright integration tests present and passing?
- Is deploy configuration compatible with chosen routing strategy?
- Are build and lint outputs warning-free?
- Were key screens opened in browser with zero console errors?
- Was Playwright available and executed for browser validation?
- For AI-enabled apps, were OpenRouter flows validated without exposing secrets in client logs or bundles?
