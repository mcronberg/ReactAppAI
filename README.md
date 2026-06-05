# ReactAppAI

A reusable collection of agents and skills for building small React apps in a consistent way.

This kit is extracted from repeated patterns across multiple production-like React projects (finance calculators, case admin, and personal knowledge app).

## Editor target

- This library is designed first for VS Code agent workflows (GitHub Copilot Chat + workspace files).
- The folder layout (`.github/agents/` + `.github/skills/`) is intentionally simple and VS Code-friendly.
- In Claude Code, you can use the same structure by loading these markdown files as role/system guidance and reusing the same flow (architect -> platform -> developer -> reviewer).
- For automatic GitHub Copilot repository behavior in VS Code, use `.github/copilot-instructions.md` and `.github/instructions/*.instructions.md`.
- In this repo, `.github/agents/` and `.github/skills/` are the source library.

## Mandatory first step (prerequisites)

- Before any bootstrap or coding, the AI must verify that Node.js and npm are available.
- If Node.js is missing, the AI must install or guide installation first, then re-verify environment.
- No project scaffolding starts before Node.js and npm are confirmed working.

## Core model

- Agent = role that controls workflow and decisions.
- Skill = concrete coding or review practice used by the agent.

## Included agents

- React App Architect Agent
- React Developer Agent
- React Review Agent
- React Platform Agent

## Included skills

- React Component Skill
- TypeScript Skill
- Tailwind UI Skill
- React Review Skill
- Routing and Hosting Skill
- Form Validation Skill
- Data Access Skill
- Testing and Release Skill
- Domain Logic Skill
- PWA Cache and Update Skill
- SEO Skill
- Browser Validation Skill
- Chart.js Visualization Skill
- PDF Generation Skill
- React App Bootstrap Skill
- Logging Skill
- Versioning and Changelog Skill

## Suggested flow

1. Architect agent designs app purpose, components, data model, file structure, and build order.
2. Platform agent sets base path, router strategy, env vars, and deployment constraints.
3. Developer agent implements features using approved skills.
4. Review agent audits structure, types, state, accessibility, and consistency.

## Folder structure

- .github/agents/
- .github/skills/
- .github/instructions/

## VS Code-first library structure

- Keep each agent in `.github/agents/*.md` so roles are easy to discover and reuse.
- Keep each practice in `.github/skills/*.md` so skills can be mixed per task.
- Keep `README.md` as the single entry point for standards and workflow.

## Cross-project baseline conventions

- React + TypeScript + Vite SPA
- Tailwind CSS utility-first styling
- Strict build pipeline: `tsc -b && vite build`
- ESLint with TypeScript + React Hooks rules
- Zero-warning policy: warnings are treated as failures
- Browser validation required: no JavaScript console errors accepted
- Browser tooling policy: Playwright required baseline, Chrome DevTools MCP optional escalation path
- Route-safe hosting setup for GitHub Pages
- For generated app repos targeting GitHub Pages, deploy is managed by GitHub Actions workflow (`.github/workflows/deploy.yml`)
- Domain logic isolated in pure utility modules
- Form-heavy pages use react-hook-form pattern
- Data access isolated through client module + hooks/services
- PWA is default unless developer opts out explicitly
- Cache policy is strict by default: avoid runtime caching
- Release UX should include "new version available" refresh path
- SEO baseline is part of architecture, not optional cleanup
- Responsive design is mandatory across mobile, tablet, and desktop
- Modern and simplified UI style follows finansberegninger2026 direction
- Menus typically use a burger pattern in the top-right corner
- Chart.js is default when charts are required
- PDF export follows finansberegninger2026-style pattern using @react-pdf/renderer and lazy loading
- New apps are bootstrapped from blank Vite React TypeScript with standardized package baseline
- Bootstrap is AI-executed end-to-end; user is only asked for required decisions
- Setup avoids interactive prompts by default and uses non-interactive flow
- If AI writes package.json, dependencies are set to latest stable versions
- Logging is consistent and centralized, enabled on localhost/dev, disabled in release
- Prerequisites gate first: Node.js and npm must be verified before all other steps
- Agents must check required tooling availability on the machine before execution
- Platform/developer flow must create or update GitHub Pages Actions workflow when missing or outdated
- GitHub Pages workflow policy applies to generated app repos, not this library repo
- Default version track is `0.minor.patch` unless otherwise specified
- Minor is bumped for larger changes by default
- Version is initialized or bumped only when the user explicitly requests it
- `CHANGELOG.md` is always present and updated for meaningful changes
- AI can suggest commit messages, but commit/push/sync are always performed by the user
- Design correctness is validated in browser with visual evidence (screenshot/snapshot)
