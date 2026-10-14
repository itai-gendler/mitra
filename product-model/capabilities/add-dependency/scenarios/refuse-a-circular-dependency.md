---
kind: validation
routes:
  web: Web
steps:
- text: The User picks, under Blocked by, an entry that already waits for this one
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product refuses the dependency and shows why
  kind: product
  actor: user
  entities:
  - {entity: dependency, effect: reads, facts: [Waiting entry, Entry to finish first]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Refuse a circular dependency

## Trigger

Two entries would each wait for the other.

## Outcome

Nothing is linked; the editor shows "This would create a circular dependency".
