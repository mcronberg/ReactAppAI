# PWA Cache and Update Skill

When implementing PWA behavior:

- Default to PWA unless developer explicitly chooses otherwise.
- Keep runtime caching disabled by default.
- Cache only what is strictly required for app shell/startup.
- Use explicit version metadata (for example version.json or build timestamp).
- Detect newer deployed version and show a user prompt.
- Provide a clear action: "New version available" -> refresh now.

## Checklist

- Was PWA choice explicitly confirmed with developer?
- Is runtime caching empty or minimized with clear rationale?
- Is version/build metadata available to the client?
- Is update detection reliable without aggressive polling?
- Does the UI provide safe refresh without data loss surprises?
