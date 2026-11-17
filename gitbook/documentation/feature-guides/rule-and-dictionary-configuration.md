---
icon: gears
---

# Rule & Dictionary Configuration

All quality checks in DocKit can be customized per project using `.vscode/settings.json`.

## Enabling API Linting Rules

Because API design standards vary across teams, DocKit's linting engine operates on an explicit allowlist.

To enable linting:

1. Open VS Code Settings (`Ctrl+,` / `Cmd+,`).
2. Set `"dockit.linting.enabled": true`.
3. Add specific rule IDs to `"dockit.linting.enabledRules"`.

```json
{
  "dockit.linting.enabled": true,
  "dockit.linting.enabledRules": [
    "dockit-paths-kebab-case",
    "dockit-no-crud-verbs-in-paths",
    "dockit-property-camel-case",
    "dockit-require-servers-https",
    "dockit-deprecated-operation-has-description"
  ]
}
```

Setting `"dockit.linting.enabled": true` without populating `"dockit.linting.enabledRules"` will produce no findings. \{% endhint %\}

To browse all available linting rules and their descriptions, run DocKit: Open Rules Reference from the Command Palette.

### Configuring Prose Style Checks

Each prose style package is toggled independently under `dockit.spellCheck.styles.*`. There is no master switch.

```json
{
  "dockit.spellCheck.styles.google": true,
  "dockit.spellCheck.styles.writeGood": true,
  "dockit.spellCheck.styles.alex": true,
  "dockit.spellCheck.styles.microsoft": false,
  "dockit.spellCheck.styles.ibm": false
}
```

### Custom Dictionaries

Avoid false positives on product names, internal frameworks, and acronyms by adding custom terms.

#### Option A: Inline Workspace Settings

Add terms directly to `.vscode/settings.json`. This works even in untrusted workspaces:

```json
{
  "dockit.spellCheck.words": [
    "GraphQL",
    "Kubernetes",
    "OAuth2",
    "WidgetFlow"
  ]
}
```

#### Option B: External Dictionary Files

Point DocKit to external word lists in your repository:

```json
{
  "dockit.spellCheck.customDictionaries": [
    ".vscode/company-terms.txt",
    ".vscode/api-acronyms.json"
  ]
}
```

**Supported Dictionary Formats**

* Plain Text (`.txt` or `.dic`): One word per line. Blank lines and lines starting with `#` or `//` are ignored.

```
# Custom API Terminology
idempotency
WidgetFlow
microservice
```

* JSON (`.json`): A flat array of strings:

```json
["idempotency", "WidgetFlow", "microservice"]
```

**Security & Parsing Guardrails for External Dictionaries**

* Workspace Trust: External dictionaries are disabled in Restricted Mode.
* Containment: Paths must resolve within the workspace folder (symlinks or `../` escaping the workspace are blocked).
* File Limits: Up to 2 files, each at most 5 MB, with a combined maximum of 100,000 words.
* Token Format: Entries must be single words (starting with an ASCII letter, maximum 80 characters). Phrases with spaces are skipped.
