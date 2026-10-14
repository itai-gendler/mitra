---
kind: validation
routes:
  web: Web
steps:
- text: The User drags a calendar towards another account
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Order]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product refuses with "Sources can only be reordered within their integration"
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Keep a calendar within its account

## Trigger

The user drags a calendar under another account's heading.

## Outcome

The calendar stays in its own account.
