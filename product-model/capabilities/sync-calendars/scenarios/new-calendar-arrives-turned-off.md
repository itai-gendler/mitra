---
kind: unattended
routes:
  web: Web
steps:
- text: The account holds a calendar Mitra does not know yet
  kind: condition
  unattended: true
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product adds it turned off
  kind: product
  entities:
  - {entity: calendar, effect: creates, to: Turned off, facts: [Name, Provider name, Color, Holds, Read-only, Hidden, Order]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Notice a calendar created at the provider

## Trigger

Someone creates a calendar in the account at the provider.

## Outcome

The calendar is known to Mitra, turned off, so nothing new lands on the user's calendar without them choosing it.
