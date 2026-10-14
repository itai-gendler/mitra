---
kind: alternative
routes:
  web: Web
steps:
- text: The User selects several rows and chooses Move to…
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Calendar]}
  contexts:
    web:
      place: web::signed-in::table-view
- text: The User picks a calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::table-view
- text: The Product moves each selected entry there
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Calendar]}
  - {entity: task, effect: changes, facts: [Calendar]}
  contexts:
    web:
      place: web::signed-in::table-view
---

# Move selected rows of the table

## Trigger

The user tidies up entries that landed in the wrong calendar.

## Outcome

Every selected entry lives in the picked calendar; for a repeating entry only the selected occurrence moves, unless the table lists all entries.
