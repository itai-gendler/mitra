---
kind: primary
routes:
  web: Web
steps:
- text: The User points at a person and marks them optional
  kind: actor
  actor: user
  entities:
  - {entity: participant, effect: reads, facts: [Role]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the role
  kind: product
  actor: user
  entities:
  - {entity: participant, effect: changes, facts: [Role]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Mark someone optional

## Trigger

A colleague may join if they can.

## Outcome

The person shows as Optional.
