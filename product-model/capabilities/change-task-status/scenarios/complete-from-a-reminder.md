---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses Done on the reminder notification
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::reminder-notification
- text: The Product marks the task Done, and only that occurrence when the task repeats
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: To Do, to: Done, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::reminder-notification
---

# Mark a task done from its reminder

## Trigger

A task's reminder goes off.

## Outcome

The task is done without opening Mitra.

## Edge cases

- Safari and Firefox do not show the notification's buttons.
- A second press writes nothing more to the provider.
