---
icon: compass
---

# Schema & Metadata Navigation

DocKit provides an OpenAPI-aware tree view and dependency analyzer, eliminating the need to scroll through multi-thousand-line specification files.

## OpenAPI Outline

The **OpenAPI Outline** parses the active specification into a hierarchical tree:

* **Root Metadata:** `info` (title, version, terms), `servers`, `tags`, and `externalDocs`.
* **Endpoints & Operations:** HTTP methods (`GET`, `POST`, `PUT`, `DELETE`), paths, parameters, request bodies, and responses.
* **Reusable Components:** `components/schemas`, `definitions`, `securitySchemes`, parameters, and responses.

### Navigation Actions & Controls

* **Jump to Source:** Click any node in the Outline to center the editor on that exact line.
* **Follow Cursor:** Keep the Outline tree synchronized with your active editor cursor. Toggle via the outline `...` menu or set `"dockit.followCursor": true`.
* **Filter as You Type:** Type directly in the Outline to filter nodes dynamically (`"dockit.filterOnType": true`).
* **Sort Orders:** From the `...` menu, choose **Sort By**:
  * `Position`: Reflects the exact order in the source document (default).
  * `Name`: Alphabetical sort.
  * `Category`: Groups items by OpenAPI structural type.
* **Group by Tag:** Toggle **Group by Tag** to cluster all paths and operations under their assigned global tags.

***

## Search View

The dedicated **Search** panel provides fast free-text search across large specifications:

1. Open **DocKit → Search** (or press `Ctrl+Alt+F` / `Cmd+Alt+F` from the Outline).
2. Enter an operation ID, path fragment, parameter name, or documentation keyword.
3. Matching keys, paths, and scalar values appear dynamically. Click any item to navigate directly to it.

***

## References View (`$ref` Dependency Tracing)

When modifying shared schema definitions, you must know what other objects depend on them.

1. Select a schema or reusable component in the editor or the OpenAPI Outline.
2. Open **DocKit → References**.
3. Inspect the two relationship categories:
   * **Incoming References:** Endpoints and schemas that reference the selected component via `$ref`.
   * **Outgoing References:** Other components that the selected component references.
4. Click any reference to jump to its declaration or usage.

***

## Summary View

Located in the DocKit Inspector, the **Summary** view displays contextual metadata for whatever node is currently selected:

* Property counts and child node statistics.
* For schema objects: an interactive **donut chart** depicting property data-type distributions (`string`, `integer`, `object`, `array`, `boolean`).
* Reference counts (incoming/outgoing).
