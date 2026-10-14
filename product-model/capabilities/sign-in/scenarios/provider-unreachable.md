---
kind: edge
routes:
  web: Web
steps:
- text: The Visitor opens Mitra
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::signed-out
- text: Mitra cannot look up the provider
  kind: condition
  entities: []
  contexts:
    web:
      place: web::signed-out
- text: The Product fails this sign-in and tries the lookup again on the next one
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::signed-out
---

# Try the provider again

## Trigger

The sign-in provider started after Mitra.

## Outcome

Sign-in fails this time, and Mitra looks the provider up again on the next attempt.
