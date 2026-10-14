---
kind: primary
routes:
  web: Web
steps:
- text: The User presses Due date and picks Friday
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Due date]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the due date
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Due date]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Set a due date

## Trigger

A presentation is due on Friday.

## Outcome

The task carries the due date and its flag, whether or not it is scheduled.
