---
icon: pen-to-square
---

# Inline Authoring & Utilities

DocKit provides focused authoring aids that reduce the risk of structural formatting errors when updating API documentation.

## Leaf Node Editing

Leaf node editing allows technical writers to update scalar values directly from the **OpenAPI Outline** without editing raw JSON/YAML blocks.

### Supported Fields

* `summary` and `description` text
* `tags`
* `servers` URLs
* `enum` values
* Scalar configuration flags and booleans (e.g., `deprecated: true`)

### How to Edit

1. Locate the target node in the **OpenAPI Outline**.
2. Hover over the scalar value to reveal the **Edit (pencil)** icon.
3. Click the icon, enter the new value in the input field, and press `Enter`.
4. The change is written directly to the source file. Use standard VS Code Undo (`Ctrl+Z` / `Cmd+Z`) to revert if necessary.

{% hint style="warning" %}
**Scope Limitation:** Leaf editing is strictly for scalar values. To add new paths, delete schema objects, or restructure arrays, edit the source document directly in the VS Code editor.
{% endhint %}

***

## Code Snippet Generation

Generate ready-to-test client request examples for any endpoint in an OpenAPI 3.x document.

1. Open an OpenAPI 3.x specification.
2. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) and run **DocKit: Generate Code Snippets**.
3. Select the target operation from the dropdown list.
4. Choose the target snippet format:
   * **cURL**
   * **Python (`requests`)**
5. Inspect or copy the generated request snippet (including URL paths, headers, and request bodies).

{% hint style="info" %}
Snippet generation supports OpenAPI 3.0.x and 3.1.x specifications. OpenAPI 2.0 (Swagger) is not supported.
{% endhint %}

***

## Format Conversion (JSON ↔ YAML)

Switch between JSON and YAML formats without leaving the editor:

1. Open the active `.json` or `.yaml` specification.
2. Run **DocKit: Convert OAS (JSON ↔ YAML)** from the Command Palette.
3. DocKit converts the document and opens it in a new editor tab. Your original source file remains unchanged.
