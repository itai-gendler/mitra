---
kind: person
acts: external
references:
- kind: code
  role: implementation
  target: src/features/identity/server/auth.ts#authMiddleware
- kind: doc
  role: intent
  target: docs/sso.md
  title: Single sign-on
---

# Visitor

Someone who opens a Mitra server with sign-in turned on and has not signed in yet. Signing in makes them a User.
