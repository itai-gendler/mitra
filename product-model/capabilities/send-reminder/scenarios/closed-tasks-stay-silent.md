---
kind: unattended
routes:
  web: Web
steps:
- text: A task's reminder is due
  kind: condition
  unattended: true
  entities:
  - {entity: task, effect: reads, facts: [Reminders]}
  contexts:
    web:
      place: web::signed-in::reminder-notification
- text: The task is done or cancelled
  kind: condition
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::reminder-notification
- text: The Product sends nothing
  kind: product
  entities: []
  contexts:
    web:
      place: web::signed-in::reminder-notification
---

# Stay silent for a closed task

## Trigger

A task with a reminder was marked done before the reminder was due.

## Outcome

No reminder goes out.
