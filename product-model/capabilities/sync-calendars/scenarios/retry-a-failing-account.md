---
kind: unattended
routes:
  web: Web
steps:
- text: Syncing one account fails
  kind: condition
  unattended: true
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product leaves that account for at least a minute and goes on with the others
  kind: product
  entities: []
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Retry an account that fails

## Trigger

An account's provider is down.

## Outcome

The other accounts sync as usual; the failing one is tried again later.
