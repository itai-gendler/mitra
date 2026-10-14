---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Remove all in the menu beside the count
  kind: actor
  actor: user
  entities:
  - {entity: participant, effect: reads, facts: [Email]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product empties the list
  kind: product
  actor: user
  entities:
  - {entity: participant, effect: removes}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Remove everyone

## Trigger

The meeting becomes a personal block.

## Outcome

The list is empty.
