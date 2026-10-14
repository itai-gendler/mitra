---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks the command that shades working hours on a Thursday
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The default calendar already has availability
  kind: condition
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default calendar]}
  - {entity: calendar, effect: reads, facts: []}
  - {entity: availability, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The Product saves a weekly window, 9:00 to 17:00, on Thursday and opens it
  kind: product
  actor: user
  entities:
  - {entity: availability, effect: creates, facts: [Calendar, Start, End, Time zone, Repeat, Busy or free]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Add a window on today's weekday

## Trigger

The calendar already has working hours, and the user adds study time on Thursdays.

## Outcome

A weekly window on today's weekday is saved and open in the editor.
