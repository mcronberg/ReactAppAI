# Domain Logic Skill

When implementing non-trivial business logic:

- Place business rules in pure utility modules.
- Keep functions deterministic and testable.
- Avoid React state dependencies inside core calculations.
- Reuse shared format/parse helpers for consistency.
- Document assumptions and units for formulas.

## Checklist

- Can the logic run without React?
- Are edge cases covered by tests?
- Are names domain-specific and clear?
- Is formatting separated from numeric computation?
