# Copilot Instructions (Repository)

This repository is VS Code + GitHub Copilot first.

## Source of truth

- Agent role definitions live in `.github/agents/`.
- Skill definitions live in `.github/skills/`.
- This file and `.github/instructions/*.instructions.md` are the auto-loaded compatibility layer for Copilot.

## Required workflow

1. Use Architect perspective for structure decisions.
2. Use Platform perspective for hosting, PWA/cache, and SEO constraints.
3. Use Developer perspective for implementation.
4. Use Reviewer perspective for quality gates.

## Hard quality gates

- Zero warnings in lint/build.
- Browser validation required with zero JavaScript console errors.
- Responsive behavior required (mobile/tablet/desktop).
- Playwright is required baseline for browser validation.
- Chrome DevTools MCP is optional escalation path.
- Setup flow must avoid interactive prompts and use non-interactive commands.
- If AI creates/rewrites package.json, use latest stable package versions.
- Design must be validated in browser with screenshot/snapshot evidence.

## Prerequisites gate

- Verify Node.js and npm before any scaffold/build actions.
- If missing, resolve prerequisites first.

## Versioning and git policy

- Use `0.minor.patch` as default version scheme unless otherwise specified.
- Bump minor for larger changes by default.
- Initialize or bump version only when the user explicitly requests version bump.
- Keep `CHANGELOG.md` present and updated.
- AI may suggest commit messages.
- User performs all commit/push/sync actions.
