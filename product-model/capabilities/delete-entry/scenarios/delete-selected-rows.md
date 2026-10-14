---
kind: alternative
routes:
  web: Web
steps:
- text: The User selects rows and presses Delete
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::table-view
- text: The Product asks to confirm, naming how many entries and that repeating ones lose every occurrence when listed as a whole
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::table-view
- text: The User confirms
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::table-view
- text: The Product deletes them
  kind: product
  actor: user
  entities:
  - {entity: event, effect: removes}
  - {entity: task, effect: removes, from: Done}
  contexts:
    web:
      place: web::signed-in::table-view
---

# Delete selected rows of the table

## Trigger

The user clears out old entries.

## Outcome

Every selected entry is deleted after the user confirms; repeating ones lose only the selected occurrence unless the table lists all entries.
