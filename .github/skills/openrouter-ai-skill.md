# OpenRouter AI Skill

When implementing AI features in generated apps:

- Use OpenRouter as the default AI gateway.
- Prefer the latest stable `@openrouter/sdk` for TypeScript integrations.
- Follow OpenRouter Client SDK pattern (`new OpenRouter({ apiKey: process.env.OPENROUTER_API_KEY })`).
- Keep model selection explicit via env variable (`OPENROUTER_MODEL`) and allow per-feature overrides when needed.
- Ask the developer before implementation whether conversation history should be included.
- If history is enabled, ask and document retention policy (message count/time window) and where history is stored.
- When app language is Danish, generated UI text must use proper Danish characters (`æ`, `ø`, `å`) and never fallback transliterations (`ae`, `oe`, `aa`) unless explicitly requested for a legacy integration.
- Keep local secrets in `.env` and ensure `.env` is git-ignored.
- Never commit or log raw API keys.
- For production static hosting (for example GitHub Pages), do not call OpenRouter directly from browser with privileged keys.
- Route production AI requests through controlled server/edge function and store secrets in platform secret store.
- For generated app repos on GitHub, include setup guidance for Secrets/Variables needed by deployment/runtime.
- Include error handling for provider/network failures with non-sensitive logs.
- Add tests for AI success/failure paths and history-retention behavior when history is enabled.

## Suggested env contract

- `OPENROUTER_API_KEY`: OpenRouter API key (secret, local/deployment only)
- `OPENROUTER_MODEL`: Default model slug (for example `openai/gpt-5.2`)
- `OPENROUTER_SITE_URL`: Optional app attribution header value
- `OPENROUTER_APP_NAME`: Optional app attribution header value

## Minimal TypeScript client shape

```ts
import { OpenRouter } from '@openrouter/sdk';

export const openRouterClient = new OpenRouter({
  apiKey: process.env.OPENROUTER_API_KEY,
  httpReferer: process.env.OPENROUTER_SITE_URL,
  appTitle: process.env.OPENROUTER_APP_NAME,
});
```

## Checklist

- Is OpenRouter used as default integration path?
- Is latest stable `@openrouter/sdk` used when package.json is AI-generated?
- Is `.env` present locally with required keys and ignored by git?
- Was history behavior explicitly confirmed with retention limits?
- For Danish-language apps, were `æ`, `ø`, and `å` used correctly in generated copy?
- Are secrets excluded from frontend bundles and logs?
- Are deployment secrets/variables documented for generated app repos?
