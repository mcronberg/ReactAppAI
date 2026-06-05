# Logging Skill

When implementing frontend logging in React apps:

- Use `loglevel` as the default logging package.
- Route all logs through a shared logger module (for example `src/lib/logger.ts`).
- Enable logs only in localhost/development by default.
- Disable logging output in production/release builds.
- Include at least one startup log and one feature/action log in localhost/dev.
- Include error logs for failed user flows with safe context.
- Use consistent levels: `trace`, `debug`, `info`, `warn`, `error`.
- Use structured messages with context objects where relevant.
- Never log secrets, tokens, personal data, or sensitive payloads.

## Required event contract (for Copilot/runtime verification)

Use stable event IDs as message text (do not rename between refactors):

- `APP_START`
- `VIEW_READY`
- `ACTION_SUBMIT`
- `ACTION_SUCCESS`
- `ACTION_ERROR`

Required payload fields:

- `eventId`: same as message text
- `feature`: short feature name (for example `day-calculator`)
- `step`: short step label (for example `submit`, `calculate`, `render`)
- `status`: `start` | `ok` | `error`
- `timestamp`: ISO string

Error event payload also requires:

- `errorCode`: stable short code (for example `INVALID_DATE`)
- `safeMessage`: non-sensitive description

Rules:

- Keep event IDs and payload keys stable for automated checks.
- Add optional fields only; never remove required fields.
- Do not encode user-sensitive values in payload.

## Recommended pattern

- Centralize logger setup in one module.
- Derive logging enablement from environment and host checks.
- Export small helpers per domain (for example `logApi`, `logAuth`, `logUi`).
- Keep error logs actionable and include stable identifiers where possible.
- Keep message text stable so runtime verification can confirm expected logs.
- Use the required event IDs so browser checks can assert functionality.

## Checklist

- Is `loglevel` used instead of ad-hoc `console.log` calls?
- Is all logging gated to localhost/development by default?
- Is release output free of debug/info logs?
- Are log levels used consistently?
- Are sensitive fields excluded or redacted?
- Are baseline runtime logs visible in localhost/dev (startup + key action)?
- Are expected logs absent/silent in release mode?
- Do logs use required stable event IDs?
- Do payloads include all required keys for each event type?
