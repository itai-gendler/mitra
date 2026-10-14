---
kind: primary
routes:
  web: Web
steps:
- text: The User presses / and types part of the title
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The Product lists the matching entries, a repeating one once at its nearest occurrence
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Start, Calendar]}
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The User picks the entry
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The Product goes to its date and opens it
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Find an entry

## Trigger

The user remembers a meeting's title but not its date.

## Outcome

The view moves to the entry's date with its editor open.

## Edge cases

- Availability, and the busy events written for it, are never found.
