---
kind: alternative
routes:
  web: Web
steps:
- text: The User drags one occurrence of a repeating event while holding Ctrl
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product moves only that occurrence, which becomes an entry of its own
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Start, End, Repeat]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Move one occurrence of a series

## Trigger

One weekly meeting moves to Wednesday this week.

## Outcome

Only the dragged occurrence moves; the series skips its old date.

## Edge cases

- Without Ctrl, Mitra asks whether this entry, this and following entries, or all entries are meant; All entries moves every occurrence by the same amount.
