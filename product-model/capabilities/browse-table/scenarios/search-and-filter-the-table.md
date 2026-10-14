---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the table view
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::table-view
- text: The Product lists the next 30 days of entries with the undated and overdue tasks
  kind: product
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Title, Start, Calendar]}
  - {entity: event, effect: reads, facts: [Title, Start, Calendar]}
  contexts:
    web:
      place: web::signed-in::table-view
- text: The User types a word, filters Status to open tasks and Calendar to one calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::table-view
- text: The Product lists only the rows that match
  kind: product
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Title, Calendar, Description, Location]}
  contexts:
    web:
      place: web::signed-in::table-view
---

# Search and filter the table

## Trigger

The user looks for every open task in one calendar.

## Outcome

Only matching rows are listed, with their count beside the search field.

## Edge cases

- The Status filter's No status stands for events, so unticking it lists tasks alone.
- Title and When cannot be hidden.
