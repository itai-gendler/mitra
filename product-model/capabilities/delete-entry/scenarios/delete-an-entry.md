---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete in the editor's menu
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product deletes the event from its calendar
  kind: product
  actor: user
  entities:
  - {entity: event, effect: removes}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Delete an entry

## Trigger

A meeting was called off.

## Outcome

The entry is gone from Mitra and from its calendar's provider; a deleted Notion task goes to Notion's trash.

## Edge cases

- A calendar server with participants tells them the entry was cancelled.
