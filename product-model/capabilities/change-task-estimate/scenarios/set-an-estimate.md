---
kind: primary
routes:
  web: Web
steps:
- text: The User types 3 hours into the Estimate field
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Estimate]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the estimate
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Estimate]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Set an estimate

## Trigger

The user expects a task to take three hours.

## Outcome

The unscheduled task carries the estimate, and scheduling it later gives it that length.
