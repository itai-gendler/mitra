---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User chooses Duplicate in the meeting's editor
  kind: actor
  actor: user
  capability: duplicate-entry
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves a copy in the same calendar and opens its editor
  kind: product
  actor: user
  capability: duplicate-entry
  entities:
  - {entity: event, effect: creates, facts: [Title, Calendar, Description, Location, Color, Start, End, All day, Time zone, Busy or free, Visibility, Reminders]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User changes the copy's start to next week
  kind: actor
  actor: user
  capability: edit-entry
  entities:
  - {entity: event, effect: reads, facts: [Start]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the new start and end
  kind: product
  actor: user
  capability: edit-entry
  entities:
  - {entity: event, effect: changes, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Duplicate a meeting for another day

## Trigger

A meeting happens again next week.

## Outcome

The copy is at next week's time; the original is unchanged.
