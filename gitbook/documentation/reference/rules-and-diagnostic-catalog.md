---
icon: fence
---

# Rules & Diagnostic Catalog

DocKit includes 19 custom governance rules designed to enforce consistency and developer usability across your APIs.

## Custom DocKit Governance Rules (`dockit-*`)

| Rule ID                                       | Category     | Summary                                                                                       |
| --------------------------------------------- | ------------ | --------------------------------------------------------------------------------------------- |
| `dockit-paths-kebab-case`                     | URL Design   | Path segments must use kebab-case (e.g., `/user-profiles`).                                   |
| `dockit-no-crud-verbs-in-paths`               | REST Design  | Paths must not contain CRUD verbs (e.g., `/getUsers`, `/createOrder`).                        |
| `dockit-path-contains-version`                | Versioning   | Paths should include explicit API versioning prefixes (e.g., `/v1/`).                         |
| `dockit-schema-names-pascal-case`             | Naming       | Schema model identifiers must use PascalCase (e.g., `PetOwner`).                              |
| `dockit-property-camel-case`                  | Naming       | JSON property keys must use camelCase (e.g., `createdAt`).                                    |
| `dockit-require-servers-https`                | Security     | Server URLs must specify the `https://` protocol scheme.                                      |
| `dockit-no-http-basic-auth`                   | Security     | Disallows basic HTTP authentication schemes in security definitions.                          |
| `dockit-define-error-response-400`            | DX / Quality | Operations should explicitly declare a `400 Bad Request` response.                            |
| `dockit-require-rate-limit-headers`           | Governance   | Responses should declare standard rate-limiting headers.                                      |
| `dockit-deprecated-operation-has-description` | Lifecycle    | Any endpoint marked `deprecated: true` must include a description explaining migration paths. |

{% hint style="info" %}
To inspect the complete rule set, run **DocKit: Open Rules Reference** from the Command Palette inside VS Code.
{% endhint %}
