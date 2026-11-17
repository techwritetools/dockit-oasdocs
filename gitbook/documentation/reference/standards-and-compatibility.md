---
icon: puzzle-piece-simple
---

# Standards & Compatibility

## Supported Specifications

DocKit supports the following API specification standards:

* **OpenAPI 3.1.x:** Full schema validation and editing support (v3.1.0 – v3.1.2).
* **OpenAPI 3.0.x:** Full schema validation, outline navigation, and snippet generation (v3.0.0 – v3.0.4).
* **OpenAPI 2.0 (Swagger 2.0):** Outline navigation, validation, leaf editing, and linting. _(Note: Code snippet generation is not supported for Swagger 2.0)._

## Supported File Formats

DocKit automatically detects and binds to:

* `.json` (Standard JSON)
* `.jsonc` (JSON with comments)
* `.yaml` / `.yml` (YAML 1.2)

## Privacy & Offline Execution

* **Zero Telemetry:** DocKit does not collect usage analytics or tracking data.
* **Completely Local:** Validation, linting, spelling, and style analysis run strictly inside your local VS Code extension host and worker processes.
* **No Network Calls:** Specifications are never sent to external servers or cloud services.
