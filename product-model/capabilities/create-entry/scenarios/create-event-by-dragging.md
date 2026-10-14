---
kind: primary
routes:
  web: Web
steps:
- text: The User drags across an empty stretch of a day in the week view
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product drafts an event over that stretch in the default calendar and opens its editor
  kind: product
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default calendar, Snap to]}
  - {entity: calendar, effect: reads, facts: []}
  - {entity: event, effect: reads, facts: []}
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
- text: The Product saves the event with the default event reminder and the user's time zone
  kind: product
  actor: user
  entities:
  - {entity: event, effect: creates, facts: [Title, Calendar, Start, End, All day, Time zone, Busy or free, Reminders]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Create an event by dragging across the week

## Trigger

The user sees free time in their week and wants to put a meeting there.

## Outcome

The event is saved in the default calendar, Busy, with the default event reminder, and its editor stays open.

## Edge cases

- Dragging inside a window of availability still creates an ordinary entry, as on an empty part of the grid.
- On a touch screen, holding on an empty spot for half a second starts the drag; a plain swipe scrolls.
