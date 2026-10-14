---
kind: unattended
routes:
  web: Web
steps:
- text: The calendar server collected a reply to an entry's invitation
  kind: condition
  unattended: true
  entities:
  - {entity: event, effect: reads, facts: []}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product updates the participant's reply
  kind: product
  entities:
  - {entity: participant, effect: changes, facts: [Reply]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Bring in participants' replies

## Trigger

An invitee accepts in their mail app.

## Outcome

The badge on their initial shows the reply after the next sync.
