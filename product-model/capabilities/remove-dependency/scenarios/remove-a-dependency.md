---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the cross beside the draft in the review's Blocked by row
  kind: actor
  actor: user
  entities:
  - {entity: dependency, effect: reads, facts: [Entry to finish first]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product removes the dependency
  kind: product
  actor: user
  entities:
  - {entity: dependency, effect: removes}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Remove a dependency

## Trigger

The review no longer needs to wait.

## Outcome

The two entries are no longer linked and the line disappears.
