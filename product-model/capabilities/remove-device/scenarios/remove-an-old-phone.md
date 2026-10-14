---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the cross beside the old phone
  kind: actor
  actor: user
  entities:
  - {entity: device, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
- text: The Product removes the device
  kind: product
  actor: user
  entities:
  - {entity: device, effect: removes}
  contexts:
    web:
      place: web::signed-in::notifications-settings
---

# Remove an old phone

## Trigger

The user gave away a phone.

## Outcome

The phone is off the list and gets no more reminders.
