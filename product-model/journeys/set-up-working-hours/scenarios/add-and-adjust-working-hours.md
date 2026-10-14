---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User picks the command that shades working hours in the command palette
  kind: actor
  actor: user
  capability: add-availability
  entities: []
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The Product saves working hours from Monday to Friday, 9:00 to 17:00, and opens them in the editor
  kind: product
  actor: user
  capability: add-availability
  entities:
  - {entity: availability, effect: creates, facts: [Calendar, Start, End, Time zone, Repeat, Busy or free]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User changes the end to 16:00
  kind: actor
  actor: user
  capability: edit-entry
  entities:
  - {entity: availability, effect: reads, facts: [End]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product asks which days are meant and, for all of them, saves the new end
  kind: product
  actor: user
  capability: edit-entry
  entities:
  - {entity: availability, effect: changes, facts: [End]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Add working hours and adjust them

## Trigger

The user wants their working hours visible in the week.

## Outcome

Weekly availability from Monday to Friday ends at the hour the user works until.
