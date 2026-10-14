---
kind: validation
routes:
  web: Web
steps:
- text: The User confirms New calendar with an empty name
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product refuses with "A name is required"
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Refuse a calendar without a name

## Trigger

The user leaves the name empty.

## Outcome

Nothing is created; a name is required.
