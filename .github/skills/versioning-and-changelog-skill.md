# Versioning and Changelog Skill

When handling project versioning:

- Use `0.minor.patch` as default versioning track unless otherwise specified.
- For larger feature changes, bump `minor` by default.
- Initialize or bump version only when the user explicitly asks for a version bump.
- Keep `CHANGELOG.md` present at all times.
- Add a clear changelog entry for every meaningful change set.

## Git responsibility rule

- All git commits, pushes, pulls, sync actions, and branch publishing are performed by the user.
- The AI may suggest commit message text, but does not execute commit/push/sync actions.

## Checklist

- Is the versioning scheme set to `0.minor.patch` by default?
- Was minor bump used for larger changes unless instructed otherwise?
- Was version changed only after explicit user request?
- Does `CHANGELOG.md` exist and include the relevant update entry?
- Were git actions left to the user while providing optional commit message suggestions?
