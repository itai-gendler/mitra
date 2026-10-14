---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the plus on Blocked by in the review's editor and picks the draft
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the dependency with the review
  kind: product
  actor: user
  entities:
  - {entity: dependency, effect: creates, facts: [Waiting entry, Entry to finish first, Broken]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Make an entry wait for another

## Trigger

The review cannot start until the draft is finished.

## Outcome

The review is blocked by the draft; a line runs from the draft's end to the review's start.

## Edge cases

- When the waiting entry already starts too early, the dependency is broken: its line turns red and the other entry is named in red until either moves back into order.
