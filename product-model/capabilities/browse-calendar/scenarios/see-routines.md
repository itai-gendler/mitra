---
kind: alternative
routes:
  web: Web
steps:
- text: The User looks at the month view
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product draws frequent same-titled entries of a calendar as a routine
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Calendar, Start, Repeat]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The User clicks the routine
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product opens its first entry in that row
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# See things done often as routines

## Trigger

A daily workout fills the month.

## Outcome

Entries of one calendar with the same title, at least four in view and more often than weekly in the month view, show as a thin line with a mark per day.

## Edge cases

- In the year view, entries about every five weeks or more often become marks too.
- The week view always shows each entry in full.
