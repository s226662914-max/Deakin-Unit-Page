# Input Sanitisation Review — Sprint 1

Ticket: [5pts] Security Hardening, Task 1
Reviewer: Senuja D.  |  Date: 2026-08-15
Scope: index.html, main.css

## Method
Walked index.html DOM tree and every rule in main.css looking for:
  - HTML `<form>`, `<input>`, `<textarea>` elements
  - `<script>` blocks (inline or external)
  - Dynamic DOM writes (innerHTML, document.write, eval)
  - URL/fragment/query-string parsing used as input to rendering
  - Any unsanitised template interpolation

## Findings
| Area | Result | Notes |
|------|--------|-------|
| Forms / user input | N/A ✅ | Zero form controls present. Site is read-only content. |
| Client-side scripting | N/A ✅ | Zero `<script>` tags, no JS framework, no inline handlers. |
| DOM injection surface | N/A ✅ | All content is static, authored directly in HTML source. |
| External resource loading | Pass ✅ | stylesheet = local (main.css); image = local (logo.svg.webp); handbook links = https with noopener. |
| Inline event handlers (`on*`) | Pass ✅ | None found (grep: 0 matches). |
| `javascript:` URIs | Pass ✅ | None found. |

## Verdict
No input sanitisation vulnerabilities exist in Sprint 1.
Rationale: there are no inputs. This is a static brochure page, so the
correct control is to *keep it that way* — if Sprint 2 introduces
contact forms or search, sanitisation MUST be added at that point.

Signed-off: Senuja Dikkumbura (Team Lead)
