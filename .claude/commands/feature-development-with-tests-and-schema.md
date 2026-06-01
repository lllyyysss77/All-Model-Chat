---
name: feature-development-with-tests-and-schema
description: Workflow command scaffold for feature-development-with-tests-and-schema in All-Model-Chat.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-development-with-tests-and-schema

Use this workflow when working on **feature-development-with-tests-and-schema** in `All-Model-Chat`.

## Goal

Develop a new feature or major enhancement, including UI, logic, schema, and tests

## Common Files

- `src/components/**/*.{ts,tsx}`
- `src/features/**/*.{ts,tsx}`
- `src/hooks/**/*.{ts,tsx}`
- `src/components/**/*.{test.tsx}`
- `src/features/**/*.{test.tsx}`
- `src/hooks/**/*.{test.tsx}`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Add or update multiple files in src/components/ (UI), src/features/ (logic), src/hooks/ (logic/UI hooks)
- Update or add tests in src/components/*/*.test.tsx, src/features/*/*.test.tsx, or src/hooks/*/*.test.ts(x)
- Update or add schema/types in src/schemas/*.ts, src/types/*.ts
- Update constants if needed (src/constants/...)
- Update i18n files if user-facing text is changed

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.