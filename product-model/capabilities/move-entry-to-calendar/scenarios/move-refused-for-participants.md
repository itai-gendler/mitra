---
kind: validation
routes:
  web: Web
steps:
- text: The User moves an event with participants to a calendar that cannot hold participants
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Calendar]}
  - {entity: calendar, effect: reads, facts: []}
  - {entity: participant, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product refuses with "This calendar does not support participants. Remove them before moving the entry"
  kind: product
  actor: user
  entities:
  - {entity: participant, effect: reads, facts: [Email]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Refuse a move the destination cannot hold

## Trigger

The user moves a meeting with participants into a Notion calendar.

## Outcome

Nothing moves; the user learns what to remove first.

## Edge cases

- The same holds for Free, a visibility, a progress or a due date the destination cannot store.
