---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete in the account's menu
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product takes back the busy availability written to the account and removes the account with everything Mitra keeps of it
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: removes}
  - {entity: calendar, effect: removes, from: Imported, with: integration}
  - {entity: event, effect: removes, with: calendar}
  - {entity: availability, effect: removes, with: calendar}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Disconnect an account

## Trigger

The user stops using an account.

## Outcome

The account, its calendars, their entries and their availability are gone from Mitra.
