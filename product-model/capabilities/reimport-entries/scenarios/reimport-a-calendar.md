---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Re-import entries in a calendar's menu
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product discards the calendar's entries and imports it again
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, from: Imported, to: Importing, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Re-import a calendar

## Trigger

A calendar looks wrong after an update.

## Outcome

The calendar is read again from the provider from the start.
