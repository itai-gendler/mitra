---
kind: primary
routes:
  web: Web
steps:
- text: The User picks Private in the row with the eye
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Visibility]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the visibility with the entry
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Visibility]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Make an entry private

## Trigger

A doctor's appointment sits in a calendar the family shares.

## Outcome

The entry is saved as Private, so other apps show only that the time is taken.
