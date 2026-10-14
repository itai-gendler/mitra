---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens a page of Mitra
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::signed-out
- text: The Product sends them to the sign-in provider
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::signed-out
- text: The Visitor signs in at the provider
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::signed-out
- text: The Product creates their account with the provider's name and email, opens a session and returns them to the page they asked for
  kind: product
  actor: visitor
  entities:
  - {entity: user, effect: creates, facts: [Name, Email]}
  contexts:
    web:
      place: web::signed-out
---

# Sign in for the first time

## Trigger

A family member opens the shared Mitra server.

## Outcome

They have a new, empty account of their own and land on the page they asked for.

## Edge cases

- A session lasts 30 days from the last time the person used Mitra.
