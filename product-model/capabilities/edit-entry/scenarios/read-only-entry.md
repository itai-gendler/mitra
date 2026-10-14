---
kind: validation
routes:
  web: Web
steps:
- text: The User opens an entry of a calendar subscription
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: []}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: Its calendar is read-only
  kind: condition
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Read-only]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product shows every field as selectable text and offers no change, move or delete
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Start, End, Location, Description]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Open an entry in a read-only calendar

## Trigger

The user opens an entry of a subscription.

## Outcome

Everything can be read, selected and copied; nothing can be changed.
