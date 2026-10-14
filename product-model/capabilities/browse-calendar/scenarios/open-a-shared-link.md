---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens a link that names the month view, a date and an entry
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product opens that view on that date with the entry's editor open
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Open a link to a place in the calendar

## Trigger

The user opens a bookmark of a view, a date and an entry.

## Outcome

The same view, date and entry open as when the link was made.
