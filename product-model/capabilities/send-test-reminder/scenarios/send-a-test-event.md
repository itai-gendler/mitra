---
kind: primary
routes:
  web: Web
steps:
- text: The User asks for a sample meeting reminder
  kind: actor
  actor: user
  entities:
  - {entity: device, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
- text: The Product sends a sample reminder to every device of the user
  kind: product
  actor: user
  entities:
  - {entity: device, effect: reads, facts: [Language, Time zone]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
---

# Send a test event

## Trigger

A reminder did not arrive and the user checks their devices.

## Outcome

Each device shows a sample event reminder; if it arrives, the missing reminder's calendar is probably turned off.
