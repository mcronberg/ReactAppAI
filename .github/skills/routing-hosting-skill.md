# Routing and Hosting Skill

When building a React SPA for static hosting:

- Set Vite `base` to the deployed subpath.
- Use router mode that matches hosting behavior:
  - Prefer BrowserRouter with basename when deep-link fallback is configured.
  - Use HashRouter when fallback handling is unavailable.
- Ensure deep links resolve after refresh.
- For GitHub Pages style hosting, include SPA fallback strategy (for example 404.html mirroring index.html).
- Default to PWA unless explicitly disabled by developer decision.
- Use strict cache behavior by default: no runtime caching.
- Add a user-visible update flow when a newer version is detected.
- Create or update GitHub Actions workflow for GitHub Pages deployment (`.github/workflows/deploy.yml`).

## Checklist

- Is the base path correct for deployment URL?
- Is router type consistent with hosting constraints?
- Are route links and navigation tested on refresh/deeplink?
- Is the deployment pipeline aware of SPA fallback needs?
- Is runtime caching disabled unless explicitly justified?
- Is there a "new version available" prompt with controlled refresh?
- Is `.github/workflows/deploy.yml` present and aligned with GitHub Pages deployment?
