# Logging Skill

When implementing frontend logging in React apps:

- Use `loglevel` as the default logging package.
- Route all logs through a shared logger module (for example `src/lib/logger.ts`).
- Enable logs only in localhost/development by default.
- Disable logging output in production/release builds.
- Use consistent levels: `trace`, `debug`, `info`, `warn`, `error`.
- Use structured messages with context objects where relevant.
- Never log secrets, tokens, personal data, or sensitive payloads.

## Recommended pattern

- Centralize logger setup in one module.
- Derive logging enablement from environment and host checks.
- Export small helpers per domain (for example `logApi`, `logAuth`, `logUi`).
- Keep error logs actionable and include stable identifiers where possible.

## Checklist

- Is `loglevel` used instead of ad-hoc `console.log` calls?
- Is all logging gated to localhost/development by default?
- Is release output free of debug/info logs?
- Are log levels used consistently?
- Are sensitive fields excluded or redacted?
