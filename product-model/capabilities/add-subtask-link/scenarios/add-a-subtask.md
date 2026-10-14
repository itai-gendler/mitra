---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the plus on Subtask of and types part of the bigger task's title
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product searches every visible calendar of the user
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User picks the bigger task
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the link with the subtask
  kind: product
  actor: user
  entities:
  - {entity: subtask-link, effect: creates, facts: [Subtask, Bigger task]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Make a task a subtask

## Trigger

Booking the venue is part of organizing the party.

## Outcome

The bigger task lists the subtask and counts it, and a line joins the two on the calendar when both are in view.

## Edge cases

- In Notion, a link to a task in the same database goes into its Parent task relation; Mitra keeps links to anything else itself.
