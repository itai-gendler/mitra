---
kind: primary
routes:
  web: Web
steps:
- text: The User double-clicks the calendar's name and types another
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product saves the name
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Rename a calendar

## Trigger

The provider's name for a calendar means nothing to the user.

## Outcome

The calendar shows the user's name everywhere.
