---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the event in a view
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product opens its editor beside it
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Description, Links]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User changes the title and writes a description in Markdown
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves both to the event's calendar
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Title, Description]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Edit an event's title and description

## Trigger

The user opens an event to add notes.

## Outcome

The new title and description are saved to the event's calendar; the links in the description show in the Links row.

## Edge cases

- A description line starting with a box becomes a checklist item that can be ticked without editing the text.
- Links that would run code, such as javascript:, show as plain text and never as links.
