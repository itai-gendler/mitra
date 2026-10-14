---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the calendar name in the entry's header
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Calendar]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product lists the calendars that could keep everything the entry has
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Color]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User picks another calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the entry in that calendar and then deletes the original
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Calendar]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Move an entry to another calendar

## Trigger

A personal appointment was created in the work calendar.

## Outcome

The entry lives in the picked calendar, with its color, and the original is gone.

## Edge cases

- Moving an entry with participants deletes it from the first calendar, and some servers then tell the participants it was cancelled.
- A task keeps its place in the planning order when it moves.
