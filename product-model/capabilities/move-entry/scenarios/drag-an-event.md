---
kind: primary
routes:
  web: Web
steps:
- text: The User drags the event to another time
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product saves the new start and end, landing on the Snap to step
  kind: product
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Snap to]}
  - {entity: event, effect: changes, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Drag an event to another time

## Trigger

A meeting moves to the afternoon.

## Outcome

The event keeps its length at the new time, saved to its calendar.

## Edge cases

- On a touch screen, an entry moves only after it is held for half a second.
- Dragging a task changes its schedule, never its due date.
