---
icon: gear-api
---

# Overview for Developers

For API and backend developers, DocKit acts as an in-editor linter and contract validator, catching breaking schema bugs and naming inconsistencies before CI/CD checks run.

## Key Developer Tasks

### 1. In-Editor Contract Validation

DocKit supplies version-aware schema validation for JSON and runs native OAS structural validation for YAML.

* Schema mismatches and missing required properties are flagged inline and in VS Code's **Problems** panel.
* Manual trigger: Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) and run `DocKit: Validate OpenAPI Document`.

### 2. Enforcing API Governance via Linting

DocKit includes built-in `spectral:oas` rules and 19 custom governance rules (`dockit-*`):

* **Path Naming:** Detects anti-patterns like `dockit-no-crud-verbs-in-paths` or non-kebab-case URLs (`dockit-paths-kebab-case`).
* **Property Conventions:** Flags snake\_case or PascalCase where camelCase is expected (`dockit-property-camel-case`).
* **Security & Infrastructure:** Requires HTTPS servers (`dockit-require-servers-https`) and disallows HTTP Basic Auth (`dockit-no-http-basic-auth`).

### 3. Pre-Commit Review Workflow

1. Open your spec file (`.json` or `.yaml`).
2. Run `DocKit: Lint OAS File` to evaluate rules defined in your workspace `.vscode/settings.json`.
3. Check the **DocKit: Inspector → All Issues** tab to ensure all `Validation` and `Linting` items are resolved.
4. If testing endpoints with local clients, run `DocKit: Generate Code Snippets` to generate cURL commands for manual testing.
