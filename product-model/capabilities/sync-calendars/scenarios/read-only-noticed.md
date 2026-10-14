---
kind: unattended
routes:
  web: Web
steps:
- text: The provider reports different privileges for a calendar
  kind: condition
  unattended: true
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product marks the calendar read-only or writable
  kind: product
  entities:
  - {entity: calendar, effect: changes, facts: [Read-only]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Notice that a calendar became read-only or writable

## Trigger

The owner of a shared calendar changes what the user may do.

## Outcome

Editing turns on or off with the next sync.
