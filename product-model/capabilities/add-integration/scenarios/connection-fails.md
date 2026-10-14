---
kind: edge
routes:
  web: Web
steps:
- text: The User presses Connect with a wrong password or token
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product shows why the provider refused and keeps the form open
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  contexts:
    web:
      place: web::signed-in::integration-details
---

# Show why connecting failed

## Trigger

The provider refuses the details the user entered.

## Outcome

Nothing is saved; the provider's reason is shown, such as "Tempo rejected the API token".
