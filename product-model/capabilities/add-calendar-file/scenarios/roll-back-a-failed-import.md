---
kind: edge
routes:
  web: Web
steps:
- text: The User adds a file
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-file-import
- text: The calendar refuses one of the entries
  kind: condition
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendar-file-import
- text: The Product removes the entries it had already added
  kind: product
  actor: user
  entities:
  - {entity: event, effect: removes}
  contexts:
    web:
      place: web::signed-in::calendar-file-import
---

# Take back a half-finished import

## Trigger

Adding fails partway through the file.

## Outcome

Nothing from the file stays half imported; if some entries cannot be removed, the user learns how many to delete by hand.
