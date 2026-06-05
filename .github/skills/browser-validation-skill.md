# Browser Validation Skill

When validating implemented features:

- Use Playwright as the required automation baseline.
- Use Chrome DevTools MCP as optional escalation for deep debugging.
- Check tooling availability on the current machine before validation starts.
- If Playwright is missing, install/configure it before continuing.
- Open the app in a browser and verify key routes/screens.
- Check browser console during normal usage flows.
- Treat any JavaScript console error as a release blocker.
- Resolve errors before handoff, then re-verify in browser.
- Document what was checked and final console status.

## Checklist

- Were all changed pages/screens opened in browser?
- Were core interactions exercised manually?
- Is console free of runtime JavaScript errors?
- Were fixes re-validated after changes?
- Is verification evidence included in handoff notes?
- Was Playwright available and used for baseline validation?
- If deep debugging was needed, was DevTools MCP available and used?
