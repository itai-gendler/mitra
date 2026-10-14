---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens the Planning tab
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::planning-tab
- text: A task repeats by its due date
  kind: condition
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Repeat, Due date]}
  contexts:
    web:
      place: web::signed-in::planning-tab
- text: The Product lists only its next occurrence
  kind: product
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Title, Due date]}
  contexts:
    web:
      place: web::signed-in::planning-tab
---

# See only the next of a repeating due date

## Trigger

A task repeats by its due date every month.

## Outcome

Only the next one is listed, and it is never overdue.
