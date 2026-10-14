---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks Event in the header and picks Task
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves a task with the event's facts and deletes the event
  kind: product
  actor: user
  entities:
  - {entity: task, effect: creates, to: To Do, facts: [Title, Calendar, Description, Location, Color, Start, End, All day, Time zone, Visibility, Reminders]}
  - {entity: event, effect: removes}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Turn an event into a task

## Trigger

Something on the calendar turns out to be work to tick off.

## Outcome

The entry is a task in the same calendar, To Do, and has lost busy or free.

## Edge cases

- A task that becomes an event loses its status, progress, due date and estimate.
