---
kind: validation
routes:
  web: Web
steps:
- text: The User asks to move the entries of a subscription
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The calendar is read-only
  kind: condition
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Read-only]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The Product refuses with "Entries in this calendar cannot be deleted from mitra, so they can only be copied out of it"
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::move-entries
---

# Refuse to move out of a read-only calendar

## Trigger

The user tries to move a subscription's entries.

## Outcome

Nothing moves; read-only calendars can only be copied from.
