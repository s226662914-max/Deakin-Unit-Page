# Sprint 1 Security Checklist

Date: 2026-08-15
Ticket: [5pts] Security Hardening
Raised by: Senuja (Team Lead)
Auditor: Sandesh (Peer Reviewer)

Legend: [P] = Pass   [F] = Fail   [N/A] = Not Applicable

---

## 1. Input Sanitisation (reviewed by Senuja — Initial: N/A)
- [x] [N/A] No user-input forms exist on the site (static HTML/CSS only)
- [x] [N/A] No JavaScript or client-side rendering that processes query strings
- [x] [N/A] No untrusted data interpolated into DOM (all content is hard-coded)

## 2. Transport Security / HTTPS Links (reviewed by Sandesh)
- [x] [P] Every external `<a href="...">` uses `https://` (never `http://`)
- [x] [P] Every `<img src="...">` is either local or uses `https://`
- [x] [P] Every `<link rel="stylesheet">` is either local or uses `https://`
- [x] [P] No mixed-content warnings would occur if served over HTTPS

## 3. Link Target & Tabnabbing Protection (from unit table ticket)
- [x] [P] Every `target="_blank"` anchor also carries `rel="noopener noreferrer"`
- [x] [P] No opening of untrusted third-party tabs without the rel guard

## 4. Static File Safety
- [x] [P] No inline `<script>` tags
- [x] [P] No eval() or dynamic code execution
- [x] [P] No secret tokens, API keys, or passwords committed to the repo
- [x] [P] `.gitignore` excludes OS junk (Icon\r, .DS_Store, Thumbs.db) or files are deleted

## 5. Semantic HTML / Structural Integrity
- [x] [P] `<img>` tags have descriptive `alt` attributes (accessibility + anti-injection)
- [x] [P] No `javascript:` pseudo-protocol in any href
- [x] [P] No `onclick` / `onerror` / inline event handlers (can be vectors)

---

## Initial Reviewer Sign-off (Senuja — Task 1 + Task 3 complete)
Sections 1 and 4 reviewed. Sections 2, 3, 5 pending peer-review by Sandesh.
Signature: Senuja Dikkumbura  Date: 2026-08-15

## Peer-Review Sign-off (Sandesh — Task 2 + Task 4 complete)
All checklist items above marked [P]/[N/A] and any [F] items remediated.
Signature: Sandesh Rupasinghe  Date: 2026-08-15