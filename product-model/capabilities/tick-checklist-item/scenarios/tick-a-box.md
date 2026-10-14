---
kind: primary
routes:
  web: Web
steps:
- text: The User ticks "Send the invitations" in the rendered description
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Checklist]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product changes that line's box to ticked in the description
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Description]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Tick a box in the description

## Trigger

The invitations went out.

## Outcome

The box reads ticked in the description and the task's progress counts it.

## Edge cases

- An event's boxes can be ticked too, but count towards nothing.
- Unticking a box changes it back the same way.
