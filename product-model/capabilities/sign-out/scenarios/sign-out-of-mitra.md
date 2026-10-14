---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Sign out in the menu beside their account card
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Name, Email]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product ends the session and sends the person to the provider's sign-out
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Sign out of Mitra

## Trigger

The user is done on a shared computer.

## Outcome

The session is gone and the person is signed out at the provider where it allows.
