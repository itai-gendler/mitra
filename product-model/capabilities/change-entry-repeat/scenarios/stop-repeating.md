---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks Does not repeat
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product removes the rule from the series
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Stop an entry repeating

## Trigger

A weekly meeting is over for good.

## Outcome

The entry no longer repeats; Mitra does not ask which occurrences are meant.
