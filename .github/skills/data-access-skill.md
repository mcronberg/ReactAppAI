# Data Access Skill

When integrating backend data:

- Keep backend client setup in a dedicated `lib` module.
- Keep data fetching/mutations in hooks or service modules.
- Never embed privileged credentials in frontend code.
- Use row-level security expectations explicitly when backend supports it.
- Keep UI components unaware of transport details.
- Log request/response failures through centralized logger only.
- Keep API logging enabled in localhost/dev and disabled in release.
- For AI calls, default to OpenRouter.
- Keep `OPENROUTER_API_KEY` in server/edge context for production static hosting.
- If local frontend testing uses env vars, keep them in `.env` and ensure `.env` is git-ignored.
- Ask and document whether conversation history is persisted and the retention limit.

## Checklist

- Is data access isolated from presentation components?
- Are environment variables documented and safely scoped?
- Are auth and access assumptions explicit?
- Is error handling consistent and user-friendly?
- Are data-layer logs centralized and environment-gated?
- Is OpenRouter key handling safe for deployment target (no client-exposed secret)?
