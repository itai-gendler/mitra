---
kind: primary
routes:
  web: Web
steps:
- text: The User picks a color in the calendar's menu
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Color]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product saves the color
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, facts: [Color]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Recolor a calendar

## Trigger

Two calendars look too alike.

## Outcome

The calendar and the entries without a color of their own wear the new color.
