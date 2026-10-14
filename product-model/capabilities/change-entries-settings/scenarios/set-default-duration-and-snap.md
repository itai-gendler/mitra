---
kind: primary
routes:
  web: Web
steps:
- text: The User sets Default Duration to 30 minutes and Snap to to 30 min
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default duration, Snap to]}
  contexts:
    web:
      place: web::signed-in::entries-settings
- text: The Product saves both with the user's account
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Default duration, Snap to]}
  contexts:
    web:
      place: web::signed-in::entries-settings
---

# Set the default duration and snap

## Trigger

Most of the user's meetings last half an hour.

## Outcome

New entries without a length last 30 minutes, and drags land on 30-minute steps.
