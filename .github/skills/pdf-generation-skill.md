# PDF Generation Skill

When implementing PDF export in React apps:

- Follow finansberegninger2026 approach as baseline.
- Use @react-pdf/renderer for PDF generation.
- Keep PDF components separate from page components.
- Lazy-load PDF generation modules to avoid heavy initial bundles.
- Build reusable export helpers (for example for tabular and summary exports).
- Keep number/date/currency formatting consistent with app format helpers.
- Ensure filenames are stable and user-friendly.

## Checklist

- Is @react-pdf/renderer used as default PDF engine?
- Are PDF components isolated from normal UI components?
- Is PDF generation code lazy-loaded?
- Are export helpers reusable across pages/features?
- Are output values formatted consistently with the app?
- Is PDF generation verified in browser without console errors?
