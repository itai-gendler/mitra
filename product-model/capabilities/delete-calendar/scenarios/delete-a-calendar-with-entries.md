---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete calendar in the calendar's menu
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product warns that every entry goes too and cannot come back
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The User chooses Delete
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product deletes the calendar with its entries and availability
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: removes, from: Imported}
  - {entity: event, effect: removes, with: calendar}
  - {entity: task, effect: removes, from: To Do, with: calendar}
  - {entity: availability, effect: removes, with: calendar}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Delete a calendar with its entries

## Trigger

An old project calendar is no longer needed.

## Outcome

The calendar and its entries are gone for good.
