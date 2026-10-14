---
kind: validation
routes:
  web: Web
steps:
- text: The User opens a saved worklog
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The event is in a Tempo calendar
  kind: condition
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  - {entity: calendar, effect: reads, facts: []}
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product shows the title as read-only text and keeps the description editable
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Description]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Keep a booked worklog's title

## Trigger

The user opens a worklog in a Tempo calendar.

## Outcome

The title, the Jira issue's key and summary, cannot be edited; the description, the worklog's note, can.
