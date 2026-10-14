---
kind: validation
routes:
  web: Web
steps:
- text: The User clicks the name of the home zone
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Home time zone]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product offers Rename and no Remove
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Keep home and the current zone

## Trigger

The user tries to remove their home zone.

## Outcome

The column stays; to replace home, the user makes another zone home.
