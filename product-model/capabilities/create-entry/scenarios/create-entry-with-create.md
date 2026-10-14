---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses Create
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product drafts an entry at the next full hour, an hour long, in the default calendar, as an event unless that calendar holds only tasks
  kind: product
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default calendar]}
  - {entity: calendar, effect: reads, facts: [Holds]}
  - {entity: event, effect: reads, facts: []}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User types a title
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves it as a task in the default calendar, since that calendar holds only tasks
  kind: product
  actor: user
  entities:
  - {entity: task, effect: creates, to: To Do, facts: [Title, Calendar, Start, End, All day, Time zone, Reminders]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Create an entry with Create

## Trigger

The user presses C or Create in the page header.

## Outcome

A new entry starts at the next full hour, lasts an hour, and is saved in the default calendar once it has a title.

## Edge cases

- In the timeline, a new entry is a task wherever the calendar can hold tasks; a calendar that holds none hands over to the week view.
- In the table view, a new entry starts today and opens as a row of the table.
