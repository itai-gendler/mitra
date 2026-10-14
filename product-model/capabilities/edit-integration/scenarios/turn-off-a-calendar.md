---
kind: alternative
routes:
  web: Web
steps:
- text: The User unticks a calendar under Edit and presses Save
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product turns the calendar off
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, from: Imported, to: Turned off, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Turn off a calendar

## Trigger

The user wants a calendar gone from Mitra entirely, reminders and all.

## Outcome

The calendar is no longer synced or stored, and its busy availability is taken back from the provider.
