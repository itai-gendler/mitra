---
kind: alternative
routes:
  web: Web
steps:
- text: The User adds an email address
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The entry is in a Mitra calendar
  kind: condition
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product adds the person as a record only
  kind: product
  actor: user
  entities:
  - {entity: participant, effect: creates, facts: [Email, Role, Reply]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Record people in a Mitra calendar

## Trigger

The entry lives in a Mitra calendar.

## Outcome

The people are listed with no organizer; nobody is invited and no replies come in.
