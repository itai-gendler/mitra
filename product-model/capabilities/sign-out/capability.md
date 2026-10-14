---
availability:
- {place: 'web::signed-in'}
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
---

# Sign out

End the session with Sign out in the menu beside the account card at the bottom of the sidebar. If the provider supports it, signing out of Mitra signs the person out there as well. It exists only while sign-in is turned on.
