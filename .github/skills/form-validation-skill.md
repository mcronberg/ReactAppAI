# Form Validation Skill

When implementing forms:

- Prefer react-hook-form style patterns for predictable validation.
- Use explicit default values and typed form inputs.
- Validate on submit first, then revalidate on change when needed.
- Keep parsing and domain conversion logic outside JSX blocks.
- Show clear validation feedback near each field.

## Checklist

- Are form inputs fully typed?
- Are validation rules explicit and readable?
- Is submit flow deterministic and side-effect aware?
- Are example/test inputs easy to apply?
