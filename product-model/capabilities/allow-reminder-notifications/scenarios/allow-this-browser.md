---
kind: primary
routes:
  web: Web
steps:
- text: The User presses Allow and accepts the browser's question
  kind: actor
  actor: user
  entities:
  - {entity: device-settings, effect: reads, facts: [Reminder notifications]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
- text: The Product registers this browser as one of the user's devices, with its language and time zone
  kind: product
  actor: user
  entities:
  - {entity: device-settings, effect: changes, facts: [Reminder notifications]}
  - {entity: device, effect: creates, facts: [Language, Time zone]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
---

# Allow this browser

## Trigger

The user wants reminders on their laptop.

## Outcome

The row reads Allowed, and the laptop is listed under Devices as this device.
