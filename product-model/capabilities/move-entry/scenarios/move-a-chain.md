---
kind: alternative
routes:
  web: Web
steps:
- text: The User drags an entry that other entries wait for
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product asks Move dependent entries too?, with how many entries each choice moves
  kind: product
  actor: user
  entities:
  - {entity: dependency, effect: reads, facts: [Waiting entry, Entry to finish first]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The User chooses Keep the chain intact
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product moves the entry and moves the others only as far as needed to keep them in order
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Start, End]}
  - {entity: task, effect: changes, facts: [Start, End]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Move an entry that others depend on

## Trigger

A draft runs late and the review waiting for it should follow.

## Outcome

The entries waiting on it move as the user chose, so the chain stays in order.

## Decision points

### What moves with it

How should dependent entries move?

- Only this entry → the others stay where they are
- Keep the chain intact → later entries move later and, when this one moved earlier, earlier ones move earlier, each only as far as needed
- Move them all by the same amount → the whole chain moves by the same time, keeping the gaps

## Edge cases

- Mitra asks only when the choices would give different results.
- Repeating entries and unscheduled tasks in a chain are never moved; an entry moved with the chain takes its subtasks along.
- Changing times in the editor never moves other entries.
