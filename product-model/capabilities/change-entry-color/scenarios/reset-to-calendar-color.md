---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Reset to calendar color
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Color]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product removes the entry's own color
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Color]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Reset to the calendar's color

## Trigger

The entry no longer needs to stand out.

## Outcome

The entry wears its calendar's color again.
