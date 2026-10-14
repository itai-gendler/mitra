---
appliesTo:
- type: entity
  id: user
  effect: creates
references:
- kind: code
  role: implementation
  target: src/features/identity/server/auth.ts#authMiddleware
- kind: doc
  role: intent
  target: docs/sso.md
  title: Single sign-on
---

# Turning sign-in on starts everyone with a new account

Whatever was set up while the server was for one person stays with that old account: connected accounts, settings and every entry in Mitra calendars. Everyone who signs in, the former single user included, starts with an empty account.
