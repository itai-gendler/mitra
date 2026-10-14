---
actors:
- visitor
access: public
entryPoints:
- web: /auth/login
references:
- kind: code
  role: implementation
  target: src/features/identity/server/auth.ts#authRouter
---

# Signed out

Where a Visitor arrives on a server with sign-in turned on: every page sends them to sign in first.
