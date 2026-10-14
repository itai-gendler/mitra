---
kind: alternative
routes:
  web: Web
steps:
- text: The User types the new password under Edit and presses Save
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Connection details]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product keeps the new password on the server
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: changes, facts: [Secret]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Change an account's password

## Trigger

The user changed their password at the provider.

## Outcome

Syncing works again with the new password; the server URL and username stay as they were.
