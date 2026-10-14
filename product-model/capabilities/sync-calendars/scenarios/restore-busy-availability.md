---
kind: unattended
routes:
  web: Web
steps:
- text: A busy event written for availability was changed, moved or deleted at the provider
  kind: condition
  unattended: true
  entities:
  - {entity: availability, effect: reads, facts: [Busy or free, Start, End, Repeat]}
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product writes the busy events for the availability again
  kind: product
  entities:
  - {entity: event, effect: reads, facts: []}
  - {entity: availability, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Put busy availability back

## Trigger

Someone moves one of the busy events written for availability in another app.

## Outcome

The busy events match the availability again after the next sync.
