---
icon: file-pen
---

# Overview for Technical Writers

Technical writers often manage API documentation directly within Git-backed OpenAPI specification files. DocKit streamlines this process by removing the friction of manual JSON/YAML syntax manipulation and running editorial checks in real time.

## Recommended Review Workflow

Rather than treating DocKit as a collection of isolated utilities, follow this sequential review pipeline when onboarding or auditing an API specification:

```
1. Inspect Structure  ──► 2. Resolve Errors  ──► 3. Polish Prose   ──► 4. Export & Deliver
   (OpenAPI Outline)         (Validation/Lint)      (Leaf Editing)        (Export Public Spec)
```

* Easily Find Elements and Understand the File Structure: Open the file and examine the OpenAPI Outline. Use Group by Tag to review endpoints by functional domain rather than raw file order.
* Resolve Structural Errors: Check the DocKit: Inspector → All Issues panel. Clear any red Validation errors before reviewing text, as invalid schemas can obscure downstream metadata.
* Trace Component Dependencies: When auditing shared objects under `components/schemas`, use the References view to see all incoming references before changing descriptions.
* Edit Documentation Fields: Use Leaf Node Editing to rewrite `summary`, `description`, and parameter text directly from the outline view without touching YAML indentation.
* Run Language & Style Checks: Fix flagged typos in Spelling, add company terms to `.vscode/company-terms.txt`, and check style guidance (Google, Microsoft, or IBM) in the Styles panel.
* Generate Request Samples: Verify that your parameter descriptions match real-world requests using DocKit: Generate Code Snippets.
* Export Public Artifacts: If internal endpoints exist, generate a sanitized public copy with DocKit: Export Public Spec.
