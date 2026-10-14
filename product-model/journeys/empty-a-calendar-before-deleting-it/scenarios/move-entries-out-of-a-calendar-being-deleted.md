---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User chooses Delete calendar on a calendar with entries
  kind: actor
  actor: user
  capability: delete-calendar
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product warns that every entry goes too and offers Move entries first…
  kind: product
  actor: user
  capability: delete-calendar
  entities: []
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The User chooses Move entries first…
  kind: actor
  actor: user
  capability: delete-calendar
  entities: []
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product keeps the calendar and opens Move entries for it
  kind: product
  actor: user
  capability: delete-calendar
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The User picks a destination and confirms the move
  kind: actor
  actor: user
  capability: move-calendar-entries
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The Product copies the entries into the destination and then deletes the originals
  kind: product
  actor: user
  capability: move-calendar-entries
  entities:
  - {entity: event, effect: changes, facts: [Calendar]}
  - {entity: task, effect: changes, facts: [Calendar]}
  contexts:
    web:
      place: web::signed-in::move-entries
---

# Move the entries out of a calendar being deleted

## Trigger

The user deletes a Mitra calendar that still holds entries.

## Outcome

The entries were moved to another calendar; the user can now delete the empty one without a question.
