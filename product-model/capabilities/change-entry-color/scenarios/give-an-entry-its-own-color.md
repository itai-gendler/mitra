---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the dot in the header and picks a color
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Color]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the color with the entry
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Color]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Give an entry its own color

## Trigger

One appointment should stand out.

## Outcome

The entry wears its own color everywhere it shows.
