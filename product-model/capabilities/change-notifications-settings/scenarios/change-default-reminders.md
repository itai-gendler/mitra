---
kind: primary
routes:
  web: Web
steps:
- text: The User sets the default reminder for new meetings to an hour before
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default event reminder]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
- text: The Product saves it with the user's account
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Default event reminder]}
  contexts:
    web:
      place: web::signed-in::notifications-settings
---

# Change the default reminders

## Trigger

The user wants an hour's warning before every meeting.

## Outcome

New timed events start with a reminder an hour before; all-day entries still start without one.
