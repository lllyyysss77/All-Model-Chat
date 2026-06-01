```markdown
# All-Model-Chat Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute to the [All-Model-Chat](https://github.com/your-org/All-Model-Chat) codebase, a TypeScript project built with Vite. You'll learn the project's coding conventions, commit patterns, and the step-by-step workflows for adding features, updating settings, managing models, refactoring, and more. The guide also covers testing patterns and provides handy slash commands for common tasks.

---

## Coding Conventions

**File Naming**
- Use `camelCase` for file and folder names.
  - Example: `settingsModal.tsx`, `fileUploader.ts`

**Imports**
- Use relative imports.
  - Example:
    ```ts
    import { useFileUploader } from './useFileUploader';
    ```

**Exports**
- Mixed export style: both named and default exports are used.
  - Example:
    ```ts
    // Named export
    export function useFileUploader() { ... }

    // Default export
    export default SettingsModal;
    ```

**Commit Messages**
- Use [Conventional Commits](https://www.conventionalcommits.org/):
  - Prefixes: `fix`, `chore`, `feat`, `refactor`, `docs`
  - Example: `feat: add Gemini 3.5 Flash model support`

---

## Workflows

### Add or Update Settings Option
**Trigger:** When adding or modifying a user-facing setting (appearance, model, live artifacts, MCP, etc.)  
**Command:** `/add-setting`

1. Edit or add files in `src/components/settings/sections/` (e.g., `AppearanceSection.tsx`, `ModelsSection.tsx`).
2. Update `src/schemas/appSettingsSchema.ts` (and `.test.ts`) for schema changes.
3. Update `src/constants/settingsDefaults.ts` (and `.test.ts`) for default values.
4. Edit `src/types/settings.ts` for type changes.
5. Update `src/i18n/translations/settings/*.ts` for new/changed labels.
6. Add or update tests in `src/components/settings/sections/*.test.tsx`.
7. Optionally update `SettingsContent.tsx` and/or `SettingsModal.tsx`.

**Example:**
```ts
// src/components/settings/sections/AppearanceSection.tsx
export function AppearanceSection() {
  // ...new setting UI
}
```

---

### Feature Development with Tests and Schema
**Trigger:** When building a new feature or making a major enhancement (UI, logic, schema, tests)  
**Command:** `/new-feature`

1. Add or update files in `src/components/`, `src/features/`, `src/hooks/`.
2. Write or update tests in `*.test.tsx` files.
3. Update or add schemas/types in `src/schemas/*.ts`, `src/types/*.ts`.
4. Update constants in `src/constants/` if needed.
5. Update i18n files for user-facing text.
6. Optionally update documentation (`README.md`, etc.).

**Example:**
```ts
// src/features/chat/newFeature.ts
export function newFeatureLogic() { ... }

// src/features/chat/newFeature.test.ts
import { newFeatureLogic } from './newFeature';
test('should work', () => { ... });
```

---

### Version Bump and Release
**Trigger:** When releasing a new version or updating dependencies  
**Command:** `/bump-version`

1. Update `package.json` version.
2. Update `package-lock.json`.
3. Optionally update `README.md` or other metadata.

**Example:**
```json
// package.json
{
  "version": "1.2.3"
}
```

---

### Fix or Enhance File Upload or Import
**Trigger:** When fixing or improving file upload/import logic  
**Command:** `/fix-file-upload`

1. Edit files in `src/hooks/file-upload/` (e.g., `useFileDragDrop.ts`).
2. Edit `src/utils/file-upload/` or `src/utils/import-context/` as needed.
3. Update or add tests in `src/hooks/file-upload/*.test.tsx`, `src/utils/import-context/*.test.ts`.
4. Optionally update related UI components (e.g., `AttachmentMenu.tsx`, `SelectedFileDisplay.tsx`).

**Example:**
```ts
// src/hooks/file-upload/useFileUploader.ts
export function useFileUploader() { ... }
```

---

### Refactor or Reorganize App Structure
**Trigger:** When improving code structure, naming, or modularity across many files  
**Command:** `/refactor`

1. Edit files across `src/components/`, `src/features/`, `src/hooks/`, `src/utils/`, `src/constants/`, etc.
2. Update or add tests to reflect new structure.
3. Update types and schemas if necessary.
4. Update documentation if user-facing structure/naming changes.

**Example:**
```ts
// src/utils/fileHelpers.ts
export function normalizeFileName(name: string) { ... }
```

---

### Add or Update Model Support
**Trigger:** When adding a new AI model or updating model details  
**Command:** `/add-model`

1. Edit `src/constants/modelConstants.ts`, `modelRegistry.ts`, `settingsModelOptions.test.ts`.
2. Edit `src/utils/modelCatalog.ts`, `modelCapabilities.ts`, `modelSorting.ts`, `modelSwitchSettings.ts` (and their `.test.ts`).
3. Edit `src/components/settings/sections/ModelsSection.tsx` (and `.test.tsx`).
4. Update `src/types/settings.ts` if needed.
5. Update i18n if user-facing model names change.

**Example:**
```ts
// src/constants/modelConstants.ts
export const SUPPORTED_MODELS = ['Gemini 3.5 Flash', ...];
```

---

## Testing Patterns

- **Framework:** [Vitest](https://vitest.dev/)
- **Test file pattern:** `*.test.ts` or `*.test.tsx`
- **Location:** Tests are placed alongside source files or in the same directory.
- **Example:**
  ```ts
  // src/features/chat/chatLogic.test.ts
  import { chatLogic } from './chatLogic';

  test('returns correct response', () => {
    expect(chatLogic('hello')).toBe('hi');
  });
  ```

---

## Commands

| Command         | Purpose                                                      |
|-----------------|--------------------------------------------------------------|
| /add-setting    | Add or update a user-facing setting                          |
| /new-feature    | Develop a new feature with UI, logic, schema, and tests      |
| /bump-version   | Bump package version and update lockfile for release         |
| /fix-file-upload| Fix or enhance file upload/import logic                      |
| /refactor       | Refactor or reorganize app structure                         |
| /add-model      | Add support for a new AI model or update model details       |
```
