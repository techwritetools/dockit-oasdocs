---
icon: file-export
---

# Exporting Public Specifications

When managing a unified internal OpenAPI specification that contains unreleased or private endpoints, use DocKit to generate a clean, public-facing artifact.

## Marking Internal Operations

By default, DocKit inspects operations and paths for the vendor extension:

```yaml
x-internal: true
```

_(The vendor tag can be changed using `"dockit.publicExport.internalExtension"`)._

### Running the Export

1. Open your master OpenAPI specification.
2. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`).
3. Run DocKit: Export Public Spec (Remove Internal Endpoints).
4. Select the output destination. By default, DocKit creates a companion file matching the source format:
   * `openapi.public.yaml` or `openapi.public.json`

#### What DocKit Does During Export:

1. Strips all paths or operations containing the configured internal extension.
2. Removes the `x-internal` marker itself from any remaining operations (controlled by `"dockit.publicExport.stripInternalMarker": true`).
3. Optionally prunes unreferenced components (`"dockit.publicExport.pruneUnusedComponents": true`).

### Conservative Component Pruning

When internal operations are stripped, their supporting data schemas under `components/schemas` may become orphans.

* Enable `"dockit.publicExport.pruneUnusedComponents": true` to automatically clean up these unreferenced models.
* DocKit uses transitive `$ref` analysis to identify dead components.
* Preserving Schemas: If a schema is not referenced directly in an endpoint but must remain in the public specification (e.g., dynamic webhook payloads), add:

```yaml
x-keep: true
```

* Components marked with `x-keep: true` are never pruned.

{% hint style="info" icon="triangle-exclamation" %}
**Manual Review Required:** Always inspect exported files before publishing them to public portals. Verify that public server URLs, security scopes, and descriptions remain accurate. \{% endhint %\}
{% endhint %}

