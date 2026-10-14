---
kind: primary
routes:
  web: Web
steps:
- text: The User picks Free
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Busy or free]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves Free with the event
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Busy or free]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Show an event as free

## Trigger

A holiday the user is not taking off should not block the day.

## Outcome

The event shows on the calendar without blocking the time for anyone checking when the user is free.
