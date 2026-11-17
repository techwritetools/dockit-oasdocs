---
icon: user-tie-hair
---

# Overview for Product Managers

Product Managers and API Product Owners need to verify that an API contract aligns with business requirements, developer ergonomics, and customer needs—without deciphering raw JSON/YAML trees.

## PM Review Capabilities

### 1. High-Level Specification Audit

* **OpenAPI Outline:** View endpoints grouped cleanly by tag (`dockit.outlineGroupBy: "tag"`). This lets you audit business domains (e.g., `/billing`, `/users`, `/webhooks`) sequentially.
* **Summary View:** Select any schema object in the Outline to view its property distribution (including a type donut chart), child counts, and reference metadata.

### 2. Auditing User-Facing Quality

* **Missing Descriptions:** Ensure developers have documented all query parameters, request bodies, and error responses.
* **Checking Deprecation Notices:** Run validation to verify that any endpoint marked `deprecated: true` includes an explanatory description detailing migration steps (`dockit-deprecated-operation-has-description`).
* **Spelling & Terminology:** Spot inconsistent feature naming or outdated brand terms across all endpoint descriptions in the **Spelling** tab.

### 3. Reviewing Public vs. Internal Boundaries

Ensure that private administrative or internal staging endpoints are not exposed to public consumers:

1. Verify that internal endpoints include `x-internal: true`.
2. Run `DocKit: Export Public Spec (Remove Internal Endpoints)`.
3. Audit the generated `.public.yaml` or `.public.json` to confirm that sensitive internal operations are excluded.
