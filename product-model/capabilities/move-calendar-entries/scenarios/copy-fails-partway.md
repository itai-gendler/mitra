---
kind: edge
routes:
  web: Web
steps:
- text: The User confirms a move
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The destination refuses one of the copies
  kind: condition
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The Product stops the move before deleting any original and says how many entries are now in both calendars
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::move-entries
---

# Stop when copying fails

## Trigger

The destination provider fails while copies are being made.

## Outcome

The whole move stops and nothing is deleted; at worst an entry is in both calendars, never in neither.
