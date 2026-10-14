---
kind: alternative
routes:
  web: Web
steps:
- text: The User draws a bar on the empty row at the bottom of the timeline
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product drafts a task over those days in the default calendar that can hold tasks
  kind: product
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default calendar]}
  - {entity: calendar, effect: reads, facts: []}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The User types a title
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the task
  kind: product
  actor: user
  entities:
  - {entity: task, effect: creates, to: To Do, facts: [Title, Calendar, Start, End, All day]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Draw a task on the timeline

## Trigger

The user plans work across several days in the timeline.

## Outcome

The task is saved with the drawn dates and gets its own row.
