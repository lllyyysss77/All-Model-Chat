---
name: add-or-update-settings-option
description: Workflow command scaffold for add-or-update-settings-option in All-Model-Chat.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-settings-option

Use this workflow when working on **add-or-update-settings-option** in `All-Model-Chat`.

## Goal

Add or update a user-facing setting (e.g., appearance, model, live artifacts, MCP, etc.)

## Common Files

- `src/components/settings/sections/*.ts(x)`
- `src/schemas/appSettingsSchema.ts`
- `src/schemas/appSettingsSchema.test.ts`
- `src/constants/settingsDefaults.ts`
- `src/constants/settingsDefaults.test.ts`
- `src/types/settings.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add files in src/components/settings/sections/ (e.g., AppearanceSection.tsx, ModelsSection.tsx, LiveArtifactsSection.tsx, McpSection.tsx)
- Update src/schemas/appSettingsSchema.ts (and .test.ts) to reflect schema changes
- Update src/constants/settingsDefaults.ts (and .test.ts) for default values
- Edit src/types/settings.ts for type changes
- Update src/i18n/translations/settings/*.ts for new/changed labels

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.