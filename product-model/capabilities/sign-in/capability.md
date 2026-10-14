---
availability:
- {place: 'web::signed-out'}
references:
- kind: code
  role: implementation
  target: src/features/identity/server/auth.ts#authRouter
- kind: code
  role: implementation
  target: src/features/identity/server/Oidc.ts
- kind: code
  role: implementation
  target: src/features/identity/server/Session.ts
- kind: doc
  role: intent
  target: docs/sso.md
  title: Single sign-on
- kind: code
  role: implementation
  target: src/features/identity/User.ts#User
---

# Sign in

Sign in through the server's OpenID Connect provider with an account the person already has. It exists only while the server has sign-in turned on. Anyone the provider lets through gets a Mitra account of their own the first time; their name and email are taken from the provider at every sign-in. Mitra keeps no password.
