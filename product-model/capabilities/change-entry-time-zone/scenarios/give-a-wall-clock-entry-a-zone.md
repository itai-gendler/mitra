---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks a zone for an entry that shows Wall clock (no time zone)
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Time zone]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the zone
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Time zone]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Give a wall clock entry a zone

## Trigger

An entry came from another app with no zone and shows Wall clock.

## Outcome

The entry has the picked zone and keeps its clock times; it cannot become a wall clock entry again.
