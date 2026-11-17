---
icon: comments-question
---

# Troubleshooting & FAQ

### The DocKit Inspector appears in the wrong sidebar

If the **DocKit: Inspector** panel appears docked inside the left sidebar instead of the right:

1. Ensure the secondary sidebar is visible: run **View: Toggle Secondary Side Bar** from the Command Palette.
2. Click and drag the **DocKit: Inspector** title bar to the secondary sidebar on the right. VS Code remembers this position.

### Linting checks do not show any findings

Verify that both settings are configured in `.vscode/settings.json`:

1. `"dockit.linting.enabled": true`
2. `"dockit.linting.enabledRules"` contains at least one valid rule ID (e.g., `"dockit-paths-kebab-case"`). Because the allowlist is empty by default, enabling the engine without choosing rules produces no diagnostics.

### Style findings do not appear

Unlike spell checking, prose style rules are disabled by default. Enable your desired packages under `dockit.spellCheck.styles.*` (e.g., set `"dockit.spellCheck.styles.google": true`).

### An external dictionary file is not loading

Confirm the following constraints:

* **Workspace Trust:** The workspace must be in **Trusted** mode. External dictionaries are blocked in Restricted Mode.
* **File Location:** The dictionary must be located inside the workspace folder. Paths containing `../` that resolve outside the workspace are rejected.
* **File Limits:** DocKit loads at most **2** dictionary files, each under **5 MB**, with no more than **100,000** total words.
* **Word Formats:** Words must begin with an ASCII letter and contain no spaces.

### Performance on very large specifications (5+ MB)

Building the initial outline tree and running lint checks on files larger than 5 MB can take a few seconds. DocKit executes linting passes in a background worker thread to ensure your editor remains responsive.
