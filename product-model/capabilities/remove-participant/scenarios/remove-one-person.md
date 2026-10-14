---
kind: primary
routes:
  web: Web
steps:
- text: The User points at a person and presses the cross
  kind: actor
  actor: user
  entities:
  - {entity: participant, effect: reads, facts: [Email]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product removes them from the entry
  kind: product
  actor: user
  entities:
  - {entity: participant, effect: removes}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Remove one person

## Trigger

Someone no longer needs to attend.

## Outcome

The person is off the list.
