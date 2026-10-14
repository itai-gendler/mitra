---
appliesTo:
- type: capability
  id: sign-in
- type: capability
  id: sign-out
references:
- kind: code
  role: implementation
  target: src/features/identity/server/Session.ts
- kind: doc
  role: intent
  target: docs/sso.md
  title: Single sign-on
---

# A session lasts 30 days from the last use

The browser holds only a cookie; signing out ends the session at once.
