---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks another calendar in the editor of an occurrence
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Calendar, Repeat]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product asks whether this entry, this and following entries, or all entries are meant
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User chooses This and following entries
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product ends the series before this occurrence and saves the rest of it in the new calendar
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Calendar, Repeat]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Move the rest of a series to another calendar

## Trigger

A weekly class moves to the university calendar from this week on.

## Outcome

The chosen occurrences live in the new calendar; earlier ones stay behind.

## Edge cases

- A calendar that cannot repeat entries is offered only for This entry.
