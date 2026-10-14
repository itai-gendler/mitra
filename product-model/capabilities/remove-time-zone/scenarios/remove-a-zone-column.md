---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the zone's name and chooses Remove
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Added time zones]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product removes the zone from the user's list
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Added time zones]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Remove a zone from the week

## Trigger

The colleague in Tokyo moved on.

## Outcome

The column is gone on every device.
