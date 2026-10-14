---
kind: primary
routes:
  web: Web
steps:
- text: The User presses Snooze 10 min on the notification
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::reminder-notification
- text: The Product sends the same reminder to the user's devices ten minutes later
  kind: product
  actor: user
  entities:
  - {entity: device, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::reminder-notification
---

# Snooze a reminder for ten minutes

## Trigger

The user is busy when a reminder arrives.

## Outcome

The same reminder arrives again on every device ten minutes later.
