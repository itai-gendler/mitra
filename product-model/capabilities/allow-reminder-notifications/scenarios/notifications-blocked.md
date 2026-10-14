---
kind: edge
routes:
  web: Web
steps:
- text: The User opens Settings → Notifications
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::notifications-settings
- text: The browser blocks notifications from Mitra
  kind: condition
  actor: user
  entities:
  - {entity: device-settings, effect: reads, facts: [Reminder notifications]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
- text: The Product shows Blocked
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::notifications-settings
---

# Notice blocked notifications

## Trigger

The user once refused notifications in this browser.

## Outcome

The row reads Blocked; the user unblocks Mitra in the browser's site settings. The reminders they add are saved either way.
