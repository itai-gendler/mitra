---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the zone and picks New York
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Time zone]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the zone and keeps the clock times
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Time zone]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Pick another zone for an entry

## Trigger

A flight leaves at 9:00 in New York.

## Outcome

The entry is at 9:00 New York time, and the editor shows the user's time beside it.

## Edge cases

- While the entry's zone differs from the user's, a button switches the editor between the user's time and the entry's own; the zone changes only from the entry's own time.
