---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the eye of a hidden calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Hidden]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product shows the calendar
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, facts: [Hidden]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Show a hidden calendar

## Trigger

The user needs the family calendar again.

## Outcome

Its entries are back in every view.

## Edge cases

- Showing a calendar by hand does not cost the way back to the calendars shown before Only show this calendar.
