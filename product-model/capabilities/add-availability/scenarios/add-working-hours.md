---
kind: primary
routes:
  web: Web
steps:
- text: The User picks the command that shades working hours in the command palette
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The default calendar has no availability yet
  kind: condition
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default calendar]}
  - {entity: calendar, effect: reads, facts: []}
  - {entity: availability, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The Product saves weekly availability from Monday to Friday, 9:00 to 17:00, and opens it in the week view
  kind: product
  actor: user
  entities:
  - {entity: availability, effect: creates, facts: [Calendar, Start, End, Time zone, Repeat, Busy or free]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Add working hours

## Trigger

The user wants their working week shaded.

## Outcome

Weekly availability Monday to Friday, 9:00 to 17:00, Free, shades the week in the calendar's color, and its editor is open.
