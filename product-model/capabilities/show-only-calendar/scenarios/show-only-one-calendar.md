---
kind: primary
routes:
  web: Web
steps:
- text: The User Alt-clicks the eye of the work calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Hidden]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product remembers which calendars were showing and hides every other one
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Previously visible calendars]}
  - {entity: calendar, effect: changes, facts: [Hidden]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Show only one calendar

## Trigger

The user wants to see only work.

## Outcome

Every other calendar is hidden, and the menu item now reads Show previously visible calendars.

## Edge cases

- A calendar that is turned off cannot be the only one shown.
