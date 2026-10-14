---
kind: alternative
routes:
  web: Web
steps:
- text: The Visitor opens Mitra and signs in at the provider
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::signed-out
- text: The Product finds their account, takes the provider's current name and email, and opens a session
  kind: product
  actor: visitor
  entities:
  - {entity: user, effect: changes, facts: [Name, Email]}
  contexts:
    web:
      place: web::signed-out
---

# Sign in again

## Trigger

A person whose session ended comes back.

## Outcome

They are back in their own account, with the provider's current name and email.
