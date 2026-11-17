---
icon: square-sliders-vertical
---

# Settings & Configuration Reference

Configure DocKit options in your User or Workspace `settings.json` under the `dockit.*` namespace.

### General & Outline Settings

| Setting                    | Type      | Default      | Description                                                                 |
| -------------------------- | --------- | ------------ | --------------------------------------------------------------------------- |
| `dockit.validateOnSave`    | `boolean` | `true`       | Automatically run validation whenever the file is saved.                    |
| `dockit.showValuePreviews` | `boolean` | `true`       | Display preview values next to nodes in the OpenAPI Outline.                |
| `dockit.followCursor`      | `boolean` | `false`      | Synchronize the Outline view with the cursor location in the active editor. |
| `dockit.filterOnType`      | `boolean` | `true`       | Filter Outline tree nodes dynamically as you type.                          |
| `dockit.outlineSortOrder`  | `string`  | `"position"` | Tree ordering. Accepted values: `"position"`, `"name"`, `"category"`.       |
| `dockit.outlineGroupBy`    | `string`  | `"none"`     | Endpoints grouping. Accepted values: `"none"`, `"tag"`.                     |

### Linting Settings

| Setting                       | Type      | Default | Description                                                                    |
| ----------------------------- | --------- | ------- | ------------------------------------------------------------------------------ |
| `dockit.linting.enabled`      | `boolean` | `false` | Master toggle for the API linting engine.                                      |
| `dockit.linting.enabledRules` | `array`   | `[]`    | List of rule IDs to enforce. Must contain at least one ID to produce findings. |

### Prose Style Settings

| Setting                              | Type      | Default | Description                                          |
| ------------------------------------ | --------- | ------- | ---------------------------------------------------- |
| `dockit.spellCheck.styles.google`    | `boolean` | `false` | Enables Google Developer Documentation Style checks. |
| `dockit.spellCheck.styles.microsoft` | `boolean` | `false` | Enables Microsoft Writing Style Guide checks.        |
| `dockit.spellCheck.styles.ibm`       | `boolean` | `false` | Enables IBM Style checks.                            |
| `dockit.spellCheck.styles.writeGood` | `boolean` | `false` | Enables write-good readability and clarity checks.   |
| `dockit.spellCheck.styles.alex`      | `boolean` | `false` | Enables alex inclusive-language checks.              |

### Dictionary Settings

| Setting                                | Type    | Default | Description                                                                        |
| -------------------------------------- | ------- | ------- | ---------------------------------------------------------------------------------- |
| `dockit.spellCheck.words`              | `array` | `[]`    | List of custom words accepted by the spell checker across all workspaces.          |
| `dockit.spellCheck.customDictionaries` | `array` | `[]`    | Workspace-relative paths to `.txt`, `.json`, or `.dic` wordlist files (maximum 2). |

### Public Export Settings

| Setting                                     | Type      | Default        | Description                                                        |
| ------------------------------------------- | --------- | -------------- | ------------------------------------------------------------------ |
| `dockit.publicExport.internalExtension`     | `string`  | `"x-internal"` | Vendor extension key identifying internal paths and operations.    |
| `dockit.publicExport.stripInternalMarker`   | `boolean` | `true`         | Strips the internal extension tag from surviving public endpoints. |
| `dockit.publicExport.pruneUnusedComponents` | `boolean` | `false`        | Prunes unreachable schemas after removing internal endpoints.      |
