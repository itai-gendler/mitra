---
kind: edge
routes:
  web: Web
steps:
- text: The User changes an entry in a tab opened before the server was updated
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product refuses the change with "Mitra was updated. Reload the page to save your changes."
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Refuse a change from a tab opened before an update

## Trigger

The server was updated while an old tab stayed open.

## Outcome

Nothing is saved; the user is told to reload the page.
