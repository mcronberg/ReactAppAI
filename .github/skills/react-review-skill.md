# React Review Skill

When reviewing React code:

- Verify component boundaries and responsibilities.
- Verify TypeScript usage in props, state, and data models.
- Verify predictable state updates and event handling.
- Verify accessibility basics: labels, button text, keyboard use, and semantic elements.
- Verify consistency with approved architecture and skills.
- Verify routing and hosting assumptions match deployment.
- Verify data access boundaries and env var safety.
- Verify core domain logic is isolated and testable.
- Verify lint/build logs are warning-free.
- Verify browser console is free of JavaScript errors on tested flows.
- Verify responsive behavior across mobile, tablet, and desktop.
- Verify visual style is modern and simplified with consistent hierarchy.
- Verify Chart.js is used for charts unless an explicit exception is documented.
- Verify PDF export uses @react-pdf/renderer with lazy-loaded export flow unless an explicit exception is documented.
- Verify logging is centralized and disabled in release output.
- Verify sensitive or personal data is not present in logs.

## Review order

1. Correctness
2. Type safety
3. Readability and maintainability
4. Accessibility basics
5. Consistency with team approach
6. Platform compatibility and release readiness
7. Browser runtime health (console clean)

## Output style

- Prioritize high-impact findings.
- Give minimal, concrete fixes.
- Call out missing tests or edge cases.
