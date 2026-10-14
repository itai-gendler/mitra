---
kind: validation
routes:
  web: Web
steps:
- text: The User clears the name and confirms
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product refuses with "A name is required"
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Refuse an empty name

## Trigger

The user clears the name.

## Outcome

The calendar keeps its name.
