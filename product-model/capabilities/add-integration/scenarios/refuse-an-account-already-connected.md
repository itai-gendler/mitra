---
kind: validation
routes:
  web: Web
steps:
- text: The User enters the details of an account already connected and presses Connect
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product refuses with "This account is already connected"
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Connection details]}
  contexts:
    web:
      place: web::signed-in::integration-details
---

# Refuse an account that is already connected

## Trigger

The user connects a CalDAV account that is already in the sidebar.

## Outcome

Nothing is added; the user is told "This account is already connected".
