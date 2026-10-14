---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Copy entries to… on a subscription and picks a destination
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The Product shows what the copy would cost
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Repeat, Reminders]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The User confirms
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The Product creates a copy of each entry in the destination
  kind: product
  actor: user
  entities:
  - {entity: event, effect: creates, facts: [Title, Calendar, Description, Location, Start, End, All day, Time zone, Repeat]}
  contexts:
    web:
      place: web::signed-in::move-entries
---

# Copy a subscription's entries

## Trigger

The user wants an editable copy of the school terms.

## Outcome

Each entry has an editable copy in the destination; the subscription is untouched.
