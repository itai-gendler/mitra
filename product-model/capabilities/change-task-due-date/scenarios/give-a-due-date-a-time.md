---
kind: alternative
routes:
  web: Web
steps:
- text: The User turns off All day at the end of the due date
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Due date, All day]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product gives the task times and sets the due date to 17:00 that day
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [All day, Due date]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Give an all-day task's due date a time

## Trigger

The presentation is due at noon.

## Outcome

The whole task has times, and its due date is at 17:00 on the same day until the user changes it.
