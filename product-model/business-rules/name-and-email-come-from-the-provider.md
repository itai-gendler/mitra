---
appliesTo:
- type: entity
  id: user
  effect: changes
  facts: [Name, Email]
permits:
- actors:
  - visitor
references:
- kind: code
  role: implementation
  target: src/features/identity/User.ts#User
- kind: doc
  role: intent
  target: docs/sso.md
  title: Single sign-on
---

# A user's name and email come only from the sign-in provider

Each person's name and email are updated from the provider every time they sign in; Mitra offers no way to change them.
