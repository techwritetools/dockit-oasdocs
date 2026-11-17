---
icon: palette
---

# Command Palette Reference

Access all DocKit commands via the Command Palette (`Ctrl+Shift+P` on Windows/Linux or `Cmd+Shift+P` on macOS):

| Command Label                                              | Identifier                  | Purpose                                                      |
| ---------------------------------------------------------- | --------------------------- | ------------------------------------------------------------ |
| **DocKit: Validate OpenAPI Document**                      | `dockit.validate`           | Runs structural and schema validation on the open file.      |
| **DocKit: Lint OAS File**                                  | `dockit.lint`               | Runs enabled Spectral and `dockit-*` linting rules.          |
| **DocKit: Open Rules Reference**                           | `dockit.openRulesReference` | Displays the interactive catalog of linting and style rules. |
| **DocKit: Check Spelling**                                 | `dockit.checkSpelling`      | Executes spelling and terminology validation.                |
| **DocKit: Export Public Spec (Remove Internal Endpoints)** | `dockit.exportPublicSpec`   | Generates a sanitized public specification.                  |
| **DocKit: Convert OAS (JSON ↔ YAML)**                      | `dockit.convertFormat`      | Converts active specification between JSON and YAML.         |
| **DocKit: Generate Code Snippets**                         | `dockit.generateSnippets`   | Generates cURL and Python request snippets for OAS 3.x.      |
| **DocKit: Show DocKit**                                    | `dockit.focusSidebar`       | Opens the primary DocKit navigation sidebar.                 |
| **DocKit: Show DocKit Inspector**                          | `dockit.focusInspector`     | Opens the DocKit Inspector sidebar.                          |
| **DocKit: Follow Cursor**                                  | `dockit.toggleFollowCursor` | Toggles automatic Outline-to-cursor synchronization.         |
| **DocKit: Filter on Type**                                 | `dockit.toggleFilterOnType` | Toggles instant filtering in the Outline tree.               |
| **DocKit: Sort By: ...**                                   | `dockit.setSortOrder`       | Changes Outline sorting (`Position`, `Name`, `Category`).    |
| **DocKit: Group by Tag**                                   | `dockit.toggleGroupByTag`   | Toggles endpoint grouping by assigned tags.                  |
