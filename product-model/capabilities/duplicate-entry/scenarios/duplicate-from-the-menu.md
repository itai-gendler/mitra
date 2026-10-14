---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Duplicate in the editor's menu
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves a copy in the same calendar and opens its editor
  kind: product
  actor: user
  entities:
  - {entity: event, effect: creates, facts: [Title, Calendar, Description, Location, Color, Start, End, All day, Time zone, Busy or free, Visibility, Reminders]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Duplicate an entry from its menu

## Trigger

A meeting happens again on another day.

## Outcome

A copy with the same facts is saved in the same calendar, and its editor opens.
