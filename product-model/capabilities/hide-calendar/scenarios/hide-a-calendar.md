---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the eye of a calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Hidden]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product hides the calendar
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, facts: [Hidden]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Hide a calendar

## Trigger

The family calendar crowds the week.

## Outcome

Its entries leave every view and the search.
