---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses the cross beside the task's end date
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product removes the end and keeps the start
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [End]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Turn a task into a moment

## Trigger

The user wants a task at one point in time, such as medication at 7:30.

## Outcome

The task keeps its start and has no end; the week view shows it as a slim line at its start time.

## Edge cases

- Pressing End date gives the moment an end again.
