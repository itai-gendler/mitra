---
kind: alternative
routes:
  web: Web
steps:
- text: The User moves a calendar's entries to a Notion calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: 'The Product asks what to do with the repeating ones: leave them here, or flatten them into single entries'
  kind: product
  actor: user
  entities:
  - {entity: task, as: series, effect: reads, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The User chooses Flatten into single entries
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::move-entries
- text: The Product writes out each occurrence of the coming year as its own entry in the destination and deletes the series
  kind: product
  actor: user
  entities:
  - {entity: task, as: flattened, effect: creates, to: To Do, facts: [Title, Calendar, Start, End, All day]}
  - {entity: task, as: series, effect: removes, from: To Do}
  contexts:
    web:
      place: web::signed-in::move-entries
---

# Flatten repeating entries on the way

## Trigger

The destination cannot repeat entries.

## Outcome

Each series arrives as single entries, one per occurrence in the coming year, that no longer repeat.

## Edge cases

- Mitra never flattens without asking.
- A series with occurrences changed on their own stays behind.
