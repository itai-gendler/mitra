---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Mitra, names the first calendar and presses Save
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product adds the Mitra integration with that calendar
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: creates, facts: [Provider, Order]}
  - {entity: calendar, effect: creates, to: Imported, facts: [Name, Color, Holds, Hidden, Order], with: integration}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Add Mitra calendars

## Trigger

The user wants calendars with no account behind them.

## Outcome

A Mitra calendar with the given name is ready straight away, and the Mitra tile leaves Add Integration.
