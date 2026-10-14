---
kind: validation
routes:
  web: Web
steps:
- text: The User opens a repeating event
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product offers no other type for it
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Keep a repeating entry's type

## Trigger

The user tries to turn a weekly meeting into a task.

## Outcome

The type stays; it cannot change on a repeating entry.

## Edge cases

- The type cannot change either in a calendar that holds only one type, such as a Notion calendar.
