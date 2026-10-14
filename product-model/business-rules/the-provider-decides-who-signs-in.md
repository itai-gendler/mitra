---
appliesTo:
- type: entity
  id: user
  effect: creates
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

# Anyone the sign-in provider lets through gets an account

There is no user list to manage in Mitra: a person gets an account the first time the provider signs them in, so who may sign in is decided at the provider, by group, app assignment or however it handles access.
