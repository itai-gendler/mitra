---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens Mitra for the first time
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The account has no home yet
  kind: condition
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Home time zone]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product makes the device's zone home
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Home time zone]}
  - {entity: device, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Set home from the first device

## Trigger

The user opens Mitra for the first time.

## Outcome

The device's zone is the user's home; on later trips the zone the user is in shows beside home without being added.
