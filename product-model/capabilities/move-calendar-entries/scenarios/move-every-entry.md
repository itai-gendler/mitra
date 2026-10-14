---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Move entries to… and picks the destination
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The Product shows how many entries move, which arrive with everything, which lose something, and which stay
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Repeat, Reminders]}
  - {entity: task, effect: reads, facts: [Title, Due date, Estimate]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The User confirms the move
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The Product copies the entries into the destination, repoints links to them, and then deletes the originals
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Calendar]}
  - {entity: task, effect: changes, facts: [Calendar]}
  - {entity: availability, effect: changes, facts: [Calendar]}
  contexts:
    web:
      place: web::signed-in::move-entries
---

# Move every entry to another calendar

## Trigger

The user moves from a Mitra calendar to their CalDAV server.

## Outcome

The entries the destination can take are there with everything it can hold; the rest stay behind, listed by name.

## Edge cases

- Links from entries that stay behind keep pointing at the ones that moved, even into Notion, which gives every page a new ID.
