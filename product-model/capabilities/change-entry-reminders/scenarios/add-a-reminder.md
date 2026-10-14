---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the plus on the reminders row and picks an hour before
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Reminders]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the reminder and, the first time, the browser asks whether Mitra may show notifications
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Reminders]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Add a reminder

## Trigger

The user wants to be told an hour before a meeting.

## Outcome

The event reminds every device of the user an hour before it starts.

## Edge cases

- If the user declines notifications, the reminder is still saved with the entry.
