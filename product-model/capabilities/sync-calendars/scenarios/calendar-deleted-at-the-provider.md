---
kind: unattended
routes:
  web: Web
steps:
- text: A calendar Mitra keeps no longer exists at the provider
  kind: condition
  unattended: true
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product removes the calendar with its entries
  kind: product
  entities:
  - {entity: calendar, effect: removes, from: Imported}
  - {entity: event, effect: removes, with: calendar}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Notice a calendar deleted at the provider

## Trigger

A calendar is deleted at the provider.

## Outcome

It leaves the sidebar with its entries on the next sync.
