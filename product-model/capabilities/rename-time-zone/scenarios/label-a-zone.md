---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the zone's name, chooses Rename and types Mom
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Added time zones]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product saves the label
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Added time zones]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Label a zone

## Trigger

The Lisbon column is where the user's mother lives.

## Outcome

The column reads Mom on every device.
