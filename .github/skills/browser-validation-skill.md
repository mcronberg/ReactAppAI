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
- Capture screenshot/snapshot evidence for changed screens.
- Confirm rendered design matches expected style and layout baseline.
- Assert expected functional log events in localhost/dev for tested flow.
- Verify that key UI flows are covered by Playwright integration tests and that core logic has unit tests.

Expected baseline event IDs:

- `APP_START`
- `VIEW_READY`
- `ACTION_SUBMIT`
- `ACTION_SUCCESS` or `ACTION_ERROR`

## Checklist

- Were all changed pages/screens opened in browser?
- Were core interactions exercised manually?
- Is console free of runtime JavaScript errors?
- Were fixes re-validated after changes?
- Is verification evidence included in handoff notes?
- Was Playwright available and used for baseline validation?
- If deep debugging was needed, was DevTools MCP available and used?
- Were screenshots/snapshots captured for changed screens?
- Does visual output match expected design baseline?
- Were expected event IDs observed for the tested scenario?
- Were unit tests and Playwright tests executed for the tested scenario?
