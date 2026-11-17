---
icon: octagon-check
---

# Specification Validation & Quality Checks

DocKit consolidates four distinct quality dimensions into the **DocKit: Inspector → All Issues** panel:

| Check          | Scope       | Purpose                                                                     |
| -------------- | ----------- | --------------------------------------------------------------------------- |
| **Validation** | Structural  | Verifies strict conformity with the official OpenAPI schema specifications. |
| **Linting**    | Governance  | Checks adherence to API design standards (Spectral & DocKit rules).         |
| **Spelling**   | Terminology | Scans human-facing documentation strings for typographical errors.          |
| **Styles**     | Editorial   | Flags prose style issues based on Vale guidelines (Google, Microsoft, IBM). |

***

## 1. OpenAPI Validation

* **JSON Schema Validation:** Supplies version-aware schemas for OpenAPI 3.1.0–3.1.2, 3.0.0–3.0.4, and Swagger 2.0, providing native autocomplete and schema error detection.
* **YAML & Parser Validation:** Validates document structure using DocKit’s built-in parser.
* **Trigger:** Runs automatically on save (`"dockit.validateOnSave": true`) and during active editing with debouncing.
* **Manual Run:** Command Palette → `DocKit: Validate OpenAPI Document`.

## 2. API Linting

While validation guarantees that a parser can read your file, linting ensures that your API follows consistent design conventions. Linting runs in a background worker process to prevent UI slowdowns.

* Linting is **disabled by default**.
* Findings appear in the **Problems** tab and under **DocKit: Inspector → All Issues → Linting**.
* Manual Run: Command Palette → `DocKit: Lint OAS File`.

## 3. Spelling & Terminology Checks

DocKit scans human-facing text nodes (`description`, `summary`, and tag descriptions) while ignoring code elements (keys, path templates, and `$ref` pointers).

* **Always Enabled:** Runs automatically across all documentation strings.
* **Quick Fixes:** Click the VS Code lightbulb (`Ctrl+.` / `Cmd+.`) on flagged words to apply suggested replacements.
* Custom technical terms can be added to custom dictionaries to suppress false positives.

## 4. Prose Style Checks

DocKit includes optional editorial rule sets adapted from popular Vale packages:

* **Google Developer Documentation Style**
* **Microsoft Writing Style Guide**
* **IBM Style**
* **write-good** (readability, passive voice, weasel words)
* **alex** (inclusive, considerate language)

Style suggestions appear with informational severity and frequently offer single-click Quick Fixes.
