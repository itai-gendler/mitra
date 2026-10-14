---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses the cross beside a reminder
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Reminders]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product removes it
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Reminders]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Remove a reminder

## Trigger

A reminder is no longer wanted.

## Outcome

The entry has one reminder fewer.
