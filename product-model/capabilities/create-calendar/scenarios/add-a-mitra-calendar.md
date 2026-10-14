---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses New calendar on the Mitra heading and names it
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product creates the calendar
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: creates, to: Imported, facts: [Name, Color, Holds, Hidden, Order]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Add a Mitra calendar

## Trigger

The user wants a separate calendar for the household.

## Outcome

The calendar is ready straight away, turned on, in a color not yet used among its siblings.
