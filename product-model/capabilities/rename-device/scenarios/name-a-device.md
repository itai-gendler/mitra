---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the pencil beside a device and types a name
  kind: actor
  actor: user
  entities:
  - {entity: device, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
- text: The Product saves the name
  kind: product
  actor: user
  entities:
  - {entity: device, effect: changes, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
---

# Name a device

## Trigger

Two phones look alike in the list.

## Outcome

The device carries the name, kept when its browser renews its registration.
