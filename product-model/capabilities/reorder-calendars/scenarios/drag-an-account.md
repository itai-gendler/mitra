---
kind: alternative
routes:
  web: Web
steps:
- text: The User drags an account by its heading
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Order]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product saves the order of the user's integrations
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: changes, facts: [Order]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Drag an account with its calendars

## Trigger

The work account should come before the personal one.

## Outcome

The account and all its calendars move together.
