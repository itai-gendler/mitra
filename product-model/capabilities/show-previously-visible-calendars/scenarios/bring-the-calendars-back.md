---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Show previously visible calendars
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Previously visible calendars]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product hides exactly the calendars that were hidden before and forgets the memory
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, facts: [Hidden]}
  - {entity: user, effect: changes, facts: [Previously visible calendars]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Bring the other calendars back

## Trigger

The user is done focusing on work.

## Outcome

The calendars showing before are back; those hidden before stay hidden, and one connected meanwhile shows.
